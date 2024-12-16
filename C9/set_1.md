# Zadania dla Początkujących - Inteligentne Wskaźniki (Smart Pointers)

## Sekcja Pomocy

### Podstawy `Box<T>`
- `Box` to wskaźnik, który przechowuje dane na stercie (heap) zamiast na stosie (stack). Jest przydatny, gdy chcemy kontrolować, gdzie przechowywane są nasze dane.
- **Wskazówka**: Użyj `Box::new(value)` do stworzenia wskaźnika `Box` z wartością.

### Podstawy `Rc<T>`
- `Rc` (Reference Counted) to inteligentny wskaźnik, który pozwala na współdzielenie danych między różnymi częściami programu. Jest przydatny do danych niemutowalnych.
- **Wskazówka**: Użyj `Rc::clone(&value)` do zwiększenia liczby referencji.

## Zadania

1. **Przechowywanie Danych na Stercie za Pomocą `Box<T>`**
    - Stwórz zmienną typu `Box<i32>`, która przechowuje wartość `10`, i wyświetl tę wartość w konsoli.
    - **Wymagania**: Użyj `Box::new(10)` i `*box_var`, aby odczytać wartość.

2. **Udostępnianie Danych za Pomocą `Rc<T>`**
    - Stwórz zmienną typu `Rc<String>` z wartością `"Hello"`. Utwórz dwie dodatkowe referencje do tej zmiennej i wyświetl liczbę referencji.
    - **Wymagania**: Użyj `Rc::clone` do tworzenia referencji i `Rc::strong_count`, aby sprawdzić liczbę referencji.

3. **Praca z `Rc` i Wektorem**
    - Stwórz `Rc<Vec<i32>>`, zawierający wektor liczb od 1 do 5. Utwórz dodatkową referencję do tego wektora i sprawdź, czy możesz uzyskać dostęp do elementów wektora przez tę referencję.
    - **Wymagania**: Użyj `Rc::clone` oraz `for` do iteracji po elementach.
