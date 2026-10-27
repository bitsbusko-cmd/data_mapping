# Uzgodnienia PECI → Xpertis · PECI → Xpertis mapping

**PL** · [EN](#english)

Narzędzie warsztatowe do uzgadniania interfejsu Workday (Chorus, plik PECI) → middleware → Xpertis dla Polski. Partner Workday, partner Xpertis i integrator przechodzą proces po procesie i dla każdego pola potwierdzają:

- co wysyła Workday w PECI (element XML, typ danych, format),
- jak middleware przekształca daną na standard Xpertis (wystarczalność, rodzaj transformacji, format docelowy, reguła, słownik),
- gdzie dana trafia w Xpertis (pole, obiekt, typ, wymagalność),
- skąd uzupełnić dane, których PECI nie dostarcza.

## Język

Przełącznik **PL | EN** na górnym pasku zmienia język interfejsu i danych referencyjnych (opisy pól, procesów, kwestii, reguł i słowników). Wersję można też wskazać w linku: `index.html?lang=pl` albo `index.html?lang=en`. Wybór zapamiętuje przeglądarka; przy pierwszym uruchomieniu narzędzie przyjmuje język przeglądarki.

Ustalenia zapisują się niezależnie od języka: statusy, wybory z list i potwierdzenia są wspólne, więc strona polska i zagraniczna pracują na tym samym pliku ustaleń – każda we własnym języku. Tekst wpisany ręcznie (komentarze, decyzje, formaty) pozostaje w języku autora. Eksport do Excela i protokół warsztatu powstają w języku wybranym w chwili eksportu.

## Jak pracować

1. Otwórz `index.html` (lokalnie albo przez GitHub Pages). Przy pierwszym uruchomieniu podaj imię i nazwisko oraz stronę – podpisują komentarze, potwierdzenia i akceptacje.
2. Wybierz proces z listy po lewej (kolejność: P00, potem wejście, dane osobowe, zmiany, wynagrodzenie, nieobecności, wyjście).
3. Przechodź pola po kolei. Karta pola ma trzy kroki z osobnym potwierdzeniem każdej strony: **1 Workday**, **2 Middleware**, **3 Xpertis**. Gdy wszystkie strony się zgadzają, kliknij **Uzgodnione na warsztacie** – pole dostaje status „Potwierdzone”, a karta przechodzi do następnego pola.
4. Brakujące dane dopisz w zakładce **Paczka Xpertis**.
5. W zakładce **Kontrola** popraw błędy i ostrzeżenia (przycisk „Popraw” prowadzi do właściwego pola). Formaty docelowe wynikające z reguł możesz przyjąć jednym kliknięciem.
6. W zakładce **Akceptacja** wpisz dane warsztatu, zaakceptuj proces w imieniu stron i skopiuj protokół warsztatu.

**Przegląd** pokazuje postęp wszystkich procesów, pola czekające na decyzję, dane bez źródła i działania według właścicieli.

## Specyfikacja PECI dla zespołu Xpertis

Zakładka **Specyfikacja PECI** (w każdym procesie) i sekcja 1 karty pola pokazują dokładnie, co wysyła Workday:

- ścieżkę XML (np. `Effective_Change › Worker_Status › Hire_Date`),
- typ danych i zapis (np. data `RRRR-MM-DD±hh:mm`, wartość logiczna `1 / 0`, kod – Reference ID albo Mapped_Value, tekst z wiodącymi zerami),
- wartości z próbek PECI, długości tekstu, wielokrotność, atrybuty zmian (`isAdded`, `isUpdated`, `isDeleted`, `priorValue`),
- zdarzenia, przy których sekcja zawsze jest w pliku (według dokumentacji Workday).

Zespół Xpertis ocenia każde pole: **Zgodne** albo **Pytanie** (z treścią pytania do Workday). Pytania trafiają do kontroli, protokołu warsztatu i eksportu do Excela (arkusz „Specyfikacja PECI”). Objaśnienie typów danych otwiera link „Jak czytać typy danych PECI”, a widok **Zdarzenia** pokazuje datę zdarzenia i sekcje w pliku dla każdego kodu (np. TERM = data rozwiązania + 1 dzień).

Typy i przykłady wartości ustalono na podstawie próbek PECI projektu (pliki testowe innych krajów) i słownika PECI Chorus; dane osobowe z próbek zostały zastąpione kształtem wartości (A/a – litera, 9 – cyfra). Ostatecznym potwierdzeniem jest plik PECI z tenanta PL.

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

W profilu (prawy górny róg) można też zmienić język, włączyć **duży tekst** na projektor oraz wybrać motyw jasny lub ciemny.

## Źródła danych

Propozycja mapowania (wersja 0.1, 22.10.2026) powstała z plików roboczych projektu: Data Dictionary PL, katalog pól PECI (Chorus), Data Traceability Matrix i próbki PECI. Próbki pochodzą z plików testowych innych krajów – słowniki dla Polski wymagają potwierdzenia na polskim pliku testowym. Plik „Fields mapping open points” był chroniony i nie został uwzględniony (kwestia K-01). Wersja angielska danych referencyjnych jest tłumaczeniem wersji polskiej; w razie rozbieżności rozstrzyga wersja polska.

Opis budowy pliku, atrybutów zmian, daty zdarzeń i sekcji w pliku pochodzi z dokumentacji Workday: [Creating PECI Integrations](https://doc.workday.com/workday-education/en-us/course-manuals/creating-integrations-using-global-payroll-connect/creating-peci-integrations.html), [Change Detection](https://doc.workday.com/workday-education/en-us/course-manuals/creating-integrations-using-global-payroll-connect/change-detection.html), [Functional Changes](https://doc.workday.com/workday-education/en-us/course-manuals/creating-integrations-using-global-payroll-connect/functional-changes.html) (Workday Education, Creating Integrations Using Global Payroll Connect).

Narzędzie nie zawiera danych osobowych pracowników.

---

<a id="english"></a>
## English

A workshop tool for agreeing the Workday (Chorus, PECI file) → middleware → Xpertis interface for Poland. The Workday partner, the Xpertis partner and the integrator go through the processes one by one and, for every field, confirm:

- what Workday sends in PECI (XML element, data type, format),
- how middleware transforms the data to the Xpertis standard (sufficiency, transformation type, target format, rule, dictionary),
- where the data goes in Xpertis (field, object, type, whether required),
- where to complete data that PECI does not deliver.

### Language

The **PL | EN** switch in the top bar changes the language of the interface and of the reference data (descriptions of fields, processes, issues, rules and dictionaries). You can also set it in the link: `index.html?lang=en` or `index.html?lang=pl`. The browser remembers the choice; on first use the tool follows the browser language.

Agreements are stored independently of the language: statuses, list choices and confirmations are shared, so the Polish and the international parties work on the same agreements file – each in their own language. Text typed by hand (comments, decisions, formats) stays in the author's language. The Excel export and the workshop minutes are produced in the language selected at the time of export.

### How to work

1. Open `index.html` (locally or via GitHub Pages). On first use, enter your name and party – they sign your comments, confirmations and sign-offs.
2. Choose a process from the list on the left (order: P00, then entry, personal data, changes, compensation, absences, exit).
3. Go through the fields one by one. The field card has three steps, each confirmed separately by its party: **1 Workday**, **2 Middleware**, **3 Xpertis**. When all parties agree, click **Agreed in workshop** – the field gets the status “Confirmed” and the card moves on to the next field.
4. Add missing data in the **Xpertis package** tab.
5. In the **Checks** tab, fix errors and warnings (the “Fix” button takes you to the right field). Target formats that follow from the rules can be accepted with one click.
6. In the **Sign-off** tab, enter the workshop details, sign off the process on behalf of the parties and copy the workshop minutes.

The **Overview** shows the progress of all processes, fields awaiting a decision, data without a source and actions by owner.

### PECI specification for the Xpertis team

The **PECI specification** tab (in every process) and section 1 of the field card show exactly what Workday sends:

- the XML path (e.g. `Effective_Change › Worker_Status › Hire_Date`),
- the data type and notation (e.g. date `YYYY-MM-DD±hh:mm`, boolean `1 / 0`, code – Reference ID or Mapped_Value, digit strings with leading zeros),
- values from PECI samples, text lengths, multiplicity, change attributes (`isAdded`, `isUpdated`, `isDeleted`, `priorValue`),
- the events in which the section is always in the file (per Workday documentation).

The Xpertis team rates every field: **Matches** or **Question** (with the question to Workday). Questions go into the checks, the workshop minutes and the Excel export (sheet “PECI specification”). The “How to read PECI data types” link opens a data-type reference, and the **Events** view shows the event date and the sections in the file for every code (e.g. TERM = termination date + 1 day).

Types and sample values were derived from the project's PECI samples (test files of other countries) and the Chorus PECI dictionary; personal data from the samples was replaced by the shape of the value (A/a – letter, 9 – digit). The final confirmation is a PECI file from the PL tenant.

### Saving and exchanging agreements

Changes are saved automatically in the browser. To pass your agreements to the other parties, choose **File → Save agreements to file** and send the JSON file. The recipient chooses **File → Load agreements from file** – changes are merged: newer entries win, and the parties' confirmations and sign-offs are combined. **File → Export to Excel** creates a workbook with the mapping, Xpertis packages, processes, issues, dictionaries and comments.

### Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl` + `K` or `/` | Search the whole tool (fields, processes, issues, dictionaries, rules) |
| `j` / `k` or `↓` / `↑` | Next / previous field |
| `Ctrl` + `Enter` | Send comment |
| `Esc` | Close the window or the field card |
| `?` | Help |

The profile menu (top right) also lets you change the language, switch on **large text** for a projector and choose a light or dark theme.

### Data sources

The mapping proposal (version 0.1, 22 October 2026) was built from the project working files: Data Dictionary PL, the PECI field catalogue (Chorus), the Data Traceability Matrix and PECI samples. The samples come from test files of other countries – the dictionaries for Poland need to be confirmed on a Polish test file. The file “Fields mapping open points” was protected and was not included (issue K-01). The English reference data is a translation of the Polish version; where they differ, the Polish version prevails.

The description of the file structure, change attributes, event dates and sections in the file comes from the Workday documentation listed above (Workday Education, Creating Integrations Using Global Payroll Connect).

The tool contains no employee personal data.

## Biblioteki · Libraries

Eksport do Excela korzysta z / The Excel export uses [SheetJS](https://sheetjs.com) 0.18.5 (`vendor/xlsx.full.min.js`, Apache 2.0). Krój pisma / Typeface: IBM Plex (Google Fonts).
