
# Ownership And Borrowing For Beginners

## 1. Transferring Ownership

Write a function that accepts a `String`, moves its ownership and displays its content. Try calling the function with the same value twice and see what happens.

### Requirements

- Definte a `show_ownership` function that accepts a `String`.
- Check what happens if you attempt to use the variable after its ownership has been moved

---

## 2. Borrowing Values

Write a function that accepts a reference to a `String` and displays its value without moving its ownership

### Requirements

- Define a `show_borrowed` function that accepts `&String`.
- Call this function multiple times using the same variable

---

## 3. Mutable References

Write an `append_exclamation` function that accepts a mutable reference to a `String` and appends an exclamation at the end of the text

### Requirements

- Define a function that accepts `&mut String` and modifies its value
- Check what happens if you attempt to use another mutable reference to the same variable
