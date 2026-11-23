# ADR-003: Technologia — Python i Kivy, własny edytor klocków

**Status:** proponowana (do potwierdzenia po prototypie)
**Data:** 2026-11-22
**Autorzy:** Arsenii Liapin (z zespołem)

## Kontekst

ADR-002 ustala, że system jest jedną lokalną aplikacją (modularny monolit) bez serwera, która działa na telefonie z Androidem oraz na komputerze, jako ta sama aplikacja, bez osobnego interfejsu (FR-21). Ten ADR wybiera technologię tej aplikacji: język, biblioteki, edytor klocków i sposób pakowania.

Wymagania, które najmocniej wpływają na wybór:
- FR-01: dodanie klocka do programu z klocków metodą „przeciągnij i upuść” na ekranie dotykowym telefonu.
- FR-21: edytor i uruchamianie gier także na komputerze, w tej samej aplikacji.
- NFR-02: średnio co najmniej 30 klatek na sekundę w scenie z 50 obiektami gry na telefonie z Androidem z 3 GB pamięci RAM.
- NFR-03: od naciśnięcia przycisku „Stop” do zatrzymania uruchomionej gry mija nie więcej niż 1 sekunda, także przy pętli, która się nie kończy.
- NFR-05: obszar dotyku klocka i przycisku „Stop” co najmniej 9 × 9 mm.
- NFR-07: edytor wyświetla się w całości na ekranach telefonów o przekątnej od 5,0 do 6,7 cala, w orientacji pionowej i poziomej.
- NFR-09: uruchomienie na komputerze bez uprawnień administratora, na którym instalowanie programów jest zablokowane.

Zespół najlepiej zna Pythona. Karta projektu zapisuje Pythona i Kivy jako technologie rozważane wstępnie (sekcja „Wstępnie rozważane technologie”), a lista kandydatów „make or buy” (`docs/06-architektura/make-or-buy.md`) pozostawia do decyzji edytor klocków, platformę i wersję przenośną. Interpreter programu z klocków oraz stały zestaw klocków i zdarzenia są tam oznaczone jako „make”. Format pliku projektu gry i format wyeksportowanej gry nie są przedmiotem tego ADR.

## Rozważane opcje

### Obszar: platforma

1. **Kivy (Python).** Jedna aplikacja w Pythonie z interfejsem w Kivy, pakowana na Androida i na komputer.
2. **Aplikacja webowa.** System działa w przeglądarce (opcja 3 w ADR-002).
3. **Natywny Android.** Aplikacja napisana w języku przeznaczonym dla Androida (Kotlin lub Java).

| Wymaganie | Kivy (Python) | Aplikacja webowa | Natywny Android |
|---|---|---|---|
| Ta sama aplikacja na Androidzie i komputerze (FR-21, ADR-002) | spełnia: jeden kod w Pythonie dla obu platform | odrzucona w ADR-002 | nie spełnia: na komputer potrzebna osobna aplikacja |
| Język znany zespołowi | Python, który zespół zna najlepiej | JavaScript, drugi język | Kotlin lub Java, nowy język dla zespołu |
| Uruchomienie na komputerze bez instalacji (NFR-09) | wersja przenośna przez PyInstaller, do sprawdzenia | łatwiejsze, ale odrzucona w ADR-002 | nie dotyczy komputera |
| Wydajność na telefonie (NFR-02) | do potwierdzenia prototypem | zależy od przeglądarki | najmniejsze ryzyko |
| Ekrany 5,0–6,7 cala, obie orientacje (NFR-07) | układ ekranu przygotowujemy sami, do sprawdzenia | układ ekranu przygotowujemy sami | gotowe mechanizmy Androida |
| Licencja | Kivy: MIT, bezpłatna | nie dotyczy | bezpłatne narzędzia |

### Obszar: edytor klocków

- **A) Blockly** (biblioteka JavaScript) osadzona w aplikacji.
- **B) Własny edytor klocków w Kivy.**

| Wymaganie | A) Blockly osadzona w aplikacji | B) Własny edytor klocków w Kivy |
|---|---|---|
| „Przeciągnij i upuść” na ekranie dotykowym (FR-01) | gotowe w bibliotece | do napisania przez zespół |
| Obszar dotyku 9 × 9 mm (NFR-05) | wymaga dostosowania wyglądu klocków | rozmiar klocków ustalamy sami |
| Stały zestaw klocków (BR-02) | spełnia: udostępniamy tylko własny zestaw klocków | spełnia: edytor zna tylko nasze klocki |
| Działanie w aplikacji Kivy na Androidzie i komputerze (FR-21) | wymaga przeglądarki osadzonej w aplikacji Kivy na Androidzie oraz przekazywania programu z klocków między JavaScript a Pythonem | edytor jest częścią tej samej aplikacji Kivy |
| Język | drugi język (JavaScript) obok Pythona | jeden język (Python) |
| Licencja | Apache 2.0, bezpłatna | nie dotyczy |
| Nakład pracy w semestrze 2 | mniej pracy nad samym edytorem, więcej nad osadzeniem i integracją | dużo pracy nad edytorem |

## Decyzja

| Obszar | Technologia | Uwagi |
|---|---|---|
| język programowania | Python | jeden język w całym projekcie |
| interfejs i runner | Kivy | ta sama aplikacja na Androidzie i komputerze (FR-21, ADR-002) |
| edytor klocków | własny edytor klocków w Kivy (make) | moduł `editor/` |
| interpreter | Python (make) | moduł `interpreter/`; rdzeń dziedziny Modde (`make-or-buy.md`) |
| pakowanie na Androida | Buildozer | plik instalacyjny aplikacji na Androida |
| wersja na komputer | PyInstaller | wersja przenośna, bez instalacji (NFR-09) |

Dlaczego nie Blockly: Blockly wymaga przeglądarki osadzonej w aplikacji Kivy na Androidzie i drugiego języka (JavaScript) obok Pythona. Program z klocków musiałby być przekazywany między edytorem w JavaScript a interpreterem w Pythonie, co dodaje kolejną granicę do utrzymania obok formatu w `contract/`.

Dlaczego nie aplikacja webowa: ta forma została odrzucona w ADR-002.

Dlaczego nie natywny Android: na komputer potrzebna byłaby osobna aplikacja (FR-21), a zespół nie zna języków przeznaczonych dla Androida.

Decyzja jest wstępna. Status zmieni się na „przyjęta” po wykonaniu prototypu edytora klocków, interpretera i runnera.

## Konsekwencje

Co zyskujemy:
- Jeden język w całym projekcie: edytor, interpreter, runner oraz zapis i eksport są pisane w Pythonie, który zespół zna najlepiej.
- Ta sama aplikacja działa na Androidzie i na komputerze, bez osobnego interfejsu (FR-21).
- Własny edytor klocków zna tylko stały zestaw klocków (BR-02), a rozmiar klocków i przycisku „Stop” ustalamy sami (NFR-05).
- Brak kosztów licencji.

Co tracimy / jakie są ryzyka:
- Własny edytor klocków to dużo pracy w semestrze 2, szczególnie „przeciągnij i upuść” na ekranie dotykowym (FR-01) i układ ekranu na telefonach o przekątnej 5,0–6,7 cala (NFR-07).
- Wydajność Kivy na słabym telefonie (NFR-02) trzeba potwierdzić prototypem.
- Zatrzymanie gry w czasie nie dłuższym niż 1 sekunda, także przy pętli, która się nie kończy (NFR-03), trzeba potwierdzić prototypem interpretera.
- Wersja przenośna przez PyInstaller może zostać zablokowana przez szkolne zabezpieczenia (NFR-09); do sprawdzenia w pracowni szkolnej.

Co musimy zrobić:
- Wykonać prototyp edytora klocków, interpretera i uproszczonego runnera przed decyzją ostateczną, z pomiarem NFR-02 i NFR-03 na telefonie z Androidem. (Arsenii, Bekzhigit, Daryna M.)
- Zmienić status tego ADR na „przyjęta” po potwierdzeniu prototypem. (Arsenii)