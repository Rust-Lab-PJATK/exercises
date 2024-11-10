
# Pomoc do Zadań (Ownership i Borrowing w Rust - Zaawansowane)

## `Arc` i `Mutex` w Wielowątkowości
Kiedy dane są współdzielone między wątkami, muszą być bezpiecznie zarządzane. `Arc` jest liczonym wskaźnikiem, a `Mutex` umożliwia wyłączny dostęp do danych.

### Wskazówka:
- `Arc` zapewnia bezpieczny dostęp przez wiele wątków dzięki licznikowi referencji.
- `Mutex` blokuje dane, aby tylko jeden wątek mógł je modyfikować w danym momencie.

---

## Bufor Cykliczny (Circular Buffer)
Bufor cykliczny to struktura, która efektywnie zarządza danymi o stałym rozmiarze, nadpisując najstarsze elementy, gdy bufor jest pełny.

### Wskazówka:
- Wskaźnik do zapisu powinien być przesuwany za każdym razem, gdy dodawany jest nowy element.
- Nadpisywanie najstarszych danych wymaga utrzymywania indeksu początkowego.

---

## Optymalizacja Pamięci z `Cow`
`Cow` (Copy on Write) pozwala na uniknięcie kopiowania danych, jeśli nie są one modyfikowane. `Cow` używa oryginału, dopóki nie potrzebuje mutowalnej wersji.

### Wskazówka:
- `Cow::Borrowed` utrzymuje referencję do danych, dopóki nie zachodzi konieczność zmiany.
- `to_mut` umożliwia przekształcenie `Cow` w mutowalny typ, tworząc kopię tylko w razie potrzeby.
