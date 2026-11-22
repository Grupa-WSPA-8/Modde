# Przypadki użycia — Modde

Poniżej znajduje się lista kandydatów na przypadki użycia wyprowadzonych z historyjek użytkownika, a pełne opisy przypadków użycia powstaną na zajęciach 7–8.

## Aktorzy

| Aktor | Opis | Źródło |
|---|---|---|
| Twórca gier | Osoba, która w Modde układa program z klocków, testuje go i eksportuje własną grę. | karta projektu, sekcja 5; słownik: Twórca gier |
| Odbiorca gry | Osoba, która otrzymuje gotową grę od twórcy i uruchamia ją na swoim telefonie, bez możliwości jej zmieniania. | karta projektu, sekcja 5; słownik: Odbiorca gry |

## Kandydaci na przypadki użycia

Kandydaci wyprowadzeni z historyjek US-01…US-10:

| ID | Kandydat | Aktor | Historyjki | Wymagania |
|---|---|---|---|---|
| UC-01 | Utwórz nowy projekt gry | Twórca gier | US-10 | FR-22, BR-03 |
| UC-02 | Umieść obiekt gry w scenie | Twórca gier | US-04 | FR-06, FR-08, BR-02 |
| UC-03 | Ułóż program z klocków | Twórca gier | US-01, US-02, US-03 | FR-01, FR-02, FR-03, FR-04, FR-05, BR-02, BR-05 |
| UC-04 | Uruchom grę w edytorze | Twórca gier | US-05 | FR-10, BR-05 |
| UC-05 | Zatrzymaj uruchomioną grę | Twórca gier | US-06 | FR-11, NFR-03 |
| UC-06 | Zapisz projekt gry | Twórca gier | US-07 | FR-15, BR-03 |
| UC-07 | Eksportuj grę | Twórca gier | US-08 | FR-17, BR-04 |
| UC-08 | Uruchom otrzymaną grę | Odbiorca gry | US-09 | FR-18, BR-01, BR-04, NFR-08 |

Kandydaci wyprowadzeni z wymagań funkcjonalnych, dla których nie ma historyjki:

| ID | Kandydat | Aktor | Historyjki | Wymagania |
|---|---|---|---|---|
| UC-09 | Wczytaj projekt gry | Twórca gier | — (bez historyjki) | FR-16, FR-23, BR-03 |
| UC-10 | Otwórz przykładowy projekt gry | Twórca gier | — (bez historyjki) | FR-20 |
| UC-11 | Wybierz grafikę obiektu | Twórca gier | — (bez historyjki) | FR-09 |
| UC-12 | Steruj obiektem gry dotykiem | Odbiorca gry | — (bez historyjki) | FR-19 |