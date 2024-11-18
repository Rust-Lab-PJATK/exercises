# Zadania dla Początkujących - Typy Generyczne, Cecha (Traits) i Czas Życia (Lifetimes)

## Sekcja Pomocy

### Typy Generyczne
- Rust pozwala na tworzenie funkcji i struktur, które mogą działać z różnymi typami danych przy użyciu parametrów generycznych. Na przykład `fn max<T>(a: T, b: T) -> T`, gdzie `T` to typ generyczny.
- **Wskazówka**: Używaj `<T>` w definicji funkcji lub struktury, aby wskazać typ generyczny.

### Cecha (Traits)
- Cecha w Rust definiuje zestaw funkcjonalności, które typy mogą implementować. Na przykład, cecha `Display` pozwala na dostosowanie formatu wyświetlania.
- **Wskazówka**: Używaj `impl TraitName for Type` do implementacji cechy dla konkretnego typu.

### Czas Życia (Lifetimes)
- Wskaźniki czasów życia zapobiegają problemom z pamięcią, pomagając Rustowi zrozumieć, jak długo odniesienia są ważne.
- **Wskazówka**: Wskaźniki czasu życia są oznaczone jako `'a` i często są używane w funkcjach i strukturach z referencjami.

## Zadania

1. **Funkcja z Typem Generycznym**
    - Napisz funkcję `compare_values`, która przyjmuje dwa parametry generyczne `T` i zwraca większą wartość. Użyj cechy `PartialOrd` dla `T`, aby umożliwić porównywanie.
    - **Wymagania**: Zdefiniuj `compare_values<T: PartialOrd>(a: T, b: T) -> T`.

2. **Prosta Implementacja Cecha**
    - Zaimplementuj własną cechę `Printable` z funkcją `print_info`. Stwórz strukturę `Person`, a następnie implementuj `Printable` dla `Person`.
    - **Wymagania**: Zdefiniuj `trait Printable` z metodą `print_info` i zaimplementuj ją dla struktury `Person`.

3. **Czas Życia w Funkcjach**
    - Stwórz funkcję `longest_str`, która przyjmuje dwie referencje do `str` i zwraca dłuższy ciąg znaków. Dodaj odpowiednie oznaczenia czasu życia.
    - **Wymagania**: Zdefiniuj `longest_str<'a>(a: &'a str, b: &'a str) -> &'a str`.
