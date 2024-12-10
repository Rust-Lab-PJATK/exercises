# Zadania dla Średniozaawansowanych - Projekt I/O: Tworzenie Programu w Wierszu Poleceń

## Sekcja Pomocy

### Parsowanie Argumentów z `std::env::args`
- Aby poprawnie obsługiwać wiele argumentów, warto pobrać i sprawdzić ich liczbę, zanim przejdziemy do przetwarzania danych.
- **Wskazówka**: Można użyć `args().collect::<Vec<String>>()`, aby zamienić iterator na wektor argumentów.

### Buforowane Czytanie i Zapis
- `std::io::BufReader` i `std::io::BufWriter` są użyteczne do buforowanego czytania i zapisu, co poprawia wydajność przy pracy z większymi plikami.
- **Wskazówka**: Użyj `BufReader::new(file)` do buforowanego czytania z pliku i `BufWriter::new(file)` do buforowanego zapisu.

## Zadania

1. **Program w Wierszu Poleceń: Znajdź i Zastąp**
    - Stwórz program, który przyjmuje nazwę pliku, wyszukiwany tekst oraz tekst do zastąpienia. Program wczytuje plik, zamienia wszystkie wystąpienia wyszukiwanego tekstu na tekst zastępczy i zapisuje wynik w pliku.
    - **Wymagania**: Użyj `std::fs::read_to_string` do wczytania pliku, `str::replace` do zamiany i `std::fs::write` do zapisania wyników.

2. **Buforowane Czytanie i Zapis z `BufReader` i `BufWriter`**
    - Rozbuduj program, aby używał `BufReader` do wczytywania dużych plików linia po linii oraz `BufWriter` do zapisywania zmodyfikowanych danych.
    - **Wymagania**: Użyj `BufReader::new` i `BufWriter::new` dla odpowiednich operacji oraz metody `writeln!` do zapisu każdej linii.

3. **Opcjonalny Drugi Argument: Tworzenie Kopii Zmodyfikowanego Pliku**
    - Dodaj funkcjonalność opcjonalnego trzeciego argumentu, który określa, czy program powinien zapisać wynik do nowego pliku (np. `output.txt`). Jeśli nie podano trzeciego argumentu, nadpisz oryginalny plik.
    - **Wymagania**: Użyj `std::env::args` do sprawdzenia liczby argumentów i określ, czy zapisać wynik do nowego pliku czy nadpisać istniejący.
