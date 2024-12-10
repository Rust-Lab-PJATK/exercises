# Zadania dla Początkujących - Iteratory i Domknięcia

## Sekcja Pomocy

### Podstawy Iteratorów
- Iteratory w Rust pozwalają na sekwencyjne przetwarzanie danych w kolekcji. Podstawowe metody iteratorów to `next()` i `collect()`.
- **Wskazówka**: `iter()` tworzy iterator, a `collect()` zbiera elementy w kolekcję.

### Proste Domknięcia (Closures)
- Domknięcia w Rust są podobne do funkcji, ale mają łatwiejszą składnię i mogą przechwytywać zmienne z ich zakresu. Używaj `|x| x * 2`, aby utworzyć proste domknięcie.
- **Wskazówka**: Domknięcia są zapisywane w formie `|parametry| { wyrażenie }`.

## Zadania

1. **Używanie Iteratora do Sumu Liczb**
    - Napisz funkcję `sum_even_numbers`, która zwraca sumę liczb parzystych z wektora liczb całkowitych.
    - **Wymagania**: Użyj iteratora i metody `filter` do wyboru liczb parzystych, a następnie `sum()` do obliczenia sumy.

2. **Tworzenie Prostej Mapy z Domknięciem**
    - Napisz funkcję `double_values`, która przyjmuje wektor liczb całkowitych i zwraca nowy wektor, w którym każda liczba jest podwojona.
    - **Wymagania**: Użyj `map` z domknięciem `|x| x * 2`, aby utworzyć nowy wektor.

3. **Podstawowe Użycie `collect()`**
    - Napisz funkcję `get_strings_longer_than_three`, która przyjmuje wektor napisów i zwraca nowy wektor z napisami dłuższymi niż trzy znaki.
    - **Wymagania**: Użyj `filter` do wybrania odpowiednich napisów i `collect()` do zebrania ich w nowy wektor.
