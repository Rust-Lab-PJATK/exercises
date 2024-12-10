# Zadania dla Średniozaawansowanych - Iteratory i Domknięcia

## Sekcja Pomocy

### Łączenie Metod Iteratora
- Rust pozwala na łączenie metod iteratorów, takich jak `map`, `filter`, `enumerate`, itp., co umożliwia bardziej złożone operacje.
- **Wskazówka**: Spróbuj łączyć `map` i `filter` dla efektywniejszego przetwarzania.

### Domknięcia z Wieloma Parametrami
- Domknięcia mogą mieć wiele parametrów, a także dostęp do zmiennych spoza ich zakresu, jeśli są one przechwytywane.
- **Wskazówka**: Domknięcia automatycznie przechwycą zmienne z zakresu, jeśli są potrzebne.

## Zadania

1. **Filtrowanie i Mapowanie z Iteratorem**
    - Napisz funkcję `square_odd_numbers`, która przyjmuje wektor liczb całkowitych i zwraca wektor z kwadratami tylko tych liczb, które są nieparzyste.
    - **Wymagania**: Użyj `filter` do wybrania nieparzystych liczb, a `map` do ich podniesienia do kwadratu.

2. **Numerowanie Elementów z `enumerate`**
    - Napisz funkcję `label_strings`, która przyjmuje wektor napisów i zwraca wektor z każdą pozycją oznaczoną jej indeksem w formie `index: string`.
    - **Wymagania**: Użyj `enumerate` do dodania indeksów, a `map` do formatowania elementów.

3. **Złożone Operacje z Iteratorami**
    - Stwórz funkcję `unique_sorted_squares`, która przyjmuje wektor liczb całkowitych, usuwa duplikaty, przekształca je w wartości kwadratowe, a następnie zwraca posortowany wektor wyników.
    - **Wymagania**: Użyj `map`, `filter`, `collect()` oraz `sort()` na wyniku.
