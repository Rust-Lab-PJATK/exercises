
# Supporting materials for advanced Rust exercises

## Introduction to advanced concepts

These materials should help you do the advanced Rust exercises. We'll focus on `async`, memory management, and building a simple database with `BTreeMap` i `serde`.

---

## Exercise 1: Implementin your own `async executor`

### 1.1. How does `async` work in Rust?

In Rust, `async` in Rust allows us to write concurrent code. The fundamental element of every `async` function is a `Future`

- `Future` is a value that might not be available at the time it's being accessed
- `async fn` creates a function that returns a `Future`.

Przykład:
```rust
async fn example() {
    println!("Hello from async!");
}
```

### 1.2. `Pin`, `Waker`, and `Poll`

- **`Pin`**: ensures that the `Future` won't get moved in memory, which is required for concurrency to work.
- **`Waker`** resumes a `Future` after we're done waiting for a resource.
- **`Poll`** informs us whether a `Future` has returned a result (`Poll::Ready`) or it's still running (`Poll::Pending`).

Example of a custom `Future`:

```rust
use std::pin::Pin;
use std::task::{Context, Poll};
use std::future::Future;

struct MyFuture;

impl Future for MyFuture {
    type Output = i32;

    fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output> {
        // Simulating the result of a complex task
        Poll::Ready(42)
    }
}
```

### 1.3. Creating your own `async executor`

Create a struct for storing tasks (`Future`) with support for resuming them:

```rust
struct MyExecutor {
    // Storing tasks
}

impl MyExecutor {
    fn new() -> Self {
        MyExecutor { /* initialization */ }
    }

    fn run(&self) {
        // Execution
    }
}
```

---

## Zadanie 2: Your own `memory allocator`

### 2.1. `GlobalAlloc`

We can build our own memory allocator in Rust by implementing `GlobalAlloc`. It gives us more control over the way the memory is allocated and freed.

Example:

```rust
use std::alloc::{GlobalAlloc, Layout, System};

struct MyAllocator;

unsafe impl GlobalAlloc for MyAllocator {
    unsafe fn alloc(&self, layout: Layout) -> *mut u8 {
        System.alloc(layout)
    }

    unsafe fn dealloc(&self, ptr: *mut u8, layout: Layout) {
        System.dealloc(ptr, layout)
    }
}
```

### 2.2. Implementing a `bump allocator`

A `bump allocator` allocates memory sequentially, which is efficient, but offers no support for deallocating individual blocks:

```rust
struct BumpAllocator {
    memory: Vec<u8>,
    offset: usize,
}

impl BumpAllocator {
    fn new(size: usize) -> Self {
        Self {
            memory: vec![0; size],
            offset: 0,
        }
    }

    fn alloc(&mut self, size: usize) -> Option<&mut [u8]> {
        if self.offset + size <= self.memory.len() {
            let start = self.offset;
            self.offset += size;
            Some(&mut self.memory[start..self.offset])
        } else {
            None
        }
    }
}
```

### 2.3. Testing your allocator

Test your allocator by trying out different memory block sizes and checking if any errors occurr:

```rust
let mut allocator = BumpAllocator::new(1024);
let block = allocator.alloc(128).expect("Failed to allocate memory");
```

---

## Exercise 3: Simple database powered by `B-Tree` and `serde`

### 3.1. What's a `BTreeMap`?

`BTreeMap` is a data structure that stores key-value pairs in an ordered manner. It's optimised for insertion, searching, and deletion.

Example:

```rust
use std::collections::BTreeMap;

let mut map = BTreeMap::new();
map.insert("key", "value");
```

### 3.2. Serialization and deserialization with `serde`

`serde` allows us to convert structures to a JSON format and vice versa:

```rust
use serde::{Serialize, Deserialize};

#[derive(Serialize, Deserialize)]
struct User {
    name: String,
    age: u32,
}
```

### 3.3. Saving and loading data to/from a file

Use `serde_json` to save and load data to/from a file:

```rust
use std::fs;
use serde_json::Result;

fn save_to_file(data: &BTreeMap<String, String>, filename: &str) -> Result<()> {
    let json = serde_json::to_string(data)?;
    fs::write(filename, json)?;
    Ok(())
}

fn load_from_file(filename: &str) -> Result<BTreeMap<String, String>> {
    let data = fs::read_to_string(filename)?;
    let map: BTreeMap<String, String> = serde_json::from_str(&data)?;
    Ok(map)
}
```

### 3.4. Writing `insert()`, `get()` and `delete()` methods

Example implementation of CRUD operations:

```rust
impl Database {
    fn insert(&mut self, key: String, value: String) {
        self.data.insert(key, value);
    }

    fn get(&self, key: &str) -> Option<&String> {
        self.data.get(key)
    }

    fn delete(&mut self, key: &str) {
        self.data.remove(key);
    }
}
```

---

# Additional Resources

- **Future, Waker, and Executors**: [https://rust-lang.github.io/async-book/](https://rust-lang.github.io/async-book/)
- **Rust Memory Management**: [https://doc.rust-lang.org/nomicon/](https://doc.rust-lang.org/nomicon/)
- **Serde JSON**: [https://docs.rs/serde_json/](https://docs.rs/serde_json/)