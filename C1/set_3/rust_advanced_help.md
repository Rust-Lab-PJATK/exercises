
# Materiały Pomocnicze do Zadań Zaawansowanych z Rusta

## Wprowadzenie do Zaawansowanych Konceptów

Te materiały pomogą Ci w rozwiązywaniu zadań zaawansowanych z Rusta. Skupimy się na `async`, zarządzaniu pamięcią, oraz budowaniu prostej bazy danych z `BTreeMap` i `serde`.

---

## Zadanie 1: Implementacja własnego `async executor`

### 1.1. Jak działa `async` w Rust

`async` w Rust pozwala na pisanie kodu współbieżnego. Podstawowym elementem `async` jest `Future`:
- `Future` to wartość, która może nie być jeszcze dostępna.
- `async fn` tworzy funkcję zwracającą `Future`.

Przykład:
```rust
async fn example() {
    println!("Hello from async!");
}
```

### 1.2. Praca z `Pin`, `Waker` i `Poll`

- **`Pin`**: Zapewnia, że `Future` nie zostanie przeniesiony w pamięci, co jest wymagane do poprawnej współbieżności.
- **`Waker`**: Służy do wznawiania `Future` po zakończeniu oczekiwania na zasoby.
- **`Poll`**: Informuje, czy `Future` zakończyło działanie (`Poll::Ready`) czy jest w trakcie (`Poll::Pending`).

Przykład własnego `Future`:
```rust
use std::pin::Pin;
use std::task::{Context, Poll};
use std::future::Future;

struct MyFuture;

impl Future for MyFuture {
    type Output = i32;

    fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output> {
        // Symulujemy zakończenie zadania
        Poll::Ready(42)
    }
}
```

### 1.3. Tworzenie prostego `async executor`

Stwórz strukturę do przechowywania zadań (`Future`) i obsłuż ich wznawianie:
```rust
struct MyExecutor {
    // Przechowywane zadania
}

impl MyExecutor {
    fn new() -> Self {
        MyExecutor { /* Inicjalizacja */ }
    }

    fn run(&self) {
        // Wykonywanie zadań
    }
}
```

---

## Zadanie 2: Własny `memory allocator`

### 2.1. Czym jest `GlobalAlloc`

W Rust można stworzyć własny alokator pamięci, implementując `GlobalAlloc`. Umożliwia to kontrolę nad tym, jak pamięć jest przydzielana i zwalniana.

Przykład:
```rust
use std::alloc::{GlobalAlloc, Layout, System};

struct MyAllocator;

unsafe impl GlobalAlloc for MyAllocator {
    unsafe fn alloc(&self, layout: Layout) -> *mut u8 {
        System.alloc(layout)
    }

    unsafe fn dealloc(&self, ptr: *mut u8, layout: Layout) {
        System.dealloc(ptr, layout)
    }
}
```

### 2.2. Implementacja `bump allocator`

`Bump allocator` przydziela pamięć w sposób sekwencyjny, co jest wydajne, ale nie obsługuje zwalniania pojedynczych bloków:
```rust
struct BumpAllocator {
    memory: Vec<u8>,
    offset: usize,
}

impl BumpAllocator {
    fn new(size: usize) -> Self {
        Self {
            memory: vec![0; size],
            offset: 0,
        }
    }

    fn alloc(&mut self, size: usize) -> Option<&mut [u8]> {
        if self.offset + size <= self.memory.len() {
            let start = self.offset;
            self.offset += size;
            Some(&mut self.memory[start..self.offset])
        } else {
            None
        }
    }
}
```

### 2.3. Testowanie alokatora

Przetestuj alokator, alokując różne rozmiary pamięci i sprawdzając, czy nie dochodzi do błędów:
```rust
let mut allocator = BumpAllocator::new(1024);
let block = allocator.alloc(128).expect("Nie udało się zaalokować pamięci");
```

---

## Zadanie 3: Prosta baza danych z `B-Tree` z użyciem `serde`

### 3.1. Czym jest `BTreeMap`

`BTreeMap` to struktura danych, która przechowuje klucze i wartości w uporządkowany sposób. Jest optymalna do operacji wstawiania, wyszukiwania i usuwania.

Przykład:
```rust
use std::collections::BTreeMap;

let mut map = BTreeMap::new();
map.insert("key", "value");
```

### 3.2. Serializacja i deserializacja z `serde`

`serde` pozwala na konwersję struktur do formatu JSON oraz odczytywanie ich z JSON:
```rust
use serde::{Serialize, Deserialize};

#[derive(Serialize, Deserialize)]
struct User {
    name: String,
    age: u32,
}
```

### 3.3. Zapis i odczyt danych z pliku

Użyj `serde_json` do zapisywania i wczytywania danych z pliku:
```rust
use std::fs;
use serde_json::Result;

fn save_to_file(data: &BTreeMap<String, String>, filename: &str) -> Result<()> {
    let json = serde_json::to_string(data)?;
    fs::write(filename, json)?;
    Ok(())
}

fn load_from_file(filename: &str) -> Result<BTreeMap<String, String>> {
    let data = fs::read_to_string(filename)?;
    let map: BTreeMap<String, String> = serde_json::from_str(&data)?;
    Ok(map)
}
```

### 3.4. Tworzenie metod `insert`, `get` i `delete`

Przykładowa implementacja metod do zarządzania danymi w bazie:
```rust
impl Database {
    fn insert(&mut self, key: String, value: String) {
        self.data.insert(key, value);
    }

    fn get(&self, key: &str) -> Option<&String> {
        self.data.get(key)
    }

    fn delete(&mut self, key: &str) {
        self.data.remove(key);
    }
}
```

---

# Dodatkowe Zasoby

- **Future, Waker, and Executors**: [https://rust-lang.github.io/async-book/](https://rust-lang.github.io/async-book/)
- **Rust Memory Management**: [https://doc.rust-lang.org/nomicon/](https://doc.rust-lang.org/nomicon/)
- **Serde JSON**: [https://docs.rs/serde_json/](https://docs.rs/serde_json/)