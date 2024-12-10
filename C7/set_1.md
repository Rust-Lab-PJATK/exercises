# Zadania dla Początkujących - Projekt I/O: Tworzenie Programu w Wierszu Poleceń

## Sekcja Pomocy

### Podstawowe Operacje Wejścia/Wyjścia
- W Rust podstawowe operacje I/O można realizować za pomocą modułu `std::io`. Używaj `std::fs` do pracy z plikami i `std::io::{self, Write, Read}` do operacji na wejściu/wyjściu.
- **Wskazówka**: Do czytania plików używaj `std::fs::read_to_string("filename")`, a do zapisu `std::fs::write("filename", data)`.

### Obsługa Argumentów Linii Komend
- Argumenty można pobrać przy użyciu `std::env::args`, który zwraca iterator argumentów wprowadzonych do programu w wierszu poleceń.
- **Wskazówka**: Użyj `std::env::args().nth(index)`, aby uzyskać konkretny argument.

## Zadania

1. **Program w Wierszu Poleceń: Wczytaj Plik**
    - Napisz program, który przyjmuje nazwę pliku jako argument w wierszu poleceń, wczytuje jego zawartość i wyświetla ją w konsoli.
    - **Wymagania**: Użyj `std::env::args` do pobrania argumentu oraz `std::fs::read_to_string` do wczytania zawartości pliku.

2. **Program w Wierszu Poleceń: Zapisz do Pliku**
    - Rozbuduj program, aby zapisywał tekst wprowadzony przez użytkownika do pliku podanego jako drugi argument w wierszu poleceń.
    - **Wymagania**: Użyj `std::env::args` do uzyskania nazwy pliku oraz `std::fs::write` do zapisu tekstu do pliku.

3. **Obsługa Błędów w Programie I/O**
    - Zaimplementuj obsługę błędów dla operacji odczytu i zapisu, wyświetlając komunikat o błędzie, jeśli plik nie zostanie znaleziony lub wystąpi problem z zapisem.
    - **Wymagania**: Użyj `match` lub `unwrap_or_else` do obsługi błędów podczas otwierania lub zapisywania pliku.
