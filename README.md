# Uzgodnienia PECI → Xpertis

Narzędzie warsztatowe do uzgadniania interfejsu Workday (Chorus, plik PECI) → middleware → Xpertis dla Polski. Partnerzy Workday i Xpertis oraz integrator przechodzą proces po procesie i dla każdego pola potwierdzają:

- co wysyła Workday w PECI (element XML, typ danych, format),
- czy zestaw danych wystarcza Xpertis do wykonania operacji,
- na jaki format standardu Xpertis middleware ma przekształcić daną (reguła, słownik, przykład wejście → wyjście),
- skąd uzupełnić dane, których PECI nie dostarcza.

## Co zawiera

| Widok | Zastosowanie |
|---|---|
| Procesy | 31 procesów HR (P00–P30), lista pól, karta pola Workday → middleware → Xpertis, potwierdzenia stron, komentarze, akceptacja procesu |
| Paczka Xpertis | Komplet danych potrzebnych Xpertis w danym procesie i źródło każdej z nich; dopisywanie brakujących danych |
| Kontrola | Kontrole kompletności i spójności liczone na bieżąco (brak źródła, brak formatu docelowego, słownik, niespójności między procesami) |
| Przegląd | Postęp wszystkich procesów, dane bez źródła, pola czekające na decyzję |
| Kwestie, Słowniki, Reguły, Zdarzenia PECI, Katalog PECI | Rejestr kwestii, pary kodów Workday ↔ Xpertis, reguły transformacji, kody zdarzeń, pełny katalog pól PECI |

## Jak pracować

1. Otwórz `index.html` (lokalnie albo przez GitHub Pages).
2. W prawym górnym rogu wybierz stronę („Pracuję jako”) i wpisz podpis.
3. Zmiany zapisują się w przeglądarce. Żeby przekazać ustalenia innym stronom, użyj **Zapisz stan** (plik JSON), a druga strona używa **Wczytaj stan**. Wczytanie scala zmiany: nowsze wpisy wygrywają, potwierdzenia i akceptacje stron są łączone.
4. **Eksport do Excela** tworzy plik z mapowaniem, paczkami Xpertis, procesami, kwestiami, słownikami i komentarzami.

Skróty klawiszowe na liście pól: `j` / `k` – następne i poprzednie pole, `Esc` – zamknięcie karty.

## Źródła danych

Propozycja mapowania (wersja 0.1, 22.10.2026) powstała z plików roboczych projektu: Data Dictionary PL, katalog pól PECI (Chorus), Data Traceability Matrix i próbki PECI. Próbki pochodzą z plików testowych innych krajów – słowniki dla Polski wymagają potwierdzenia na polskim pliku testowym. Plik „Fields mapping open points” był chroniony i nie został uwzględniony (kwestia K-01).

Narzędzie nie zawiera danych osobowych pracowników.

## Biblioteki

Eksport do Excela korzysta z [SheetJS](https://sheetjs.com) 0.18.5 (`vendor/xlsx.full.min.js`, licencja Apache 2.0).
