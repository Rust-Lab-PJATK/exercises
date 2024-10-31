# Rust Beginner Help

## `Book` struct with `describe` method

A structure (`struct`) in Rust allows you to store related data as a single object. You can add methods to a struct via the `impl` block.

### Hints

- Define a `Book` struct with some fields of type `String`, eg. `title` and `author`
- Add a method for displaying information about the book
- Use `&self` in said method to gain access to the struct's fields

---

## Using the `Option` type

`Option` type is used to represent a value that may or may not be available via `Some(value)` and `None` respectively.

### Hints

- Loop through the vector to find the value provided as the 2nd argument
- If you find it, return `Some(index)`
- Otherwise, return `None`

---

## Error handling with `Result`

`Result` is used for error handling. It can be either `Ok` (result/success) or `Err` (error). You can use `match` to differentiate between them.

### Hints

- Function can return `Err` if it detects division by zero
- Use `match` to check the `Result`'s value and print either the value or error

---

## File I/O Basics

Rust offers an `std::fs::File` struct and a built-in `std::io` module for working with files. The `write!` macro can be used to write some data to a file, and the `std::io::read_to_string` function to read the data from a file as text.

### Hints

- Use `File::create` to make a new file and `write!` macro to save some text to it.
- Use `File::open` to read the file and `std::io::read_to_string` to read the file's content to a `String`.

---
