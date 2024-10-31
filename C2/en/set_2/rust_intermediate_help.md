
# Rust Intermediate Help

## Prime numbers iterator

Creating a custom iterators requires you to define a struct and implement the `Iterator` trait for it. You can add an auxiliary `is_prime` method to check, if a given number is a prime.

### Hints

- The `is_prime` method can test a number using a divisor in range from `2` to `sqrt(n)`.
- The `next` method should iterate through integers, using `is_prime` to only return primes.

---

## Logging system with verbosity levels

Using an `enum` for describing log levels (eg. `Debug`, `Info`, `Warning`, `Error`) allows us to control their verbosity.

### Hints

- Define a struct to store the log level and target file
- The `log` method should compare the message's log level to the one set in the `Logger` to determine whether that message should be saved or not
- Use `std::fs::File` and `write!` to save messages to the log file

---

## Async HTTP server with JSON support

In order to build an `axum` HTTP server wtih JSON support, you can use asynchronous functions and the `serde_json` crate for parsing JSON data.

### Hints

- Use `Router` from `axum` to create a POST route
- Have your struct derive from `serde::Deserialize` to automatically implement conversion from JSON to struct
- Async functions allow you to handle requests in parallel

---

## Processing CSV files

The `csv` crate in Rust enables you to easily read and analyse data in CSV files. You can read each row as a `Record` and analyse a specific column after going through all the rows.

### Hints

- Use `ReaderBuilder` from the `csv` crate to read a CSV file
- Iterate throguh every `Record` and grab the right column values
- Calculate the average by summing up all the values and dividing that sum by the number of records

---

# Additional Resources

- **Serde**: [https://serde.rs/](https://serde.rs/)
- **CSV crate**: [https://docs.rs/csv/](https://docs.rs/csv/)
- **Axum Documentation**: [https://docs.rs/axum/latest/axum/](https://docs.rs/axum/latest/axum/)
