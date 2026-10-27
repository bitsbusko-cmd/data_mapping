# Uzgodnienia PECI → Xpertis

Narzędzie warsztatowe do uzgadniania interfejsu Workday (Chorus, plik PECI) → middleware → Xpertis dla Polski. Partner Workday, partner Xpertis i integrator przechodzą proces po procesie i dla każdego pola potwierdzają:

- co wysyła Workday w PECI (element XML, typ danych, format),
- jak middleware przekształca daną na standard Xpertis (wystarczalność, rodzaj transformacji, format docelowy, reguła, słownik),
- gdzie dana trafia w Xpertis (pole, obiekt, typ, wymagalność),
- skąd uzupełnić dane, których PECI nie dostarcza.

## Jak pracować

1. Otwórz `index.html` (lokalnie albo przez GitHub Pages). Przy pierwszym uruchomieniu podaj imię i nazwisko oraz stronę – podpisują komentarze, potwierdzenia i akceptacje.
2. Wybierz proces z listy po lewej (kolejność: P00, potem wejście, dane osobowe, zmiany, wynagrodzenie, nieobecności, wyjście).
3. Przechodź pola po kolei. Karta pola ma trzy kroki z osobnym potwierdzeniem każdej strony: **1 Workday**, **2 Middleware**, **3 Xpertis**. Gdy wszystkie strony się zgadzają, kliknij **Uzgodnione na warsztacie** – pole dostaje status „Potwierdzone”, a karta przechodzi do następnego pola.
4. Brakujące dane dopisz w zakładce **Paczka Xpertis**.
5. W zakładce **Kontrola** popraw błędy i ostrzeżenia (przycisk „Popraw” prowadzi do właściwego pola). Formaty docelowe wynikające z reguł możesz przyjąć jednym kliknięciem.
6. W zakładce **Akceptacja** wpisz dane warsztatu, zaakceptuj proces w imieniu stron i skopiuj protokół warsztatu.

**Przegląd** pokazuje postęp wszystkich procesów, pola czekające na decyzję, dane bez źródła i działania według właścicieli.

## Zapisywanie i wymiana ustaleń

Zmiany zapisują się automatycznie w przeglądarce. Żeby przekazać ustalenia innym stronom, wybierz **Plik → Zapisz ustalenia do pliku** i wyślij plik JSON. Odbiorca wybiera **Plik → Wczytaj ustalenia z pliku** – zmiany zostaną scalone: nowsze wpisy wygrywają, a potwierdzenia i akceptacje stron się łączą. **Plik → Eksport do Excela** tworzy skoroszyt z mapowaniem, paczkami Xpertis, procesami, kwestiami, słownikami i komentarzami.

## Skróty

| Skrót | Działanie |
|---|---|
| `Ctrl` + `K` lub `/` | Szukaj w całym narzędziu (pola, procesy, kwestie, słowniki, reguły) |
| `j` / `k` lub `↓` / `↑` | Następne / poprzednie pole |
| `Ctrl` + `Enter` | Wyślij komentarz |
| `Esc` | Zamknij okno albo kartę pola |
| `?` | Pomoc |

W profilu (prawy górny róg) można włączyć **duży tekst** na projektor oraz wybrać motyw jasny lub ciemny.

## Źródła danych

Propozycja mapowania (wersja 0.1, 22.10.2026) powstała z plików roboczych projektu: Data Dictionary PL, katalog pól PECI (Chorus), Data Traceability Matrix i próbki PECI. Próbki pochodzą z plików testowych innych krajów – słowniki dla Polski wymagają potwierdzenia na polskim pliku testowym. Plik „Fields mapping open points” był chroniony i nie został uwzględniony (kwestia K-01).

Narzędzie nie zawiera danych osobowych pracowników.

## Biblioteki

Eksport do Excela korzysta z [SheetJS](https://sheetjs.com) 0.18.5 (`vendor/xlsx.full.min.js`, licencja Apache 2.0). Krój pisma: IBM Plex (Google Fonts).
