
# Rust Exercises For Beginners (Volume 2, Set 1)

## 1. Simple `Book` struct with a method

Write a simple `Book` struct, which stores a book's title and author as a `String`. Add a method that prints out the book's full description using the following format: "Title: [title], Author: [author]".

### Requirements

- Create a `Book` struct with `title` and `author` fields
- Add a `describe()` method that prints out the book's description

### Example

```rust
let book = Book { title: String::from("Hobbit"), author: String::from("J.R.R. Tolkien") };
book.describe(); // Title: Hobbit, Author: J.R.R. Tolkien
```

---

## 2. Using the `Option` type

Write a `find_element` function that accepts a vector of integers and a value to find in that vector. Your function should return `Option<usize>`, where `Some(index)` means the position of found value in the vector, whereas `None` means that the value was not found.

### Requirements

- Use the `Option` type to handle the case of missing value
- Test your function by returning the elements position or printing out a "not found" message

### Example

```rust
let vec = vec![1, 2, 3, 4, 5];
let result = find_element(&vec, 3);
println!("{:?}", result); // Some(2)
```

---

## 3. `Result` of number division

Write a `divide` function that accepts two integers and returns `Result<f64, String>`. If the second argument equals 0, your function should provide this message as the error value: "Error zero division".

### Requirements

- Use the `Result` type to handle zero division error
- Return either the division result or the error message via the `Result` type

### Example

```rust
let result = divide(10, 2);
println!("{:?}", result); // Ok(5.0)
```

---

## 4. Simple file operations

Write a program that creates an `output.txt` file and writes `Welcome, Rust!` to it. Then open the file and print its content to the console.

### Requirements

- Use `std::fs::File` and the `write!` macro to write the message to the file.
- Read the message from the file and print it to the console.

### Przykład:
```rust
write_to_file("output.txt", "Welcome, Rust!");
read_from_file("output.txt"); // Welcome, Rust!
```

---
