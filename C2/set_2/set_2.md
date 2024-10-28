
# Zadania z Rusta dla Średnio Zaawansowanych (Zestaw 2)

## 1. Iterator zwracający liczby pierwsze
Napisz strukturę `PrimeNumbers`, która implementuje `Iterator` i generuje liczby pierwsze do określonej wartości `n`.

### Wymagania:
- Zaimplementuj `Iterator` dla `PrimeNumbers`, aby generować kolejne liczby pierwsze.
- Dodaj metodę `is_prime`, która sprawdza, czy dana liczba jest pierwsza.

### Przykład:
```rust
let mut primes = PrimeNumbers::new(20);
while let Some(prime) = primes.next() {
    println!("{}", prime); // Wynik: 2, 3, 5, 7, 11, 13, 17, 19
}
```

---

## 2. System logowania z poziomem szczegółowości
Rozbuduj system logowania, który pozwala wybrać poziom szczegółowości (`Debug`, `Info`, `Warning`, `Error`) i domyślnie zapisuje logi do pliku tekstowego.

### Wymagania:
- Zdefiniuj `enum LogLevel` i strukturę `Logger`, która przechowuje poziom logowania i plik docelowy.
- Zaimplementuj metodę `log`, która wypisuje komunikaty w zależności od poziomu szczegółowości.
- Zapewnij zapis logów do pliku `app.log`.

### Przykład:
```rust
let mut logger = Logger::new(LogLevel::Info, "app.log");
logger.log(LogLevel::Warning, "To jest ostrzeżenie!");
logger.log(LogLevel::Debug, "Debugowanie danych..."); // Nie zapisze, ponieważ poziom to Info
```

---

## 3. Asynchroniczny serwer HTTP z obsługą JSON
Stwórz asynchroniczny serwer HTTP za pomocą `axum`, który obsługuje zapytania POST i przyjmuje dane w formacie JSON. Serwer powinien parsować dane i zwracać potwierdzenie w formacie JSON.

### Wymagania:
- Serwer powinien obsługiwać trasę `/submit` przy użyciu metody POST i oczekiwać JSON zawierający `name` i `age`.
- Użyj `serde_json` do parsowania i zwracania danych w formacie JSON.

### Przykład:
```
POST /submit
Request JSON: {"name": "Alice", "age": 30}
Response JSON: {"status": "success", "name": "Alice", "age": 30}
```

---

## 4. Przetwarzanie plików CSV i analizowanie danych
Napisz funkcję `process_csv`, która wczytuje dane z pliku CSV i zwraca średnią arytmetyczno-geometryczną liczb dla określonej kolumny.

### Wymagania:
- Skorzystaj z `csv` crate do odczytu danych z pliku.
- Funkcja powinna przyjąć nazwę kolumny i obliczyć średnią arytmetyczno-geometryczną dla tej kolumny.

### Przykład:
```rust
let avg = process_csv("data.csv", "score");
println!("Średnia wartość kolumny 'score': {}", avg); // Wynik: 75.3 (na podstawie danych z pliku)
```

---

