# Zadania dla Ekspertów - Iteratory i Domknięcia

## Sekcja Pomocy

### Iterator Zagnieżdżony
- Rust pozwala na tworzenie iteratorów zwracających inne iteratory, co umożliwia konstrukcję złożonych struktur.
- **Wskazówka**: Twórz iteratory w pętli `for` lub przy użyciu `flat_map`.

### Zaawansowane Domknięcia w Funkcjach Wysokiego Rzędu
- Rust obsługuje funkcje wysokiego rzędu przyjmujące domknięcia jako argumenty i zwracające domknięcia, co umożliwia dynamiczne generowanie funkcji.
- **Wskazówka**: Wskaż typy domknięć za pomocą `impl Fn`.

## Zadania

1. **Niestandardowy Zagnieżdżony Iterator**
    - Zaimplementuj strukturę `Matrix` do iteracji po wartościach 2D, która zwraca iterator dla każdej kolumny w wierszu.
    - **Wymagania**: Zdefiniuj `Iterator` dla `Matrix`, który zwraca zagnieżdżone iteratory.

2. **Dynamiczne Tworzenie Funkcji z Domknięciem**
    - Stwórz funkcję `create_multiplier`, która przyjmuje liczbę i zwraca domknięcie mnożące każdy argument przez tę liczbę.
    - **Wymagania**: Zwracaj `impl Fn(i32) -> i32`, aby zwrócić domknięcie, które będzie działało jak funkcja.

3. **Iterator z Niestandardową Funkcją Przekształcającą**
    - Napisz funkcję `transform_iterator` przyjmującą iterator i domknięcie, które przekształca każdy element, a następnie zwraca nowy iterator z wynikami.
    - **Wymagania**: Użyj `impl Iterator` jako zwracany typ, aby zwrócić iterator z zastosowaną transformacją.
