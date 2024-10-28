
# Pomoc do Zadań Początkujących (Rust Beginner Help)

## Struktura `Book` i Metoda `describe`
Struktura (`struct`) w Rust pozwala przechowywać powiązane dane. Możesz dodać metodę do struktury przy użyciu `impl`.

### Wskazówka:
- Zdefiniuj strukturę `Book` z polami typu `String`, np. `title` i `author`.
- Dodaj funkcję, która wyświetli informacje o książce.
- Użyj `&self` w metodzie, aby uzyskać dostęp do pól struktury.

---

## Obsługa Opcji z `Option`
`Option` to typ używany do reprezentowania wartości, które mogą lub nie mogą być obecne. `Some(value)` oznacza, że wartość istnieje, a `None` oznacza jej brak.

### Wskazówka:
- Przejrzyj wektor elementów i porównuj każdy z nich z szukaną wartością.
- Jeśli znajdziesz szukaną wartość, zwróć jej indeks jako `Some(index)`.
- Jeśli nie znajdziesz wartości, zwróć `None`.

---

## Obsługa Błędów z `Result`
`Result` jest używany do obsługi błędów i zawiera warianty `Ok` (wynik) oraz `Err` (błąd). Możesz użyć `match`, aby rozróżnić te warianty.

### Wskazówka:
- Funkcja może zwracać `Err`, gdy dochodzi do błędu, np. dzielenia przez zero.
- Użyj `match`, aby sprawdzić wynik i zwrócić poprawny wynik lub komunikat błędu.

---

## Podstawy Operacji Plikowych
Rust oferuje `std::fs::File` oraz `std::io` do obsługi plików. `write!` pozwala na zapis do pliku, a `read_to_string` na odczyt danych.

### Wskazówka:
- Użyj `File::create` do stworzenia nowego pliku i `write!` do zapisu tekstu.
- Użyj `File::open` do odczytu pliku i `read_to_string`, aby załadować jego zawartość do `String`.

---