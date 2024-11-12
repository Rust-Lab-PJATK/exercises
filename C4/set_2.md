# Zadania dla Średniozaawansowanych - Obsługa Błędów

## Sekcja Pomocy

### Tworzenie Własnych Typów Błędów
- Rust pozwala na tworzenie własnych typów błędów, aby reprezentować specyficzne problemy. Implementacja cech `std::fmt::Display` i `std::error::Error` umożliwia ich integrację z bibliotekami do obsługi błędów.
- **Wskazówka**: Używaj makra `derive`, aby uprościć implementację cech, jeśli to możliwe.

### Obsługa błędów za pomocą `thiserror` i `anyhow`
- Biblioteki, takie jak `thiserror` (dla własnych typów błędów) i `anyhow` (dla elastycznej obsługi błędów), mogą zwiększyć czytelność i ułatwić zarządzanie błędami.
- **Wskazówka**: `thiserror` dostarcza przydatne adnotacje dla własnych typów błędów, a makro `anyhow!` z `anyhow` upraszcza tworzenie błędów.

### Konwersja błędów za pomocą `From` i `Into`
- Implementacja `From` pozwala na konwersję błędów na jednolity typ, ułatwiając łączenie i zarządzanie różnymi typami błędów.
- **Wskazówka**: Użyj `derive` dla `From` na własnych błędach lub implementuj ręcznie dla interoperacyjności.

## Zadania

1. **Tworzenie Własnego Typu Błędu**
   - Zaprojektuj typ błędu `MathError`, który obsługuje dwa przypadki: `DivideByZero` i `NegativeSquareRoot`. Zaimplementuj cechy `Display` i `Error`.
   - **Wymagania**: Zdefiniuj `MathError` jako `enum`. Zaimplementuj `Display` dla czytelnych komunikatów i użyj `derive` dla `Error`.

2. **Użycie `thiserror` dla Własnych Błędów**
   - Użyj `thiserror`, aby zdefiniować własny typ błędu dla aplikacji przetwarzającej pliki. Zaimplementuj błędy, takie jak `FileNotFound` i `ParseError`.
   - **Wymagania**: Zdefiniuj `FileProcessingError` przy użyciu `thiserror`, w tym warianty dla typowych błędów związanych z plikami.

3. **Łączenie `anyhow` z Propagacją Błędów**
   - Napisz funkcję, która odczytuje plik i parsuje liczby, używając `anyhow` do elastycznej obsługi błędów i `?` do propagacji.
   - **Wymagania**: Użyj `anyhow` do uproszczenia zwrotu błędów i dodaj szczegółowe komunikaty o błędach.
