# Introduction to Rust

## 1. Installation

In order to start working with Rust, you'll have to install it first. The easiest way to do it is using `rustup`:

1. Go to [https://rust-lang.org](https://www.rust-lang.org/) and click "Get Started".
2. If the OS you use is:
    - Windows
      - Download the Rustup installer from [https://win.rustup.rs/x86_64](https://win.rustup.rs/x86_64)
    - MacOS or Linux
      - Run the following command in your terminal: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
3. Follow the onscreen instructions to complete the installation.

Once the installation has finished, you can check if everything works by typing the following in the terminal:

```bash
rustc --version
```

This command should print out the currently installed Rust version.

## 2. Creating your first project

1. Enter this command in your terminal

```bash
cargo new project_name
```

Replace `project_name` with the actual name you want to use for your project.
2. Enter the project's directory

```bash
cd project_name
```
3. Run the project

```bash
cargo run
```

`cargo` is a tool for managing Rust projects. After running the last command, you should see "Hello, world!" in your terminal.

---

# Supporting materials for exercises

## Exercise 1: Basic Calculator

### 1.1. Working with Input/Output (`std::io`)

In order to obtain user input in Rust, we use the `std::io` module. Here's an example:

```rust
use std::io;

fn main() {
    let mut input = String::new(); // Create a new, empty `String`
    io::stdin()
        .read_line(&mut input) // Read user input
        .expect("Failed to read the line");

    println!("You entered: {}", input.trim()); // Display the data
}
```

**Explanation:**
- `let mut input = String::new();` creates a variable that will store user input
- `io::stdin().read_line()` allows us to read a line from the input stream
- `input.trim()` removes redundant whitespace characters (eg. newline character).

### 1.2. Parsing Numbers

The input we've read is a `String`, so we need to convert it to a number:

```rust
let number: i32 = input.trim().parse().expect("Please enter a number");
```

### 1.3. Basic Arithmetic Operations

Basic arithmetic operations in Rust look and work the same as in most programming languages:

- Addition: `a + b`
- Subtraction: `a - b`
- Multiplication: `a * b`
- Division: `a / b`

Example function:

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

---

## Exercise 2: Temperature Converter

### 2.1. Creating functions

Function in rust have a very simple syntax:

```rust
fn function_name(argument1: type1) -> return_type {
    // function's code
}
```

Here's an example of conversion from Celsius to Fahrenheit:

```rust
fn celsius_to_fahrenheit(c: f64) -> f64 {
    c * 9.0 / 5.0 + 32.0
}
```

### 2.2. Conditional Instructions (`if`)

Rust allows you to execute different code based on a certain condition using `if`:

```rust
if condition {
    // this code will run if a condition is met
} else {
    // (optional) this will run if the condition's not met
}
```

Target conversion unit choice example

```rust
let target_unit = String::from("F");

if target_unit == "F" {
    // Convert to Fahrenheit
} else {
    // Convert to Celsius
}
```

---

## Exercise 3: Number Guessing Game

### 3.1. Choosing random numbers with the `rand` crate

In order to use the `rand` crate in our project, we need to write the following to the `Cargo.toml` file:

```toml
[dependencies]
rand = "0.8"
```

Then we import it in our code like so:

```rust
use rand::Rng;

fn main() {
    let secret_number = rand::thread_rng().gen_range(1..=100);

    println!("The secret number is: {}", secret_number);
}
```

### 3.2. Loops (`loop`)

The `loop` instruction enables you to run a piece of code indefinitely or until it gets halted:

```rust
loop {
    // some code that may repeat forever
}
```

Example:

```rust
loop {
    let mut input = String::new();

    print!("Enter a number: ");
    io::stdin().read_line(&mut input).expect("Read error");

    let guess: u32 = input.trim().parse().expect("This is not a number");

    if guess < secret_number {
        println!("My number is greater than that.");
    } else if guess > secret_number {
        println!("My number is lower than that.");
    } else {
        println!("Correct!");
        break; // <- stops the loop
    }
}
```

**Wyjaśnienie:**
- `loop` repeats the code block until `break` is used.
- `if` lets you check whether a condition was met or not and take different actions based on that.

---

# Additional Resources

- **Oficial documentation**: [https://doc.rust-lang.org/book/](https://doc.rust-lang.org/book/)
- **Rust by Example**: [https://doc.rust-lang.org/rust-by-example/](https://doc.rust-lang.org/rust-by-example/)
- **Rust Playground**: you can test your code there without installing Rust - [https://play.rust-lang.org/](https://play.rust-lang.org/).
