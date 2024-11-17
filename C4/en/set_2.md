# Intermediate exercisees - error handling

## Help section

### Creating custom error types

- Rust allows you to create custom error types in order to represent specific issues. Implementing the `std::fmt::Display` and `std::error::Error` traits enables you to integrate your custom errors with external error handling crates
- **Hint**: If possible, use the `derive` macro to use default trait implementations

### Error handling with `thiserror` and `anyhow`

- Crates like `thiserror` (for defining custom error types) and `anyhow` (for flexible error handling) can improve code readability and simplify error handling
- **Hint**: `thiserror` provides useful annotations for custom error types, whereas the `anyhow!` macro from the `anyhow` crate makes it easier to define custom error types

### Konwersja błędów za pomocą `From` i `Into`

- Implementing the `From` trait allows you to convert errors to a uniform type, making it easier to combine and manage different kinds of errors
- **Hint**: Use `derive` with `From` on your custom errors or implement it manually for interoperability

## Exercises

1. **Defining your own error type**
   - Create a `MathError` that handles two cases: `DivideByZero` and `NegativeSquareRoot`. Implement the `Display` and `Error` traits
   - **Requirements**: Define `MathError` as an `enum`. Implement `Display` for readable error message and use `derive` for `Error`.

2. **Using `thiserror` for custom errors**
   - Use `thiserror` to define a custom error type for a simple app that processes files. Implement error kinfs such as `FileNotFound` and `ParseError`.
   - **Requirements**: define `FileProcessingError` using `thiserror`, including typical error kinds related to file I/O

3. **Combining `anyhow` with error propagation**
   - Write a file that reads a series of numbers from a file and parses them. Use `anyhow` for flexible error handling and the `?` operator for propagation
   - **Requirements**: use `anyhow` to simplify returning errors and add detailed error messages
