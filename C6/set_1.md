# Zadania dla Początkujących - Pisanie Testów Automatycznych

## Sekcja Pomocy

### Podstawowe Testy Jednostkowe
- Rust pozwala na pisanie testów jednostkowych za pomocą modułu `#[cfg(test)]` i atrybutu `#[test]` nad funkcjami testowymi.
- **Wskazówka**: Umieść testy w bloku `#[cfg(test)] mod tests { ... }`.

### Assercje
- Używaj `assert_eq!` i `assert_ne!` do porównywania wartości w testach. `assert_eq!(a, b)` sprawdza, czy `a` jest równe `b`.
- **Wskazówka**: Używaj `assert!(condition)` dla sprawdzenia warunków logicznych.

## Zadania

1. **Testowanie Funkcji Dodawania**
    - Napisz prostą funkcję `add(a: i32, b: i32) -> i32` i przetestuj ją, aby upewnić się, że zwraca poprawny wynik dla różnych wartości.
    - **Wymagania**: Napisz test, który używa `assert_eq!`, aby porównać wynik `add` z oczekiwanym rezultatem.

2. **Sprawdzanie Wyników z `assert!`**
    - Napisz funkcję `is_positive(n: i32) -> bool`, która zwraca `true`, jeśli liczba jest dodatnia. Przetestuj funkcję przy użyciu `assert!`.
    - **Wymagania**: Napisz testy sprawdzające różne przypadki, w tym liczby dodatnie, ujemne i zero.

3. **Testowanie Funkcji z Warunkami**
    - Napisz funkcję `divide(a: i32, b: i32) -> Option<i32>`, która zwraca wynik dzielenia, ale zwraca `None`, jeśli `b` wynosi 0. Dodaj testy dla przypadków z wartością `Some` i `None`.
    - **Wymagania**: Użyj `assert_eq!` do porównania wyników z oczekiwanymi wartościami `Some` i `None`.
