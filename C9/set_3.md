# Zadania dla Zaawansowanych - Inteligentne Wskaźniki (Smart Pointers)

## Sekcja Pomocy

### `Weak<T>` jako Odwołania Cyklowe
- W celu uniknięcia cyklicznych referencji, które mogą prowadzić do wycieków pamięci, Rust oferuje `Weak`, który jest słabym wskaźnikiem do danych zarządzanych przez `Rc`.
- **Wskazówka**: Użyj `Rc::downgrade` do utworzenia słabego wskaźnika i `weak.upgrade()` do uzyskania `Rc`, jeśli dane są jeszcze dostępne.

### Cykl Refleksyjny za pomocą `Rc<RefCell<T>>` i `Weak`
- `Weak` jest często używany z `Rc<RefCell<T>>` w strukturach drzewiastych, gdzie rodzic i dzieci muszą się wzajemnie przechowywać.
- **Wskazówka**: Używaj `Weak` dla odniesień do rodziców, aby uniknąć cykli.

## Zadania

1. **Tworzenie Słabego Wskaźnika (`Weak`) do Zasobu**
    - Utwórz `Rc<String>`, a następnie stwórz słaby wskaźnik do tego zasobu. Spróbuj uzyskać dostęp do danych przez `Weak` i sprawdź, czy zasób jest dostępny.
    - **Wymagania**: Użyj `Rc::downgrade` do utworzenia `Weak` oraz `upgrade()` do próby uzyskania zasobu.

2. **Struktura Drzewa z `Rc` i `Weak`**
    - Stwórz prostą strukturę drzewa, gdzie każdy `Node` przechowuje `Rc` do dzieci i `Weak` do rodzica. Dodaj funkcję do dodawania dziecka do rodzica.
    - **Wymagania**: Użyj `Rc<RefCell<Node>>` dla dzieci i `Weak<RefCell<Node>>` dla rodzica.

3. **Unikanie Wycieku Pamięci w Cyklach za Pomocą `Weak`**
    - Zaimplementuj przykład, który tworzy cykliczne odniesienia między dwoma strukturami `A` i `B` z użyciem `Rc` i `Weak`. Upewnij się, że nie ma wycieku pamięci.
    - **Wymagania**: Użyj `Rc` dla głównego odniesienia i `Weak` dla cyklicznego, aby uniknąć wycieku.
