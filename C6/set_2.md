# Zadania dla Średniozaawansowanych - Pisanie Testów Automatycznych

## Sekcja Pomocy

### Testowanie z Obsługą Błędów
- W Rust możesz testować funkcje zwracające `Result` przez porównanie `Ok` i `Err` za pomocą `assert_eq!`.
- **Wskazówka**: Użyj `unwrap` lub `expect`, aby przetestować funkcje zwracające `Result`.

### Używanie `#[should_panic]`
- Użyj atrybutu `#[should_panic]` nad funkcjami testowymi, aby sprawdzić, czy funkcja rzeczywiście wywołuje panic w odpowiednich sytuacjach.
- **Wskazówka**: Dodaj opcję `expected` w `#[should_panic(expected = "message")]` dla lepszej kontroli.

## Zadania

1. **Testowanie Funkcji z `Result`**
    - Napisz funkcję `sqrt(number: f64) -> Result<f64, String>`, która zwraca pierwiastek liczby, ale zwraca błąd, jeśli liczba jest ujemna. Przetestuj różne przypadki za pomocą `assert_eq!`.
    - **Wymagania**: Napisz testy sprawdzające wynik `Ok` dla liczb nieujemnych oraz `Err` dla liczb ujemnych.

2. **Testowanie Funkcji z `#[should_panic]`**
    - Zaimplementuj funkcję `get_element(vec: Vec<i32>, index: usize) -> i32`, która wywołuje panic, jeśli `index` jest poza zakresem. Przetestuj ją, używając `#[should_panic]`.
    - **Wymagania**: Napisz testy, które sprawdzają działanie funkcji dla poprawnych i niepoprawnych indeksów, aby wywołać panic.

3. **Mockowanie Prostych Funkcji**
    - Napisz funkcję `fetch_data`, która symuluje pobieranie danych z API. Stwórz wersję mock tej funkcji i przetestuj ją, aby upewnić się, że zwraca poprawne wyniki.
    - **Wymagania**: Napisz test, który używa zastępczej wersji `fetch_data`, aby przetestować różne przypadki.
