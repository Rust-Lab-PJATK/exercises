
# Supporting materials for intermediate Rust exercises

## Introduction to intermediate concepts

These materials should help you do the intermediate Rust exercises. We'll focus on iterators, `enum`s, and working with an HTTP server.

---

## Exercise 1: Implementing your own iterator

### 1.1. How does an `Iterator` work?

`Iterator` is a `trait` (something like an `interface` in Java), which defines a `next()` method. You can create your own iterator by writing a struct that implements this trait.

Example:

```rust
struct EvenNumbers {
    current: u32,
    max: u32,
}

impl EvenNumbers {
    fn new(max: u32) -> Self {
        EvenNumbers { current: 0, max }
    }
}

impl Iterator for EvenNumbers {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        self.current += 2;
        if self.current <= self.max {
            Some(self.current)
        } else {
            None
        }
    }
}
```

**Explanation:**

- `EvenNumbers` struct stores the `current` and `max` value.
- `Iterator` requires you to implement an `Item` type and the `next()` method, which returns `Option<Self::Item>`.
- `Some(value)` means that your iterator can produce a new value, whereas `None` means the end of iteration.

### 1.2. Using `sum()` with iterators

We can use built-in iterator methods like `sum()`, `collect()` and many others:

```rust
let sum: u32 = EvenNumbers::new(10).sum();
println!("The sum of even numbers from 0 to 10 is: {}", sum);
```

---

## Exercise 2: Your own logging sysem with `enum` and `match`

### 2.1. Working with `enum`s in Rust

An `enum` allows you to define a set of possible values for a type:

```rust
enum LogLevel {
    Info,
    Warning,
    Error,
}
```

### 2.2. Using `match` to differentiate between variants

The `match` instruction is similar to `switch` in other programming languages, but the former is more flexible:

```rust
fn log(level: LogLevel, message: &str) {
    match level {
        LogLevel::Info => println!("[INFO]: {}", message),
        LogLevel::Warning => println!("[WARNING]: {}", message),
        LogLevel::Error => eprintln!("[ERROR]: {}", message),
    }
}
```

**Explanation:**
- `match` checks `level`'s value and executes an appropriate instruction based on that.
- This is a key element that enables us to tell the logs apart based on the log level.

### 2.3. Creating data structures

Structures can contain additional information about the logs:

```rust
struct LogMessage {
    level: LogLevel,
    content: String,
}
```

---

## Exercise 3: Simple HTTP serwer using `hyper` lub `axum`

### 3.1. Instalacja `hyper` lub `axum`

Add `hyper` or `axum` to your project in `Cargo.toml`:

```toml
[dependencies]
axum = "0.6"
tokio = { version = "1", features = ["full"] }
```

### 3.2. Tworzenie podstawowego serwera z `axum`

Example of a simple server using `axum`:

```rust
use axum::{routing::get, Router};
use std::net::SocketAddr;

#[tokio::main]
async fn main() {
    let app = Router::new().route("/", get(|| async { "Hello, World!" }));

    let addr = SocketAddr::from(([127, 0, 0, 1], 3000));
    println!("Server is running on http://{}", addr);

    axum::Server::bind(&addr)
        .serve(app.into_make_service())
        .await
        .unwrap();
}
```

### 3.3. Handling different routes

You can add support for different routes by chaining together multiple `route` calls:

```rust
let app = Router::new()
    .route("/", get(|| async { "Welcome to the homepage" }))
    .route("/hello", get(|| async { "Hello, user!" }))
    .route("/status", get(|| async { "Server is running" }));
```

**Explanation:**
- `Router::new()`creates a new router instance.
- Each `route()` method defines the response that should be sent for each route.
- `tokio::main` is required to use `async` in `main`.

### 3.4. Running the server

Start your server by running `cargo run and visit these URLs in your web browser:

```
http://127.0.0.1:3000/
http://127.0.0.1:3000/hello
http://127.0.0.1:3000/status
```

Each one should show a different message.

---

# Additional Resources

- **Official Documentation**: [https://doc.rust-lang.org/book/](https://doc.rust-lang.org/book/)
- **Tokio - Asynchronous Programming**: [https://tokio.rs](https://tokio.rs)
- **Axum Documentation**: [https://docs.rs/axum/latest/axum/](https://docs.rs/axum/latest/axum/)
