
# Rust Exercises - Intermediate Level

## 1. Implementing your own iterator

Write an `Iterator` that will generate even numbers up to given `n`.

### Requirements

- Implement the `next()` method
- Add a `sum()` method that will return the sum of all the generated numbers
- Check if your implementation works by displaying the results in the terminal

### Example

```rust
let mut even_numbers = EvenNumbers::new(10);

while let Some(num) = even_numbers.next() {
    println!("{}", num);
}
```

---

## 2. Your own logging sysem with `enum` and `match`

Create your own logging system (`Info`, `Warning`, `Error`) using an `enum`.

### Requirements

- Write a `log` function, which accepts an `enum` and prints out messages accordingly
- Add a `LogMessage` struct for storing the log level and the message
- Implement unit tests to check if your solution works properly

### Example

```rust
enum LogLevel {
    Info,
    Warning,
    Error,
}

fn log(level: LogLevel, message: &str) {
    match level {
        LogLevel::Info => println!("[INFO]: {}", message),
        LogLevel::Warning => println!("[WARNING]: {}", message),
        LogLevel::Error => println!("[ERROR]: {}", message),
    }
}
```

---

## 3. Simple HTTP server using `hyper` or `axum`

Build an HTTP server that responds to requests for routes such as `/`, `/hello`, `/status`.

### Requirements

- Use `hyper` or `axum` to create your server
- It should send a different response depending on received request
- Implement support for GET and POST requests

### Example

```
GET /hello
Response: "Hello, world!"

GET /status
Response: "Server is running"
```

---

These exercises are a perfect challenge for those who have learned the basics of Rust and want to go deeper. Good luck!
