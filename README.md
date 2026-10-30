# Modde: mobilny silnik gier typu „przeciągnij i upuść" do nauki programowania

Modde to mobilny, polskojęzyczny silnik gier oparty na klockach. Pozwala początkującym tworzyć własne gry 2D na telefonie z Androidem i uczyć się przy tym podstaw algorytmów. Użytkownik buduje mechanikę gry (ruch, kolizje, punkty) samodzielnie z klocków niskiego poziomu: zmiennych, zdarzeń, warunków, pętli i sprawdzania kolizji.

Projekt powstaje w ramach zajęć „Projekt zespołowy systemu informatycznego".

## Zespół
| Osoba              | Główna odpowiedzialność                                                        | Login                   |
| ------------------ | ------------------------------------------------------------------------------ | ----------------------- |
| Arsenii Liapin     | koordynacja projektu, architektura, dokumentacja, jądro interpretera i edytora | @LiapinArsenii          |
| Bekzigit Kuatbek   | Elementy pierwotne edytora i interpretera                                      | @kuatbekulybeles-sketch |
| Daryna Melnyk      | runner (wyświetlanie gry), testy                                               | @melnukdarina1111-blip  |
| Daryna Kotiash     | projekt graficzny i UI                                                         | @daritiash              |
| Temirlan Kalibekov | zapis i eksport projektów, model danych                                        | @timakalibekov          |
## Dokumentacja

- [Karta projektu](docs/01-karta-projektu.md)
- [Słownik](docs/02-slownik.md)
- [Wymagania](docs/03-wymagania.md)
- [Diagram kontekstu](docs/06-architektura/kontekst.md)
- [Decyzje projektowe (ADR)](docs/adr/)

## Narzędzia

Zob. [ADR-001](docs/adr/ADR-001-narzedzia.md).

## Struktura repozytorium

- `docs/`: dokumentacja projektu
- `editor/`: edytor programów z klocków
- `editor/blocks/`: Elementy pierwotne edytora
- `interpreter/`: wykonywanie programów ułożonych z klocków
- `interpreter/blocks/`: Elementy pierwotne interpretera
- `runner/`: wyświetlanie gry na ekranie
- `storage/`: zapis, wczytywanie i eksport projektów
- `contract/`: uzgodnione formaty danych między częściami systemu
- `design/`: grafika i makiety

## Status

Projekt jest na etapie analizy i dokumentacji. Kod aplikacji powstanie w kolejnym semestrze.

Wersja dokumentacji: 0.3

## Zasady pracy zespołu

Zob. [TEAM.md](TEAM.md) (po rosyjsku, dla zespołu).