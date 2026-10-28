# Analiza PECI → Xpertis · PECI → Xpertis analysis

**PL** · [EN](#english)

Narzędzie do warsztatów z zespołem Xpertis dla integracji Workday (Chorus) → Xpertis w Polsce.

Workday generuje plik PECI i przesyła go przez SFTP do Xpertis. Zespół Xpertis buduje i utrzymuje bazę pośredniczącą, która wczytuje plik, konwertuje dane na standard Xpertis i ładuje je do baz produkcyjnych poszczególnych pracodawców.

**Punkt wyjścia:** znamy plik PECI – jego zakres i typy danych w każdym procesie HR. Nie zakładamy nic o tym, w jakim zakresie i formacie dane mają trafiać do Xpertis. To ustalamy na warsztatach.

## Widoki

- **Start** – cel, schemat przepływu (co znane, co do ustalenia), postęp, plan warsztatów W1–W6 i postęp procesów.
- **Procesy** – 29 procesów HR. Każdy ma trzy zakładki:
  - **Dane z PECI** – elementy pogrupowane według sekcji PECI, z typem, zapisem i przykładami z próbek. Dla każdej danej zespół Xpertis decyduje: **Potrzebna**, **Niepotrzebna** albo **Do wyjaśnienia** (przyciski w wierszu albo klawisze 1, 2, 3). Decyzję można też podjąć dla całej sekcji. Karta danej pokazuje pełną specyfikację PECI i pola analizy: gdzie dana trafia w Xpertis, typ i format w Xpertis, konwersję w bazie pośredniczącej, notatki i pytania. Analizę tej samej danej z innego procesu można przyjąć jednym kliknięciem.
  - **Dane spoza PECI** – dane, których Xpertis potrzebuje, a PECI ich nie wysyła. Każda ma proponowane źródło: pole dodatkowe w PECI, osobny raport przez SFTP, wprowadzenie w Xpertis albo wyliczenie w bazie pośredniczącej.
  - **Ustalenia procesu** – operacja w Xpertis, data skuteczności i kolejność, przypadki szczególne, dane warsztatu, pytania, protokół do skopiowania i zatwierdzenie analizy przez Workday, Xpertis i Saint-Gobain.
- **Baza pośrednicząca** – 26 tematów projektowych w 8 obszarach: odbiór pliku, wczytanie i struktura danych, identyfikacja i routing, konwersja, walidacja i wyjątki, ładowanie do baz produkcyjnych, bezpieczeństwo i RODO, testy i uruchomienie. Każdy temat ma fakty o PECI, pytania do zespołu Xpertis, ustalenia, status, właściciela i termin.
- **Pytania** – wspólny rejestr pytań do Workday, Xpertis i Saint-Gobain. Pytania zadane przy danych, procesach i tematach trafiają tutaj. Statusy: Otwarte → Odpowiedziane → Zamknięte.
- **Dokumentacja PECI** – budowa pliku, typy danych, atrybuty zmian, tabela zdarzeń i katalog pól PECI. Element z katalogu można dodać do procesu.

## Zapisywanie i wymiana ustaleń

Zmiany zapisują się automatycznie w przeglądarce.

- **Plik → Zapisz ustalenia do pliku** tworzy plik JSON do przekazania innym stronom.
- **Plik → Wczytaj ustalenia z pliku** scala zmiany: nowsze wpisy wygrywają, a zatwierdzenia stron się łączą.
- **Plik → Eksport do Excela** tworzy skoroszyt z arkuszami:
  - Analiza danych PECI (jeden wiersz na element XML),
  - Dane spoza PECI,
  - Baza pośrednicząca,
  - Pytania,
  - Procesy,
  - Plan warsztatów.

Narzędzie zaczyna od zera. Pliku z poprzedniej wersji (uzgadnianie propozycji mapowania) nie można wczytać.

## Język i skróty

Przełącznik **PL | EN** zmienia język interfejsu i danych referencyjnych (także `?lang=pl` / `?lang=en` w linku). Tekst wpisany ręcznie pozostaje w języku autora.

| Skrót | Działanie |
|---|---|
| `Ctrl` + `K` lub `/` | Szukaj (dane, procesy, tematy, pytania) |
| `j` / `k` lub `↓` / `↑` | Następna / poprzednia dana |
| `1` / `2` / `3` | Potrzebna / niepotrzebna / do wyjaśnienia |
| `Ctrl` + `Enter` | Dodaj pytanie |
| `Esc` | Zamknij okno albo kartę danej |
| `?` | Pomoc |

## Źródła

Zakres i typy danych PECI pochodzą z:
- katalogu pól PECI (Chorus),
- słownika danych PL,
- próbek PECI projektu (pliki testowe innych krajów). Dane osobowe z próbek zastąpiono kształtem wartości (A/a – litera, 9 – cyfra).

Ostatecznym potwierdzeniem jest plik PECI z tenanta PL. Budowa pliku, atrybuty zmian, daty zdarzeń i sekcje w pliku pochodzą z dokumentacji Workday: [Creating PECI Integrations](https://doc.workday.com/workday-education/en-us/course-manuals/creating-integrations-using-global-payroll-connect/creating-peci-integrations.html), [Change Detection](https://doc.workday.com/workday-education/en-us/course-manuals/creating-integrations-using-global-payroll-connect/change-detection.html), [Functional Changes](https://doc.workday.com/workday-education/en-us/course-manuals/creating-integrations-using-global-payroll-connect/functional-changes.html).

Narzędzie nie zawiera danych osobowych pracowników.

---

<a id="english"></a>
## English

A workshop tool for working with the Xpertis team on the Workday (Chorus) → Xpertis integration for Poland.

Workday generates the PECI file and sends it via SFTP to Xpertis. The Xpertis team builds and maintains a staging database that loads the file, converts the data to the Xpertis standard and loads it into the production databases of the individual employers.

**Starting point:** we know the PECI file – its scope and data types in every HR process. We assume nothing about the scope and format in which data should reach Xpertis. That is what the workshops establish.

### Views

- **Start** – goal, data-flow diagram (known vs. to be agreed), progress, workshop plan W1–W6 and process progress.
- **Processes** – 29 HR processes. Each has three tabs:
  - **Data from PECI** – elements grouped by PECI section, with type, notation and sample values. For each item the Xpertis team decides: **Needed**, **Not needed** or **To clarify** (row buttons or keys 1, 2, 3). The decision can also be made for a whole section. The data card shows the full PECI specification and the analysis fields: where the data goes in Xpertis, type and format in Xpertis, conversion in the staging database, notes and questions. The analysis of the same item from another process can be adopted with one click.
  - **Data outside PECI** – data Xpertis needs that PECI does not send. Each item has a proposed source: an additional field in PECI, a separate report over SFTP, entry in Xpertis or a calculation in the staging database.
  - **Process outcomes** – operation in Xpertis, effective date and order, special cases, workshop details, questions, minutes to copy and sign-off by Workday, Xpertis and Saint-Gobain.
- **Staging database** – 26 design topics in 8 areas: file reception, loading and data structure, identification and routing, conversion, validation and exceptions, loading into production databases, security and GDPR, testing and go-live. Each topic has facts about PECI, questions to the Xpertis team, decisions, status, owner and due date.
- **Questions** – a shared register of questions to Workday, Xpertis and Saint-Gobain. Questions asked on data items, processes and topics land here. Statuses: Open → Answered → Closed.
- **PECI documentation** – file structure, data types, change attributes, event table and the PECI field catalogue. A catalogue element can be added to a process.

### Saving and exchanging work

Changes are saved automatically in the browser.

- **File → Save agreements to file** creates a JSON file to pass to the other parties.
- **File → Load agreements from file** merges changes: newer entries win, and party sign-offs are combined.
- **File → Export to Excel** creates a workbook with these sheets:
  - PECI data analysis (one row per XML element),
  - Data outside PECI,
  - Staging database,
  - Questions,
  - Processes,
  - Workshop plan.

The tool starts from scratch. Files from the previous version (agreeing a mapping proposal) cannot be loaded.

### Language and shortcuts

The **PL | EN** switch changes the language of the interface and the reference data (also `?lang=pl` / `?lang=en` in the link). Text typed by hand stays in the author's language. Shortcuts: `Ctrl`+`K` or `/` search, `j`/`k` next/previous item, `1`/`2`/`3` needed/not needed/to clarify, `Ctrl`+`Enter` add question, `Esc` close, `?` help.

### Sources

PECI scope and data types come from:
- the Chorus PECI field catalogue,
- the PL data dictionary,
- the project's PECI samples (test files of other countries). Personal data from the samples is replaced by the shape of the value (A/a – letter, 9 – digit).

The final confirmation is a PECI file from the PL tenant. The file structure, change attributes, event dates and sections in the file come from the Workday documentation linked above.

The tool contains no employee personal data.

## Biblioteki · Libraries

Eksport do Excela korzysta z / The Excel export uses [SheetJS](https://sheetjs.com) 0.18.5 (`vendor/xlsx.full.min.js`, Apache 2.0). Krój pisma / Typeface: IBM Plex (Google Fonts).
