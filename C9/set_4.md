# Zadania dla Ekspertów - Inteligentne Wskaźniki (Smart Pointers)

## Sekcja Pomocy

### Złożone Zarządzanie Zasobami z `Arc<T>`
- `Arc` (Atomic Reference Counted) to inteligentny wskaźnik umożliwiający współdzielone, wielowątkowe zarządzanie zasobami.
- **Wskazówka**: Użyj `Arc` zamiast `Rc`, jeśli potrzebujesz wskaźników współdzielonych między wątkami.

### Łączenie `Arc<Mutex<T>>` do Synchronizacji
- Rust oferuje `Mutex` do synchronizacji, aby umożliwić bezpieczne współdzielenie danych między wątkami.
- **Wskazówka**: Użyj `Arc<Mutex<T>>`, aby bezpiecznie współdzielić dane między wątkami.

## Zadania

1. **Wielowątkowe Zarządzanie Danymi z `Arc`**
    - Stwórz `Arc<String>` z tekstem `"Hello, Arc!"` i uruchom trzy wąThreadsy, które współdzielą ten zasób. Każdy wątek powinien wyświetlić wartość tekstu.
    - **Wymagania**: Użyj `Arc::clone` do współdzielenia `Arc` między wątkami i `thread::spawn` do utworzenia wątków.

2. **Współdzielony Licznik za Pomocą `Arc<Mutex<i32>>`**
    - Stwórz `Arc<Mutex<i32>>`, inicjalizowany wartością `0`. Uruchom pięć wątków, z których każdy zwiększa wartość licznika o `1`.
    - **Wymagania**: Użyj `lock()` na `Mutex`, aby modyfikować licznik w wątkach i `Arc::clone` do współdzielenia zasobu.

3. **Synchronizacja Dostępu do Struktury za Pomocą `Arc<Mutex<T>>`**
    - Stwórz strukturę `SharedCounter` z licznikiem wewnątrz `Mutex`. Współdziel `Arc<Mutex<SharedCounter>>` między wątkami, aby liczyć, ile razy każdy wątek wykonał zadanie.
    - **Wymagania**: Zaimplementuj metodę zwiększającą licznik i współdziel `Arc<Mutex<SharedCounter>>` między wieloma wątkami.
