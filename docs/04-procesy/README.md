# Procesy biznesowe — Modde

Ten folder zawiera opisy procesów biznesowych projektu Modde. Poniżej znajduje się lista procesów, przyjęte konwencje i legenda elementów diagramów.

## Lista procesów

| ID | Nazwa | Rodzaj | Plik |
|---|---|---|---|
| P-00 | Nauka podstaw programowania w szkole | AS-IS | [P-00-nauka-programowania-as-is.md](P-00-nauka-programowania-as-is.md) |
| P-01 | Tworzenie i uruchomienie gry | TO-BE, główny | [P-01-tworzenie-i-uruchomienie-gry.md](P-01-tworzenie-i-uruchomienie-gry.md) |
| P-02 | Eksport i przekazanie gry | TO-BE | [P-02-eksport-i-przekazanie-gry.md](P-02-eksport-i-przekazanie-gry.md) |
| P-03 | Kontynuacja pracy na innym urządzeniu | TO-BE | [P-03-kontynuacja-na-innym-urzadzeniu.md](P-03-kontynuacja-na-innym-urzadzeniu.md) |

## Konwencje

- **Numeracja kroków:** każdy krok ma numer w postaci P-xx.y, gdzie P-xx to ID procesu, a y to kolejny numer kroku, np. P-03.2.
- **Tory:** tory to role ze słownika (Twórca gier, Odbiorca gry) oraz Silnik.
- **Systemy zewnętrzne:** każdy system zewnętrzny jest osobną, zwiniętą pulą.
- **Nazwa kroku:** czasownik i rzeczownik, bez nazw elementów ekranu, np. „Zapisz projekt gry”.
- **Wyniki:** każdy wynik procesu jest osobnym zdarzeniem końcowym.
- **Format diagramów:** główny proces TO-BE (P-01) jest opisany w BPMN, z plikami .bpmn i .svg obok siebie. Pozostałe procesy są narysowane w Mermaid jako przybliżenie BPMN.

## Legenda

- **Zdarzenie początkowe:** pokazuje moment, w którym proces się zaczyna.
- **Zdarzenie końcowe:** pokazuje jeden z wyników procesu, a każdy wynik ma osobne zdarzenie.
- **Zadanie użytkownika:** krok, który wykonuje człowiek w aplikacji, np. Twórca gier układa program z klocków.
- **Zadanie usługi:** krok, który Silnik wykonuje automatycznie, bez udziału człowieka.
- **Zadanie ręczne:** krok, który człowiek wykonuje poza aplikacją, np. przenosi plik z jednego urządzenia na drugie.
- **Bramka XOR (jedna ścieżka):** rozgałęzienie, po którym proces biegnie dokładnie jedną ścieżką, zależnie od odpowiedzi na podpisane pytanie.
- **Bramka AND (wszystkie ścieżki):** rozgałęzienie, po którym proces biegnie równolegle każdą z wychodzących ścieżek.
- **Podproces:** krok złożony z kilku mniejszych kroków opisanych osobno.
- **Przepływ sekwencji:** strzałka pokazująca kolejność kroków w obrębie jednej puli.
- **Przepływ wiadomości:** strzałka pokazująca przekazanie informacji między dwiema pulami.