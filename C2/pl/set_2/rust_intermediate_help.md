
# Pomoc do Zadań Średniozaawansowanych (Rust Intermediate Help)

## Iterator liczb pierwszych
Tworzenie niestandardowego iteratora wymaga zdefiniowania struktury i implementacji `Iterator` dla niej. Możesz dodać metodę pomocniczą `is_prime` do sprawdzania, czy liczba jest pierwsza.

### Wskazówki:
- `is_prime` może przetestować liczby dzielnikiem od `2` do `sqrt(n)`.
- Metoda `next` powinna przechodzić przez liczby całkowite, używając `is_prime`, aby zwracać tylko liczby pierwsze.

---

## System logowania z poziomem szczegółowości
Zastosowanie `enum` dla poziomów logowania (np. `Debug`, `Info`, `Warning`, `Error`) pozwala kontrolować szczegółowość logów.

### Wskazówki:
- W `Logger` użyj struktury, aby zapisać poziom logowania oraz docelowy plik.
- Metoda `log` powinna porównywać poziom logowania komunikatu z poziomem ustawionym w `Logger`, aby decydować, czy zapisać log.
- Do zapisu do pliku użyj `std::fs::File` i `write!`.

---

## Serwer HTTP z obsługą JSON
Aby zbudować serwer HTTP z `axum` obsługujący JSON, możesz wykorzystać asynchroniczne funkcje i crate `serde_json` do parsowania danych JSON.

### Wskazówki:
- Użyj `Router` z `axum` do tworzenia trasy POST.
- Dodaj `serde::Deserialize` do struktury, aby automatycznie mapować JSON na struktury.
- Asynchroniczne funkcje pozwalają na obsługę żądań równocześnie.

---

## Przetwarzanie plików CSV
Crate `csv` w Rust pozwala na łatwe wczytywanie i analizowanie danych CSV. Możesz wczytać dane jako `Record` i analizować wybraną kolumnę.

### Wskazówki:
- Użyj `ReaderBuilder` z `csv` crate, aby odczytać plik CSV.
- Iteruj po każdym rekordzie i zbieraj wartości z danej kolumny.
- Oblicz średnią, sumując wartości i dzieląc przez liczbę rekordów.

---

# Dodatkowe Zasoby
- **Serde**: [https://serde.rs/](https://serde.rs/)
- **CSV crate**: [https://docs.rs/csv/](https://docs.rs/csv/)
- **Axum Documentation**: [https://docs.rs/axum/latest/axum/](https://docs.rs/axum/latest/axum/)
