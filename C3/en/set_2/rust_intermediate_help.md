# Ownership and borrowing in Rust - advanced help

## `Arc` and `Mutex` in multithreading

When data is shared between threads, it needs to be managed safely. `Arc` is an atomic reference counter and `Mutex` ensures that only one thread can access it at a time

### Hints

- `Arc` gives you a thread-safe data access by counting references
- `Mutex` blocks access to data for other threads so that only one of them can modify them at a time

---

## Circular Buffer

Circular buffer is a structure that efficiently manages fixed-size data by overwriting the oldest elements when the buffer is full.

### Hints

- The write pointer should get moved every time a new element gets added
- Overwriting the oldest data requires you to keep track of the initial index

---

## Memory Optimisation With `Cow`

`Cow` (Clone On Write) allows you to avoid copying data if no modification is performed. `Cow` uses the original value until a mutable version is needed

### Hints

- `Cow::Borrowed` holds a reference to data, until a change is required
- The `to_mut` method converts `Cow` to a mutable type
