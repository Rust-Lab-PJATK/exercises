# Zadania dla Zaawansowanych - Iteratory i Domknięcia

## Sekcja Pomocy

### Domknięcia z Przechwytywaniem Zmiennych przez `move`
- Użycie `move` w domknięciach wymusza przeniesienie przechwyconych zmiennych do zamknięcia, przydatne w przypadku operacji asynchronicznych.
- **Wskazówka**: Dodaj `move` przed definicją domknięcia: `move |x| { ... }`.

## Zadania

1. **Domknięcia z Przechwytywaniem Przez `move`**
    - Napisz funkcję `execute_with_closure`, która przyjmuje liczbę i domknięcie `move`, które mnoży tę liczbę przez wartość przechwyconą z zewnętrznego zakresu.
    - **Wymagania**: Użyj `move` w domknięciu, aby przechwycić zmienną i wykonać mnożenie.

2. **Domknięcia z Operacjami Asynchronicznymi**
    - Napisz funkcję `async_filter`, która przyjmuje wektor oraz domknięcie i zwraca wektor tylko tych elementów, które spełniają warunek w domknięciu asynchronicznym.
    - **Wymagania**: Użyj `async` i `await` w domknięciu, aby filtrować elementy w sposób asynchroniczny.
