
# Exercises for beginners - error handling

## Help section

### Basic error handling using `Result` and `Option`

- Rust uses `Result` and `Option` types to handle errors and missing values. `Result` return type indicates an operation that may fail, containing `Ok(T)` for a success or `Err(E)` for an error
- **Hint**: use `match` to handle both `Ok` and `Err` cases in a readable way

### `unwrap()` and `expect()` methods

- `unwrap()` and `expect()` may simplify error handling, but use them with caution, as they cause the program to panic if an error occurs
- **Hint**: `expect("message")` allows you to define a custom error message

### Error propagation with `?`

- The `?` operator simplifies error propagation in functions that return a `Result` by stopping their execution and returning an `Err` if an error occurs
- **Hint**: use the `?` operator only in functions that return `Result` or `Option`

## Exercises

1. **Error handling using `Result`**
   - Write a function that divides two numbers and returns a `Result<f32, String>`. If the second argument equals 0, return an error message inside an `Err`.
   - **Requirements**: define a `divide_numbers` function with a `Result` return type. Handle both the success and error cases using `match`.

2. **Using `unwrap()` and `expect()`**
   - Create a function that attempts to convert a `String` to an integer. Use `unwrap` or `expect` to handle invalid numbers
   - **Requirements**: Define a `parse_integer` function and use `expect` to define a better error message

3. **Error propagation with `?`**
   - Implement a function that reads the content of some file and returns it as a `String`. Use the `?` operator to handle potential errors
   - **Requirements**: define a `read_file` function and use the `?` operator to handle file read errors
