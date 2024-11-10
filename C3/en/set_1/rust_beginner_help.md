# Ownership And Borrowing In Rust - Help

## Ownership Basics

In Rust, every value has its owner, and when the owner goes out of scope, the value gets deallocated from memory.

### Hints

- Every value has exactly one owner at any given point
- After using `move`, the value is no longer available wartość in its previous scope

---

## Borrowing And References

In order to gain access to a value without changing its ownership, use a reference. It allows you to borrow the value without transferring its ownership to the borrower.

### Hints

- Use `&` to create references and borrow values
- In order to modify a value, use `&mut` to create a mutable reference

---

## Transferring Ownership And Functions

When a value is passed to a function, its ownership gets transferred to the argument, unless you use a reference.

### Hints

- By adding a `&` to a function's argument, you require it to borrow a value instead of taking over its ownership
- Once the function has finished running, all the references passed as arguments get removed

---

## Borrow Checker Limitations

Rust doesn't allow you to create multiple mutable references, which prevents race conditions from occurring.

### Hints

- You can either operate on multiple immutable references or on a single mutable reference at a time
