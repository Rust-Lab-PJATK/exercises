# Zadania dla Średniozaawansowanych - Inteligentne Wskaźniki (Smart Pointers)

## Sekcja Pomocy

### Podstawy `RefCell<T>`
- `RefCell` to inteligentny wskaźnik, który pozwala na mutowalny dostęp do danych nawet w kontekście niemutowalnym, ale wymusza sprawdzanie mutowalności w czasie wykonywania.
- **Wskazówka**: Użyj `borrow()` dla dostępu niemutowalnego i `borrow_mut()` dla dostępu mutowalnego.

### Łączenie `Rc<T>` z `RefCell<T>`
- Często `Rc` jest używany z `RefCell`, aby umożliwić współdzielony, mutowalny dostęp do danych między różnymi częściami programu.
- **Wskazówka**: Użyj `Rc<RefCell<T>>`, aby utworzyć wskaźnik współdzielony z możliwością mutacji.

## Zadania

1. **Używanie `RefCell` do Mutacji w Kontekście Niemutowalnym**
    - Stwórz `RefCell<i32>` przechowujący wartość `5`, a następnie zmodyfikuj tę wartość do `10` przy użyciu `borrow_mut`.
    - **Wymagania**: Użyj `borrow_mut()` do zmiany wartości i `borrow()` do odczytu wartości.

2. **Tworzenie Współdzielonej Zmiennej za Pomocą `Rc<RefCell<T>>`**
    - Stwórz `Rc<RefCell<String>>` przechowujący napis `"Hello"`. Utwórz dwie referencje do tej zmiennej i zmodyfikuj zawartość przez jedną z nich.
    - **Wymagania**: Użyj `Rc::clone` do utworzenia referencji i `borrow_mut()` do zmiany zawartości.

3. **Liczenie Odwiedzin za Pomocą `Rc<RefCell<i32>>`**
    - Utwórz `Rc<RefCell<i32>>` do liczenia odwiedzin strony. Stwórz trzy referencje do zmiennej i zwiększ wartość odwiedzin przez każdą z nich.
    - **Wymagania**: Użyj `borrow_mut()` do modyfikacji wartości i `borrow()` do odczytu końcowej wartości.
