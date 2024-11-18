# Zadania dla Średniozaawansowanych - Typy Generyczne, Cecha (Traits) i Czas Życia (Lifetimes)

## Sekcja Pomocy

### Zaawansowane Typy Generyczne i Cecha
- Rust pozwala na tworzenie bardziej skomplikowanych typów generycznych z wieloma ograniczeniami cech, co daje większą elastyczność przy jednoczesnym zapewnieniu bezpieczeństwa.
- **Wskazówka**: Używaj `T: Trait1 + Trait2`, aby wymusić wielokrotne ograniczenia na typach generycznych.

### Cecha z Parametrem Generycznym
- Cecha może również przyjmować typy generyczne, co umożliwia implementację tej samej cechy dla różnych typów.
- **Wskazówka**: Używaj `trait TraitName<T>` do tworzenia cechy z typem generycznym jako parametrem.

### Czas Życia w Strukturach
- Kiedy struktura zawiera referencje, konieczne jest oznaczenie czasów życia dla jej pól.
- **Wskazówka**: Używaj `struct StructName<'a> { ... }` do oznaczenia czasów życia w strukturach.

## Zadania

1. **Struktura z Generycznym Typem i Ograniczeniami Cecha**
    - Stwórz strukturę `Container`, która przechowuje dwa elementy tego samego typu generycznego `T`, gdzie `T` implementuje `PartialOrd` i `Copy`. Dodaj metodę `max`, która zwraca większą wartość.
    - **Wymagania**: Zdefiniuj `struct Container<T: PartialOrd + Copy> { ... }` oraz metodę `fn max(&self) -> T`.

2. **Cecha z Typem Generycznym**
    - Zdefiniuj cechę `Summable<T>`, która zawiera funkcję `sum`. Zaimplementuj tę cechę dla wektorów liczb całkowitych `Vec<i32>` i `Vec<f64>`, aby zwrócić ich sumę.
    - **Wymagania**: Zdefiniuj `trait Summable<T>` i zaimplementuj `sum` dla `Vec<i32>` oraz `Vec<f64>`.

3. **Struktura z Czasem Życia**
    - Zaimplementuj strukturę `Text<'a>`, która zawiera referencję do `str` oraz zmienną liczbową `count`. Dodaj metodę `increment`, która zwiększa `count`.
    - **Wymagania**: Zdefiniuj `struct Text<'a>`, uwzględniając czas życia `'a`, oraz metodę `fn increment(&mut self)`.
