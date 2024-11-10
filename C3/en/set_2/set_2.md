# Advanced Ownership And Borrowing Exercises

## Safe access to shared data (`Mutex` and `Arc`)

Create a `Counter` structure that allows you to increment its value from different threads. Use `Arc<Mutex<Counter>>` to synchronise access to the shared counter between threads.

### Requirements

- Implement an `increment` method that increases the counter's value by 1
- Use `Arc` to enable sharing the `Counter` structure between threads and `Mutex` to prevent multiple threads from accessing the counter at the same time
- Test your `Counter` by spawning multiple threads

---

## 2. Circular Buffer

Design a `CircularBuffer` structure that allows one to safely write and read data in a circular buffer. It should have a limited capacity and overwrite the oldest data after reaching the limit.

### Requirements

- Your structure should store data using a vector and have a maximum capacity
- Add a moving pointer mechanism to overwrite the oldest data
- Use `&mut self` to handle data change without moving ownership

---

## 3. Data management using `Cow` (Clone On Write)

Create a `process_data` function that accepts a reference to a `str` and uses `Cow<str>` to create a modified version of provided text only if it's necessary.

### Requirements

- Use `Cow` to avoid copying data when it's not necessary to do so
- Funkcja powinna sprawdzić, czy tekst wymaga modyfikacji i odpowiednio utworzyć kopię lub użyć oryginału.
- Your function should check if the text needs to be changed and either create a copy or use the original
- Use `to_mut` to obtain a mutable reference if change is needed
