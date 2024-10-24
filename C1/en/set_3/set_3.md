
# Rust Exercises - Advanced Level

## 1. Implementing your own `async executor`

Create a minimal `async executor`, capable of running `Future` as well as managing `Waker` and `Poll`.

### Requirements

- Implement support for `Future` and basic concurrency
- Use `Pin`, `Waker`, and `Poll` for handling tasks
- Use `std::task` to write your own mechanism for waking up tasks
- Test your `async executor`, by running a couple `Future`s at once

### Example code to test your implementation

```rust
async fn example_task() {
    println!("Hello from a task!");
}

fn main() {
    let executor = MyExecutor::new();
    executor.spawn(example_task());
    executor.run();
}
```

---

## 2. Your own `memory allocator`

Implement your own memory management system in Rust using `GlobalAlloc`.

### Requirements

- Implement your allocator using `GlobalAlloc`.
- Support different allocation strategies, such as `bump allocator` or `buddy system`.
- Benchmark your allocator's performance against the default one used by Rust.
- Add unit tests to verify if your allocator works properly.

### Example code

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

#[global_allocator]
static A: MyAllocator = MyAllocator;
```

---

## 3. Simple database powered by `B-Tree` and `serde`

Build a simple database in Rust, which will utilise `B-Tree` for data storage alongside `serde` for serialization.

### Requirements

- Use `BTreeMap` to implement a structure for data storage.
- Implement `insert`, `get`, `delete`, `save` and `load` methods for data manpulation and disk I/O.
- Take advantage of `serde` to implement (de)serialization.
- Test your database by inserting, deleting and loading some dummy data.

### Example code

```rust
use serde::{Serialize, Deserialize};
use std::collections::BTreeMap;
use std::fs;

#[derive(Serialize, Deserialize)]
struct Database {
    data: BTreeMap<String, String>,
}

impl Database {
    fn new() -> Self {
        Database { data: BTreeMap::new() }
    }

    fn insert(&mut self, key: String, value: String) {
        self.data.insert(key, value);
    }

    fn save_to_file(&self, filename: &str) -> std::io::Result<()> {
        let json = serde_json::to_string(&self.data)?;
        fs::write(filename, json)
    }
}
```

---

# Additional resources

- **Asynchronous Programming**: [https://tokio.rs](https://tokio.rs)
- **Advanced Memory Management**: [https://doc.rust-lang.org/nomicon/](https://doc.rust-lang.org/nomicon/)
- **Serde Documentation**: [https://docs.rs/serde/](https://docs.rs/serde/)