
# Wprowadzenie do Rusta

## 1. Instalacja Rusta

Aby rozpocząć pracę z Rustem, musisz go zainstalować. Najłatwiejszym sposobem jest użycie `rustup`:

1. Przejdź na stronę [https://rust-lang.org](https://www.rust-lang.org/) i kliknij "Get Started".
2. Skopiuj polecenie instalacyjne i uruchom je w terminalu:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
3. Postępuj zgodnie z instrukcjami wyświetlanymi w terminalu.

Po zakończeniu instalacji możesz sprawdzić, czy wszystko działa, wpisując:
```bash
rustc --version
```

To polecenie powinno wyświetlić zainstalowaną wersję Rusta.

## 2. Tworzenie pierwszego projektu

1. W terminalu wpisz:
   ```bash
   cargo new nazwa_projektu
   ```
   Zamiast `nazwa_projektu` podaj nazwę swojego projektu.
2. Wejdź do katalogu z projektem:
   ```bash
   cd nazwa_projektu
   ```
3. Uruchom projekt:
   ```bash
   cargo run
   ```

`cargo` to narzędzie do zarządzania projektami w Rust. Po uruchomieniu powinieneś zobaczyć komunikat "Hello, world!".

---

# Materiały Pomocnicze do Zadań

## Zadanie 1: Kalkulator Podstawowych Operacji

### 1.1. Praca z Wejściem i Wyjściem (`std::io`)

Aby wczytać dane od użytkownika, w Rust korzystamy z modułu `std::io`. Przykładowy sposób wczytywania danych:

```rust
use std::io;

fn main() {
    let mut input = String::new(); // Tworzymy nowy, pusty `String`
    io::stdin()
        .read_line(&mut input) // Czytamy linię od użytkownika
        .expect("Nie udało się odczytać linii");

    println!("Wprowadziłeś: {}", input.trim()); // Wyświetlamy dane
}
```

**Wyjaśnienie:**
- `let mut input = String::new();` tworzy zmienną, do której wczytamy dane.
- `io::stdin().read_line()` pozwala wczytać linię tekstu.
- `input.trim()` usuwa białe znaki (np. znak nowej linii).

### 1.2. Parsowanie Liczb

Wczytane dane są typu `String`, więc musimy je przekonwertować na liczby:
```rust
let number: i32 = input.trim().parse().expect("Proszę wprowadzić liczbę");
```

### 1.3. Podstawowe Operacje Matematyczne

W Rust operacje matematyczne wyglądają tak samo, jak w większości języków:
- Dodawanie: `a + b`
- Odejmowanie: `a - b`
- Mnożenie: `a * b`
- Dzielenie: `a / b`

Przykładowa funkcja:
```rust
fn dodaj(a: i32, b: i32) -> i32 {
    a + b
}
```

---

## Zadanie 2: Konwerter Temperatury

### 2.1. Tworzenie Funkcji

Funkcje w Rust mają prostą składnię:
```rust
fn nazwa_funkcji(argument: typ) -> typ_zwrotny {
    // kod funkcji
}
```

Przykład konwersji z Celsjusza na Fahrenheita:
```rust
fn celsius_to_fahrenheit(c: f64) -> f64 {
    c * 9.0 / 5.0 + 32.0
}
```

### 2.2. Wybór Warunkowy (`if`)

Rust umożliwia podejmowanie decyzji za pomocą instrukcji `if`:
```rust
if warunek {
    // kod, jeśli warunek jest spełniony
} else {
    // kod, jeśli warunek nie jest spełniony
}
```

Przykład wyboru konwersji:
```rust
let konwersja = String::from("F");

if konwersja == "F" {
    // konwersja na Fahrenheita
} else {
    // konwersja na Celsjusza
}
```

---

## Zadanie 3: Gra w Zgadywanie Liczby

### 3.1. Losowanie Liczb z `rand`

Aby używać `rand`, dodajemy tę bibliotekę do `Cargo.toml`:
```toml
[dependencies]
rand = "0.8"
```

Następnie importujemy ją w kodzie:
```rust
use rand::Rng;

fn main() {
    let secret_number = rand::thread_rng().gen_range(1..=100);
    println!("Wylosowana liczba to: {}", secret_number);
}
```

### 3.2. Pętle (`loop`)

Pętla `loop` pozwala na wykonywanie kodu w nieskończoność, dopóki nie zostanie przerwana:
```rust
loop {
    // jakiś kod do robienia, w kółko, może i w nieskończoność
}
```

Przykład:
```rust
loop {
    println!("Wprowadź liczbę:");
    let mut guess = String::new();
    io::stdin().read_line(&mut guess).expect("Błąd wczytywania");

    let guess: u32 = guess.trim().parse().expect("Proszę podać liczbę");

    if guess < secret_number {
        println!("Za mało!");
    } else if guess > secret_number {
        println!("Za dużo!");
    } else {
        println!("Gratulacje! Zgadłeś.");
        break; // <- wychodzimy z pętli
    }
}
```

**Wyjaśnienie:**
- `loop` powtarza blok kodu, dopóki nie zostanie użyte `break`.
- `if` pozwala na sprawdzenie warunku i wykonanie różnych działań w zależności od wyniku.

---

# Dodatkowe Zasoby

- **Oficjalna dokumentacja**: [https://doc.rust-lang.org/book/](https://doc.rust-lang.org/book/)
- **Rust by Example**: [https://doc.rust-lang.org/rust-by-example/](https://doc.rust-lang.org/rust-by-example/)
- **Playground Rusta**: Można testować kod bez instalacji Rusta na [https://play.rust-lang.org/](https://play.rust-lang.org/).