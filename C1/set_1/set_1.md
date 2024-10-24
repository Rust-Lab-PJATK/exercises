# Zadania z Rusta dla Początkujących

## 1. Kalkulator Podstawowych Operacji
Napisz program, który wykonuje podstawowe operacje matematyczne:
- dodawanie,
- odejmowanie,
- mnożenie,
- dzielenie.

### Wymagania:
- Program powinien pytać użytkownika o dwie liczby oraz wybór operacji.
- Zaimplementuj każdą operację jako oddzielną funkcję.
- Obsłuż przypadek dzielenia przez zero.

### Przykładowe Wejście/Wyjście:
```
Podaj pierwszą liczbę: 10 
Podaj drugą liczbę: 2 
Wybierz operację (+, -, *, /): / 
Wynik: 5.0
```

## 2. Konwerter Temperatury
Napisz funkcję, która konwertuje temperatury między Celsjuszem a Fahrenheitem.

### Wymagania:
- Program powinien pytać użytkownika, czy chce konwertować z Celsjusza na Fahrenheita czy odwrotnie.
- Do zamiany wykorzystaj poniższe wzory:
    - `F = C * 9/5 + 32`
    - `C = (F - 32) * 5/9`
- Wypisz wynik konwersji.

### Przykładowe Wejście/Wyjście
```
Podaj temperaturę: 100 
Konwertować na (F)ahrenheita czy (C)elsjusza? F 
Wynik: 212 F
```

## 3. Gra w Zgadywanie Liczby
Stwórz grę, w której komputer losuje liczbę od 1 do 100, a użytkownik próbuje ją odgadnąć.

### Wymagania:
- Program powinien informować, czy zgadywana liczba jest za duża, za mała, czy poprawna.
- Wykorzystaj `rand` crate do generowania losowej liczby.
- Użyj pętli `loop`, aby umożliwić użytkownikowi wielokrotne próby.

### Przykładowe Wejście/Wyjście:
```
Zgadnij liczbę (1-100): 50 
Za mało! 
Zgadnij liczbę (1-100): 75 
Za dużo! 
Zgadnij liczbę (1-100): 62 
Gratulacje! Zgadłeś.
```