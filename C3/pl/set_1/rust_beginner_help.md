
# Pomoc do Zadań Początkujących (Ownership i Borrowing w Rust)

## Podstawy `Ownership`
W Rust każda wartość ma swojego właściciela, a kiedy właściciel wychodzi poza zakres, wartość zostaje zwolniona z pamięci.

### Wskazówka:
- Każda wartość w Rust może mieć tylko jednego właściciela w danym momencie.
- Po przeniesieniu (`move`) wartość nie jest już dostępna w poprzednim miejscu.

---

## `Borrowing` i Referencje
Aby uzyskać dostęp do wartości bez przeniesienia własności, użyj referencji (`&`). Dzięki temu możesz pożyczyć wartość na chwilę bez przejmowania jej własności.

### Wskazówka:
- Używaj `&` do tworzenia referencji, które pożyczają wartość.
- Aby zmodyfikować pożyczoną wartość, użyj `&mut` dla referencji zmiennej.

---

## Przechodzenie Własności i Funkcje
Rust przenosi własność wartości, kiedy przekazujesz je do funkcji, chyba że używasz referencji.

### Wskazówka:
- Przekazując `&` do funkcji, pożyczasz wartość, zachowując oryginalną własność.
- Po zakończeniu funkcji referencje są automatycznie zwalniane.

---

## Problemy z `Borrow Checker`
Rust nie pozwala mieć dwóch jednoczesnych mutowalnych referencji, co zapobiega ryzyku błędów wyścigowych.

### Wskazówka:
- Możesz mieć wiele niezmiennych referencji lub jedną mutowalną w jednym czasie.
- Używaj `Borrow Checker` do zarządzania dostępem i unikania błędów w czasie kompilacji.
