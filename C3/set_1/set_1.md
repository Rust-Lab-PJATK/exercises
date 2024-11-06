
# Zadania z Ownership i Borrowing dla Początkujących

## 1. Przeniesienie Własności
Napisz funkcję, która przyjmuje `String`, przenosi jego własność i wyświetla jego zawartość. Spróbuj wywołać tę funkcję dwa razy z tą samą wartością i zauważ wynik.

### Wymagania:
- Zdefiniuj funkcję `show_ownership`, która przyjmuje `String`.
- Sprawdź, co się stanie, gdy spróbujesz użyć zmiennej po przeniesieniu.

---

## 2. Pożyczanie Wartości z `Borrowing`
Napisz funkcję, która przyjmuje referencję do `String` i wyświetla jej zawartość bez przenoszenia własności.

### Wymagania:
- Zdefiniuj funkcję `show_borrowed`, która przyjmuje `&String`.
- Wywołaj tę funkcję kilkukrotnie, używając tej samej zmiennej.

---

## 3. Przechodzenie Własności i Mutowalne Pożyczanie
Napisz funkcję `append_exclamation`, która przyjmuje mutowalną referencję do `String` i dodaje wykrzyknik na końcu tekstu.

### Wymagania:
- Zdefiniuj funkcję, która przyjmuje `&mut String` i modyfikuje jej zawartość.
- Sprawdź, co się stanie, gdy jednocześnie spróbujesz użyć innej mutowalnej referencji.
