## Zasady wypełniania

- Każdy wypełnia tylko sekcje, przy których jest podpisany. Numery ID nadajemy po kolei i raz, potem ich nie zmieniamy.
- Źródłem każdego wymagania jest co najmniej jedna potrzeba N-xx z sekcji „Potrzeby”. Terminy muszą być zgodne ze słownikiem (`docs/02-slownik.md`).
- Unikamy słów-pułapek: „szybko”, „intuicyjnie”, „itp.”, „wszystkie”, „w miarę możliwości”, „obsługa”, „zarządzanie”. Jedno wymaganie opisuje jedną rzecz.
- Kolumnę „Priorytet” zostawiamy pustą. Uzupełnia ją Arsenii po ustaleniu MoSCoW.

## Potrzeby: Daryna M.

| ID | Potrzeba (językiem klienta) | Typ | Kto zgłosił | Źródło |
|---|---|---|---|---|
| N-01 | Brakuje nam czegoś, dzięki czemu uczniowie od razu zobaczą, jak kroki algorytmu działają w prawdziwej grze. | potrzeba | Nauczyciel | wywiad-1, pytanie 5 |
| N-02 | Wizualne środowisko programowania na wzór Scratcha → uczeń od razu tworzy proste skrypty. | rozwiązanie | Nauczyciel | wywiad-1, pytanie 1 |
| N-03 | Po pierwszej godzinie uczeń ma stworzyć prosty interaktywny projekt: podstawowy ruch, animację lub reakcję na zdarzenie. | potrzeba | Nauczyciel | wywiad-1, pytanie 2 |
| N-04 | Widoczny i łatwo dostępny przycisk „Stop” / reset musi przerwać nieskończoną pętlę bez utraty dotychczasowej pracy ucznia. | żądanie | Twórca gier | wywiad-1, pytanie 4 |
| N-05 | Uczniowie mylą warunek z pętlą i nie rozumieją, że zmienna, np. liczba punktów, zmienia się w trakcie gry; pomaga, gdy od razu widzą efekt na ekranie. | potrzeba | Nauczyciel | wywiad-1, pytanie 7 |
| N-06 | Na szkolnych komputerach instalowanie nowych programów bywa zablokowane. | potrzeba | Nauczyciel | wywiad-1, pytanie 6 |
| N-07 | W domu uczeń ma tylko telefon, a ćwiczenia są przygotowane pod komputer, więc na małym ekranie trudno je wykonać. | potrzeba | Twórca gier | wywiad-1, pytanie 8 |
| N-08 | W domu nikt nie podpowie uczniowi, co poszło nie tak, więc szybko się zniechęca i odkłada zadanie. | potrzeba | Twórca gier | wywiad-1, pytanie 8 |
| N-09 | Uczniowie łatwo tracą cierpliwość, dlatego potrzebne jest stopniowanie trudności zadań (poza zakresem). | potrzeba | Nauczyciel | wywiad-1, pytanie 11 |
| N-10 | Praca zostaje na szkolnym komputerze, a uczeń chce ją dokończyć w domu na telefonie. | potrzeba | Twórca gier | wywiad-1, pytanie 15 |
| N-11 | Pliki wysyłane przez komunikator nie zawsze udaje się otworzyć na innym urządzeniu. | potrzeba | Twórca gier | wywiad-1, pytanie 13 |
| N-12 | Odbiorca od razu chce widzieć, co jest jego postacią, co dzieje się po dotknięciu ekranu i jaki ma wynik. | potrzeba | Odbiorca gry | wywiad-1, pytanie 16 |

## Wymagania funkcjonalne (FR): Daryna M.

| ID | Treść | Źródło | Priorytet | Uwagi |
|---|---|---|---|---|
| FR-01 | System umożliwia Twórcy gier dodanie klocka do programu z klocków metodą „przeciągnij i upuść” na ekranie dotykowym telefonu. | N-02, N-07 |  |  |
| FR-02 | System umożliwia Twórcy gier przypisanie programu z klocków do jednego ze zdarzeń: początek gry, każda klatka, dotknięcie ekranu, kolizja, upływ czasu. | N-03 |  |  |
| FR-03 | System umożliwia Twórcy gier zmianę wartości zmiennej za pomocą klocka, np. zwiększenie wyniku o 1. | N-05 |  |  |
| FR-04 | System umożliwia Twórcy gier użycie warunku, który wykonuje wskazane klocki tylko wtedy, gdy sprawdzane pytanie ma odpowiedź twierdzącą. | N-05 |  |  |
| FR-05 | System umożliwia Twórcy gier użycie pętli, która powtarza wskazane klocki określoną liczbę razy lub dopóki warunek jest spełniony. | N-05 |  |  |
| FR-06 | System umożliwia Twórcy gier zmianę położenia x i y obiektu gry za pomocą klocka. | N-03 |  |  |
| FR-07 | System umożliwia Twórcy gier sprawdzenie za pomocą klocka, czy obiekt gry ma kolizję z obiektem gry wskazanego typu. | karta projektu |  |  |
| FR-08 | System umożliwia Twórcy gier umieszczenie obiektu gry w scenie. | N-03 |  |  |
| FR-09 | System umożliwia Twórcy gier wybór grafiki obiektu lub tła z biblioteki grafik. | karta projektu |  |  |
| FR-10 | System umożliwia Twórcy gier uruchomienie gry bezpośrednio w edytorze. | N-01, N-05 |  |  |
| FR-11 | System zatrzymuje uruchomioną grę po naciśnięciu przycisku „Stop”, zachowując program z klocków bez zmian. | N-04 |  |  |
| FR-12 | System przerywa wykonywanie programu z klocków, w którym pętla nie kończy się w ciągu jednej klatki, bez utraty projektu gry. | N-04 |  |  |
| FR-13 | System wyświetla Twórcy gier komunikat o błędzie w programie z klocków ze wskazaniem klocka, którego błąd dotyczy. | N-08 |  |  |
| FR-14 | System wyświetla w trakcie gry aktualną wartość zmiennej wybranej przez Twórcę gier, np. wyniku. | N-05, N-12 |  |  |
| FR-15 | System umożliwia Twórcy gier zapis projektu gry na urządzeniu. | karta projektu |  |  |
| FR-16 | System umożliwia Twórcy gier wczytanie zapisanego projektu gry z urządzenia. | karta projektu |  |  |
| FR-17 | System umożliwia Twórcy gier eksport projektu gry do pliku jako wyeksportowanej gry. | N-11 |  |  |
| FR-18 | System umożliwia Odbiorcy gry uruchomienie wyeksportowanej gry na innym telefonie niż ten, na którym ją utworzono. | N-11 |  |  |
| FR-19 | System umożliwia Odbiorcy gry sterowanie obiektem gry przez dotknięcie ekranu. | N-12 |  |  |
| FR-20 | System umożliwia Twórcy gier otwarcie jednego z dwóch przykładowych projektów gry: gry z widokiem z góry lub prostej platformówki. | karta projektu |  |  |

## Wymagania niefunkcjonalne (NFR): Daryna K.

| ID | Kategoria (ISO/IEC 25010) | Treść (mierzalna) | Źródło | Priorytet | Uwagi (sposób sprawdzenia) |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

## Reguły biznesowe (BR): Temirlan

| ID | Reguła | Źródło | Uwagi (których FR dotyczy) |
|---|---|---|---|
|  |  |  |  |

## Ograniczenia: Daryna K.

- 
## Historyjki użytkownika: Daryna K.

- (do uzupełnienia)
## Historyjki użytkownika: Temirlan

- (do uzupełnienia)
## Pytania otwarte: Temirlan

| Nr | Pytanie | Do kogo | Issue | Status |
|---|---|---|---|---|
|  |  |  |  |  |
