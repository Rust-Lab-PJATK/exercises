
# Materiały Pomocnicze do Zadań Średnio Zaawansowanych z Rusta

## Wprowadzenie do Średnio Zaawansowanych Konceptów

Te materiały pomogą Ci w rozwiązywaniu zadań średnio zaawansowanych z Rusta. Skupimy się na iteratorach, `enum` i pracy z serwerem HTTP.

---

## Zadanie 1: Implementacja własnego iteratora

### 1.1. Jak działają `Iterator` i `next()`

`Iterator` to `trait` w Rust, który definiuje metodę `next()`. Możemy stworzyć własny iterator, implementując ten trait dla własnej struktury.

Przykład:
```rust
struct EvenNumbers {
    current: u32,
    max: u32,
}

impl EvenNumbers {
    fn new(max: u32) -> Self {
        EvenNumbers { current: 0, max }
    }
}

impl Iterator for EvenNumbers {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        self.current += 2;
        if self.current <= self.max {
            Some(self.current)
        } else {
            None
        }
    }
}
```

**Wyjaśnienie:**
- Struktura `EvenNumbers` przechowuje `current` (obecna liczba) oraz `max` (maksymalna wartość).
- Implementacja `Iterator` wymaga zdefiniowania typu `Item` oraz metody `next()`, która zwraca `Option<Self::Item>`.
- `Some(value)` oznacza, że iterator może zwrócić kolejną wartość, a `None` oznacza koniec iteracji.

### 1.2. Używanie `sum()` z iteratorami

Możemy używać wbudowanych metod dla iteratorów, takich jak `sum()`, `collect()` i innych:
```rust
let sum: u32 = EvenNumbers::new(10).sum();
println!("Suma liczb parzystych do 10 wynosi: {}", sum);
```

---

## Zadanie 2: Własny system logowania z `enum` i `match`

### 2.1. Praca z `enum` w Rust

`enum` w Rust pozwala na definiowanie zbioru wartości. Każdy wariant może przyjmować różne typy danych:
```rust
enum LogLevel {
    Info,
    Warning,
    Error,
}
```

### 2.2. Wykorzystanie `match` do rozróżniania wariantów

`match` jest podobny do `switch` w innych językach, ale jest bardziej elastyczny:
```rust
fn log(level: LogLevel, message: &str) {
    match level {
        LogLevel::Info => println!("[INFO]: {}", message),
        LogLevel::Warning => println!("[WARNING]: {}", message),
        LogLevel::Error => println!("[ERROR]: {}", message),
    }
}
```

**Wyjaśnienie:**
- `match` sprawdza wartość `level` i wykonuje odpowiedni blok kodu.
- To jest kluczowy element do rozróżniania logów na podstawie poziomu logowania.

### 2.3. Tworzenie struktur z danymi

Struktury mogą przechowywać dodatkowe informacje o logach:
```rust
struct LogMessage {
    level: LogLevel,
    content: String,
}
```

---

## Zadanie 3: Prosty serwer HTTP z `hyper` lub `axum`

### 3.1. Instalacja `hyper` lub `axum`

Dodaj `hyper` lub `axum` do swojego projektu w `Cargo.toml`:
```toml
[dependencies]
axum = "0.6"
tokio = { version = "1", features = ["full" }
```

### 3.2. Tworzenie podstawowego serwera z `axum`

Przykład prostego serwera z `axum`:
```rust
use axum::{routing::get, Router};
use std::net::SocketAddr;

#[tokio::main]
async fn main() {
    let app = Router::new().route("/", get(|| async { "Hello, World!" }));

    let addr = SocketAddr::from(([127, 0, 0, 1], 3000));
    println!("Server is running on http://{}", addr);

    axum::Server::bind(&addr)
        .serve(app.into_make_service())
        .await
        .unwrap();
}
```

### 3.3. Obsługa różnych tras

Możemy obsługiwać różne trasy poprzez dodawanie kolejnych `route`:
```rust
let app = Router::new()
    .route("/", get(|| async { "Welcome to the homepage" }))
    .route("/hello", get(|| async { "Hello, user!" }))
    .route("/status", get(|| async { "Server is running" }));
```

**Wyjaśnienie:**
- `Router::new()` tworzy nową instancję routera.
- `route` określa, jakie odpowiedzi mają być zwracane dla różnych ścieżek URL.
- `tokio::main` jest wymagane do używania `async` w `main`.

### 3.4. Uruchomienie serwera

Po uruchomieniu serwera za pomocą `cargo run`, odwiedź w przeglądarce:
```
http://127.0.0.1:3000/
http://127.0.0.1:3000/hello
http://127.0.0.1:3000/status
```

Każda z tras powinna zwrócić odpowiedni komunikat.

---

# Dodatkowe Zasoby

- **Oficjalna dokumentacja**: [https://doc.rust-lang.org/book/](https://doc.rust-lang.org/book/)
- **Tokio - Asynchronous Programming**: [https://tokio.rs](https://tokio.rs)
- **Axum Documentation**: [https://docs.rs/axum/latest/axum/](https://docs.rs/axum/latest/axum/)
