
# Zadania dla Początkujących - Obsługa Błędów

## Sekcja Pomocy

### Podstawowa obsługa błędów przy użyciu `Result` i `Option`
- Rust wykorzystuje typy `Result` i `Option` do obsługi błędów i braku wartości. `Result` wskazuje na operacje, które mogą zakończyć się błędem, zawierając `Ok(T)` dla sukcesu lub `Err(E)` dla błędów.
- **Wskazówka**: Używaj `match` do obsługi obu przypadków `Ok` i `Err` w czytelny sposób.

### Obsługa typowych błędów za pomocą `unwrap` i `expect`
- `unwrap()` i `expect()` mogą uprościć obsługę błędów, ale należy ich używać ostrożnie; wywołują panic, jeśli wystąpi błąd.
- **Wskazówka**: `expect("wiadomość")` pozwala na podanie własnej wiadomości w przypadku wystąpienia błędu.

### Propagowanie błędów za pomocą `?`
- Operator `?` upraszcza propagację błędów w funkcjach zwracających `Result`, zatrzymując wykonanie i zwracając `Err`, jeśli napotka błąd.
- **Wskazówka**: Używaj `?` tylko w funkcjach, które zwracają `Result` lub `Option`.

## Zadania

1. **Obsługa błędów przy użyciu `Result`**
   - Napisz funkcję, która dzieli dwie liczby, zwracając `Result<f32, String>`. Jeśli dzielnik jest zerem, zwróć komunikat o błędzie jako `Err`.
   - **Wymagania**: Zdefiniuj `divide_numbers` z typem `Result`. Obsłuż zarówno przypadki sukcesu, jak i błędu przy użyciu `match`.

2. **Użycie `unwrap` i `expect`**
   - Stwórz funkcję, która próbuje przekonwertować ciąg znaków na liczbę całkowitą. Użyj `unwrap` lub `expect` do obsługi przypadków, gdy ciąg jest nieprawidłowy.
   - **Wymagania**: Zdefiniuj `parse_integer` używając `expect` dla lepszej informacji diagnostycznej w przypadku błędu.

3. **Propagowanie błędów za pomocą `?`**
   - Zaimplementuj funkcję, która odczytuje zawartość pliku i zwraca ją jako `String`. Użyj operatora `?` do obsługi błędów.
   - **Wymagania**: Zdefiniuj `read_file`, używając `?` do propagowania błędów podczas odczytu pliku.
