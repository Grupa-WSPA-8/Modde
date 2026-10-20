# ADR-001: Narzędzia pracy projektowej

**Status:** proponowana
**Data:** 2026-10-20
**Autorzy:** Arsenii Liapin (z zespołem)

## Kontekst

Zespół 4 osób, praca zdalna i na zajęciach, zróżnicowane doświadczenie z narzędziami (część osób nie pracowała wcześniej z Git w zespole). Dokumentacja musi być dostępna również w semestrze 2. Repozytorium znajduje się w organizacji GitHub, a prowadzący ma do niego dostęp. Projekt nie ma serwera: dane są przechowywane lokalnie na urządzeniu (sposób przechowywania do ustalenia). Wybór technologii programistycznej (język, biblioteki) nie jest przedmiotem tego ADR i zostanie zapisany w ADR-002 po wykonaniu prototypu.

## Rozważane opcje

Kryteria i wagi (1: mało ważne, 3: bardzo ważne):

| Kryterium | Waga |
|---|---|
| koszt i licencja | 3 |
| praca wielu osób jednocześnie | 2 |
| wersjonowanie i integracja z repozytorium | 3 |
| próg wejścia (czas nauki) | 3 |
| eksport / trwałość w semestrze 2 | 2 |

Oceny w skali 1–5.

### Obszar: zarządzanie zadaniami

| Kryterium | Waga | GitHub Projects | Trello | Taiga |
|---|---|---|---|---|
| koszt i licencja | 3 | 5 | 4 | 4 |
| praca wielu osób | 2 | 5 | 5 | 4 |
| wersjonowanie i integracja z repo | 3 | 5 | 2 | 3 |
| próg wejścia | 3 | 4 | 5 | 3 |
| eksport / trwałość | 2 | 4 | 4 | 4 |
| **Suma ważona** | | **60** | **51** | **46** |

### Obszar: diagramy UML / BPMN

| Kryterium | Waga | Mermaid | draw.io | PlantUML |
|---|---|---|---|---|
| koszt i licencja | 3 | 5 | 5 | 5 |
| praca wielu osób | 2 | 4 | 3 | 4 |
| wersjonowanie i integracja z repo | 3 | 5 | 3 | 3 |
| próg wejścia | 3 | 4 | 5 | 3 |
| eksport / trwałość | 2 | 4 | 5 | 4 |
| **Suma ważona** | | **58** | **55** | **49** |

### Obszar: model danych

| Kryterium | Waga | Mermaid (diagram ER / klas) | dbdiagram.io |
|---|---|---|---|
| koszt i licencja | 3 | 5 | 3 |
| praca wielu osób | 2 | 4 | 4 |
| wersjonowanie i integracja z repo | 3 | 5 | 4 |
| próg wejścia | 3 | 4 | 4 |
| eksport / trwałość | 2 | 4 | 3 |
| **Suma ważona** | | **58** | **47** |

### Obszar: projekt interfejsu

| Kryterium | Waga | Figma (z generowaniem ekranów w Google Stitch) | Penpot |
|---|---|---|---|
| koszt i licencja | 3 | 4 | 5 |
| praca wielu osób | 2 | 5 | 4 |
| wersjonowanie i integracja z repo | 3 | 2 | 2 |
| próg wejścia | 3 | 4 | 3 |
| eksport / trwałość | 2 | 4 | 4 |
| **Suma ważona** | | **48** | **46** |

Wynik macierzy to argument, a nie wyrocznia. W obszarze interfejsu różnica jest niewielka, a Figma wygrywa głównie dzięki łatwiejszemu startowi z generowaniem ekranów w Google Stitch.

## Decyzja

| Obszar              | Narzędzie                                                                                         | Format plików w repozytorium                                                                                            |
| ------------------- | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| repozytorium        | Git + GitHub (organizacja), GitHub Desktop jako klient dla osób bez doświadczenia z linią poleceń | repozytorium Git                                                                                                        |
| zadania             | GitHub Projects + Issues                                                                          | karty na tablicy w organizacji, powiązane z pull requestami                                                             |
| dokumentacja        | Markdown w katalogu `docs/` (edycja m.in. w Obsidian i w edytorze GitHub)                         | pliki `.md`                                                                                                             |
| diagramy UML / BPMN | Mermaid; złożone diagramy: draw.io                                                                | blok `mermaid` w pliku `.md`; ewentualnie `.drawio` + eksport PNG w `docs/diagramy/`                                    |
| model danych        | Mermaid (diagram ER / klas); format zapisu gry opisany w `contract/`                              | `.md` z diagramem; opis formatu w `contract/`                                                                           |
| interfejs           | Figma; wstępne ekrany generowane w Google Stitch                                                  | eksport PNG/PDF w `design/mockups/`, link w `design/figma-link.md`, plik `design/DESIGN.md` (paleta, czcionki, odstępy) |
| komunikacja         | Telegram                                                                                          | nie dotyczy                                                                                                             |

Narzędzia open source użyte w projekcie: Git, Mermaid, draw.io.

## Konsekwencje

Co zyskujemy:
- Dokumentacja, zadania i kod są w jednym miejscu, z historią zmian i widocznym wkładem każdej osoby.
- Brak kosztów licencji i niski próg wejścia dla całego zespołu.
- Diagramy w Mermaid można edytować jak tekst i przeglądać zmiany w pull requestach.

Co tracimy / jakie są ryzyka:
- Mermaid ma ograniczone możliwości dla części diagramów UML. Dla takich przypadków przewidziano draw.io.
- Pliki Figma nie są wersjonowane w repozytorium. W repozytorium trzymamy tylko eksporty i link, więc zmiany w projekcie graficznym trzeba zgłaszać w komunikatorze lub pull requestach.
- Google Stitch jest eksperymentem Google Labs: limity i funkcje (w tym eksport do Figma) mogą się zmienić. Ograniczamy ryzyko, trzymając w repozytorium eksporty gotowych makiet.
- Wynik macierzy dla interfejsu jest bliski (Figma 48, Penpot 46). Jeśli Figma lub Stitch przestaną być dostępne, przechodzimy na Penpot.
- Obsidian jest narzędziem własnościowym (używanym tylko jako edytor plików Markdown), więc nie jest wymagany do pracy.
- Wybór technologii programistycznej odłożono do ADR-002.

Co musimy zrobić:
- Dodać `.obsidian/` do `.gitignore` oraz ustawić w Obsidian zwykłe linki Markdown (nie wikilinki). (Arsenii)
- Przygotować krótką instrukcję pracy z GitHub Desktop dla zespołu. (Arsenii)
- Utworzyć `design/figma-link.md` i `design/DESIGN.md` po wygenerowaniu pierwszych ekranów. (Daryna K.)
- Napisać ADR-002 (technologia) po wykonaniu prototypu. (Arsenii)