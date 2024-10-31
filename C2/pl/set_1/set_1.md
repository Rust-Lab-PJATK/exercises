
# Zadania z Rusta dla Początkujących (Zestaw 1)

## 1. Prosta struktura `Book` z metodą
Napisz strukturę `Book`, która przechowuje tytuł oraz autora książki jako `String`. Dodaj metodę, która wypisze pełny opis książki w formacie: "Tytuł: [tytuł], Autor: [autor]".

### Wymagania:
- Zaimplementuj strukturę `Book` z polami `title` i `author`.
- Dodaj metodę `describe()`, która wypisuje opis książki.

### Przykład:
```rust
let book = Book { title: String::from("Hobbit"), author: String::from("J.R.R. Tolkien") };
book.describe(); // Wynik: Tytuł: Hobbit, Autor: J.R.R. Tolkien
```

---

## 2. Operacje na `Option`
Napisz funkcję `find_element`, która przyjmuje wektor liczb całkowitych i wartość do znalezienia. Funkcja powinna zwracać `Option<usize>`, gdzie `Some(index)` oznacza pozycję, na której znaleziono wartość, a `None` oznacza, że wartość nie została znaleziona.

### Wymagania:
- Użyj `Option` do obsługi przypadku, w którym wartość nie jest obecna w wektorze.
- Przetestuj działanie funkcji, zwracając pozycję elementu lub komunikat "Nie znaleziono".

### Przykład:
```rust
let vec = vec![1, 2, 3, 4, 5];
let result = find_element(&vec, 3);
println!("{:?}", result); // Wynik: Some(2)
```

---

## 3. Proste `Result` do dzielenia liczb
Napisz funkcję `divide`, która przyjmuje dwie liczby całkowite i zwraca wynik jako `Result<f64, String>`. Jeśli druga liczba wynosi 0, funkcja powinna zwrócić błąd z komunikatem "Błąd: dzielenie przez zero".

### Wymagania:
- Użyj `Result` do obsługi błędu dzielenia przez zero.
- Zwróć wynik dzielenia lub komunikat o błędzie.

### Przykład:
```rust
let result = divide(10, 2);
println!("{:?}", result); // Wynik: Ok(5.0)
```

---

## 4. Proste operacje plikowe
Napisz program, który tworzy plik o nazwie `output.txt` i zapisuje w nim tekst "Witaj, Rust!". Następnie otwórz plik i wyświetl jego zawartość na ekranie.

### Wymagania:
- Użyj `std::fs::File` oraz `write!` do zapisu danych do pliku.
- Wczytaj dane z pliku i wyświetl je na ekranie.

### Przykład:
```rust
write_to_file("output.txt", "Witaj, Rust!");
read_from_file("output.txt"); // Wynik: Witaj, Rust!
```

---
