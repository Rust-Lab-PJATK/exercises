# Zadania dla Zaawansowanych - Pisanie Testów Automatycznych

## Sekcja Pomocy

### Testowanie Asynchroniczne
- Rust obsługuje testy asynchroniczne przy użyciu `async` i `#[tokio::test]` (jeśli korzystasz z Tokio) lub innych executorów.
- **Wskazówka**: W Rust używaj `#[tokio::test]` do testów asynchronicznych w Tokio lub `#[async_std::test]` z async-std.

### Testowanie Współbieżne
- Testowanie współbieżne w Rust może być wyzwaniem ze względu na jednoczesny dostęp do danych. Rozważ użycie `Mutex` i `Arc`, aby zsynchronizować dostęp.
- **Wskazówka**: Używaj `Arc<Mutex<T>>` dla współdzielonych danych w testach wielowątkowych.

## Zadania

1. **Testowanie Funkcji Asynchronicznej**
    - Napisz funkcję asynchroniczną `async_fetch(url: &str) -> Result<String, String>`, która symuluje pobieranie danych z URL. Przetestuj ją, używając `#[tokio::test]`.
    - **Wymagania**: Napisz test, który sprawdza, czy `async_fetch` zwraca poprawne wyniki, oraz przypadek błędu, np. dla niepoprawnego URL.

2. **Testowanie Funkcji Wielowątkowej**
    - Zaimplementuj licznik `Counter`, który może być inkrementowany przez wiele wątków. Użyj `Arc<Mutex<Counter>>`, aby zsynchronizować dostęp w testach.
    - **Wymagania**: Stwórz test, który uruchamia wiele wątków jednocześnie i sprawdza, czy końcowa wartość licznika jest poprawna.

3. **Zaawansowane Mockowanie**
    - Napisz funkcję `api_request` do wykonywania żądań HTTP, a następnie przetestuj ją, korzystając z mock serwera HTTP (np. `httpmock`).
    - **Wymagania**: Stwórz test, który mockuje odpowiedzi API i sprawdza, czy `api_request` zwraca poprawne dane w różnych scenariuszach.
