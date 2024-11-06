
# Zadania z Ownership i Borrowing dla Zaawansowanych

## 1. Bezpieczny dostęp do współdzielonych danych (Mutex i Arc)
Stwórz strukturę `Counter`, która będzie inkrementować licznik z różnych wątków. Skorzystaj z `Arc<Mutex<Counter>>` do synchronizacji dostępu do współdzielonego licznika między wątkami.

### Wymagania:
- Zaimplementuj metodę `increment`, która zwiększa licznik o 1.
- Użyj `Arc` do dzielenia struktury `Counter` między wątki i `Mutex`, aby zapobiec jednoczesnemu dostępowi.
- Uruchom wiele wątków i zweryfikuj, czy wynik końcowy jest poprawny.

---

## 2. Składnik zarządzania buforem cyklicznym
Zaprojektuj strukturę `CircularBuffer`, która pozwala na bezpieczne zapisywanie i odczytywanie danych w buforze cyklicznym. Bufor powinien mieć ograniczoną pojemność i nadpisywać najstarsze dane po osiągnięciu limitu.

### Wymagania:
- Struktura powinna przechowywać dane w wektorze i mieć maksymalny rozmiar.
- Dodaj mechanizm przesuwania wskaźnika do zapisu, aby nadpisywać najstarsze dane.
- Użyj `&mut self` przy zapisie, aby obsłużyć zmianę danych bez przeniesienia własności.

---

## 3. Funkcja zarządzania danymi za pomocą `Cow` (Copy on Write)
Zaimplementuj funkcję `process_data`, która przyjmuje referencję do `str` i używa `Cow<str>` do stworzenia zmodyfikowanej wersji tekstu tylko wtedy, gdy jest to konieczne.

### Wymagania:
- Skorzystaj z `Cow`, aby uniknąć kopiowania danych, gdy nie jest to potrzebne.
- Funkcja powinna sprawdzić, czy tekst wymaga modyfikacji i odpowiednio utworzyć kopię lub użyć oryginału.
- Użyj `to_mut`, aby uzyskać mutowalną wersję, gdy konieczna jest zmiana.
