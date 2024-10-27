
# Zadania z Rusta dla Średnio Zaawansowanych

## 1. Implementacja własnego iteratora
Napisz własny `Iterator`, który generuje liczby parzyste do podanej liczby `n`.

### Wymagania:
- Zaimplementuj dla niego metodę `next()`.
- Dodaj metodę `sum()`, która zwraca sumę wszystkich wygenerowanych liczb.
- Przetestuj działanie iteratora, wyświetlając wyniki w terminalu.

### Przykład:
```rust
let mut even_numbers = EvenNumbers::new(10);
while let Some(num) = even_numbers.next() {
    println!("{}", num);
}
```

---

## 2. Własny system logowania z `enum` i `match`
Stwórz system logowania, który obsługuje różne poziomy logowania (`Info`, `Warning`, `Error`), używając `enum`.

### Wymagania:
- Zaimplementuj funkcję `log`, która przyjmuje `enum` i odpowiednio wypisuje komunikaty.
- Dodaj struktury `LogMessage`, które przechowują poziom logowania oraz treść.
- Zaimplementuj testy jednostkowe, aby sprawdzić poprawność działania.

### Przykład:
```rust
enum LogLevel {
    Info,
    Warning,
    Error,
}

fn log(level: LogLevel, message: &str) {
    match level {
        LogLevel::Info => println!("[INFO]: {}", message),
        LogLevel::Warning => println!("[WARNING]: {}", message),
        LogLevel::Error => println!("[ERROR]: {}", message),
    }
}
```

---

## 3. Prosty serwer HTTP z `hyper` lub `axum`
Zbuduj prosty serwer HTTP, który obsługuje podstawowe trasy, takie jak `/`, `/hello`, `/status`.

### Wymagania:
- Użyj `hyper` lub `axum` do stworzenia serwera.
- Serwer powinien zwracać różne odpowiedzi w zależności od zapytania.
- Zaimplementuj obsługę zapytań GET i POST.

### Przykładowe Wejście/Wyjście:
```
GET /hello
Response: "Hello, world!"

GET /status
Response: "Server is running"
```

---

Te zadania są doskonałym wyzwaniem dla osób, które już opanowały podstawy i chcą pogłębić swoje umiejętności w Rust. Powodzenia!
