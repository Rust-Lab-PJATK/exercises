
# Intermediate Rust Exercises (Volume 2, Set 2)

## 1. Iterator that returns prime number

Write a `PrimeNumbers` struct that implements the `Iterator` trait and generates prime numbers up until specified `n`

### Requirements

- Implement the `Iterator` trait for `PrimeNumbers` to generate subsequent primes

### Example

```rust
let mut primes = PrimeNumbers::new(20);

while let Some(prime) = primes.next() {
    println!("{}", prime);
}
```

---

## 2. Logging system with verbosity levels

Build a logging system that allows you to select different verbosity levels (`Debug`, `Info`, `Warning`, `Error`) and saves the logs to a text file by default.

### Requirements

- Define a `LogLevel` enum and a `Logger` struct, which stores the verbosity level and the target log file
- Implement a `log` method that logs specific messages based on their verbosity level
- Ensure that all logs are saved to an `app.log` file

### Example

```rust
let mut logger = Logger::new(LogLevel::Info, "app.log");
logger.log(LogLevel::Warning, "This is a warning!");
logger.log(LogLevel::Debug, "Debugging..."); // Won't get logged, because verbosity is set to Info
```

---

## 3. Asynchronous HTTP server with JSON support

Create an asynchronous `axum` HTTP server, which supports `POST` requests and accepts JSON body data. Your server should also parse the request body and send a response in the same format.

### Requirements

- Your server should handle the `POST /submit` and expect a JSON body containing both `name` and `age` fields
- Use the `serde_json` crate for serializing and deserializing JSON data.

### Example

```
POST /submit
Request JSON: {"name": "Alice", "age": 30}
Response JSON: {"status": "success", "name": "Alice", "age": 30}
```

---

## 4. Processing CSV files and analyzing their data

Write a `process_csv` function that reads data from a CSV file and returns the arithmetic mean of numbers in a specified column.

### Requirements

- Use the `csv` crate to read data from a CSV files

### Example

```rust
let avg = process_csv("data.csv", "score");
println!("Arithmetic mean: {}", avg);
```

---
