# Wymagania — Modde

**Wersja:** 0.2
**Autorzy:** Arsenii Liapin, Bekzigit Kuatbek, Daryna Melnyk, Daryna Kotiash, Temirlan Kalibekov

## Zasady wypełniania

- Każdy wypełnia tylko sekcje, przy których jest podpisany. Numery ID nadajemy po kolei i raz, potem ich nie zmieniamy.
- Źródłem każdego wymagania jest co najmniej jedna potrzeba N-xx z sekcji „Potrzeby”. Terminy muszą być zgodne ze słownikiem (`docs/02-slownik.md`).
- Unikamy słów-pułapek: „szybko”, „intuicyjnie”, „itp.”, „wszystkie”, „w miarę możliwości”, „obsługa”, „zarządzanie”. Jedno wymaganie opisuje jedną rzecz.

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

| ID    | Treść                                                                                                                                                   | Źródło         | Priorytet | Uwagi        |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | --------- | ------------ |
| FR-01 | System umożliwia Twórcy gier dodanie klocka do programu z klocków metodą „przeciągnij i upuść” na ekranie dotykowym telefonu.                           | N-02, N-07     | Must      | BR-02        |
| FR-02 | System umożliwia Twórcy gier przypisanie programu z klocków do jednego ze zdarzeń: początek gry, każda klatka, dotknięcie ekranu, kolizja, upływ czasu. | N-03           | Must      | BR-05        |
| FR-03 | System umożliwia Twórcy gier zmianę wartości zmiennej za pomocą klocka, np. zwiększenie wyniku o 1.                                                     | N-05           | Must      | BR-02        |
| FR-04 | System umożliwia Twórcy gier użycie warunku, który wykonuje wskazane klocki tylko wtedy, gdy sprawdzane pytanie ma odpowiedź twierdzącą.                | N-05           | Must      | BR-02        |
| FR-05 | System umożliwia Twórcy gier użycie pętli, która powtarza wskazane klocki określoną liczbę razy lub dopóki warunek jest spełniony.                      | N-05           | Must      | BR-02        |
| FR-06 | System umożliwia Twórcy gier zmianę położenia x i y obiektu gry za pomocą klocka.                                                                       | N-03           | Must      | BR-02        |
| FR-07 | System umożliwia Twórcy gier sprawdzenie za pomocą klocka, czy obiekt gry ma kolizję z obiektem gry wskazanego typu.                                    | karta projektu | Should    | BR-02        |
| FR-08 | System umożliwia Twórcy gier umieszczenie obiektu gry w scenie.                                                                                         | N-03           | Must      |              |
| FR-09 | System umożliwia Twórcy gier wybór grafiki obiektu lub tła z biblioteki grafik.                                                                         | karta projektu | Should    |              |
| FR-10 | System umożliwia Twórcy gier uruchomienie gry bezpośrednio w edytorze.                                                                                  | N-01, N-05     | Must      | BR-05        |
| FR-11 | System zatrzymuje uruchomioną grę po naciśnięciu przycisku „Stop”, zachowując program z klocków bez zmian.                                              | N-04           | Must      |              |
| FR-12 | System przerywa wykonywanie programu z klocków, w którym pętla nie kończy się w ciągu jednej klatki, bez utraty projektu gry.                           | N-04           | Could     |              |
| FR-13 | System wyświetla Twórcy gier komunikat o błędzie w programie z klocków ze wskazaniem klocka, którego błąd dotyczy.                                      | N-08           | Should    |              |
| FR-14 | System wyświetla w trakcie gry aktualną wartość zmiennej wybranej przez Twórcę gier, np. wyniku.                                                        | N-05, N-12     | Should    |              |
| FR-15 | System umożliwia Twórcy gier zapis projektu gry na urządzeniu.                                                                                          | karta projektu | Must      | BR-03        |
| FR-16 | System umożliwia Twórcy gier wczytanie zapisanego projektu gry z urządzenia.                                                                            | karta projektu | Should    | BR-03        |
| FR-17 | System umożliwia Twórcy gier eksport projektu gry do pliku jako wyeksportowanej gry.                                                                    | N-11           | Must      | BR-04        |
| FR-18 | System umożliwia Odbiorcy gry uruchomienie wyeksportowanej gry na innym telefonie niż ten, na którym ją utworzono.                                      | N-11           | Must      | BR-01, BR-04 |
| FR-19 | System umożliwia Odbiorcy gry sterowanie obiektem gry przez dotknięcie ekranu.                                                                          | N-12           | Should    |              |
| FR-20 | System umożliwia Twórcy gier otwarcie jednego z dwóch przykładowych projektów gry: gry z widokiem z góry lub prostej platformówki.                      | karta projektu | Could     |              |
| FR-21 | System umożliwia Twórcy gier korzystanie z edytora i uruchamianie gier także na komputerze, w tej samej aplikacji.                                      | karta projektu | Should    |              |
## Wymagania niefunkcjonalne (NFR): Daryna K.

| ID | Kategoria (ISO/IEC 25010) | Treść (mierzalna) | Źródło | Priorytet | Uwagi (sposób sprawdzenia) |
|---|---|---|---|---|---|
| NFR-01 | wydajność | Reakcja obiektu gry na dotknięcie ekranu przez Odbiorcę gry jest widoczna na ekranie nie później niż 100 ms po dotknięciu, w scenie z 50 obiektami gry, na telefonie z Androidem z 3 GB pamięci RAM. | N-12 | Should | Pomiar na telefonie z Androidem: 20 dotknięć, w co najmniej 19 z nich czas ≤ 100 ms. Wartość 100 ms oraz parametry telefonu: wartość założona przez zespół, do potwierdzenia. |
| NFR-02 | wydajność | W trakcie uruchomionej gry system rysuje średnio co najmniej 30 klatek na sekundę, w scenie z 50 obiektami gry, przez 5 minut ciągłej gry, na telefonie z Androidem z 3 GB pamięci RAM. | N-01, karta projektu | Should | Pomiar liczby klatek na sekundę na telefonie z Androidem w 3 uruchomieniach po 5 minut. Wartości 30 klatek, 50 obiektów, 5 minut i 3 GB: wartość założona przez zespół, do potwierdzenia. |
| NFR-03 | niezawodność | Od naciśnięcia przycisku „Stop” do zatrzymania uruchomionej gry mija nie więcej niż 1 sekunda, także gdy program z klocków zawiera pętlę, która nie kończy się, a po zatrzymaniu liczba klocków w programie z klocków jest równa liczbie sprzed uruchomienia (0 utraconych klocków). | N-04 | Must | Test na 10 programach z klocków z pętlą bez końca, na telefonie z Androidem: 10 z 10 zatrzymań w czasie ≤ 1 s i 0 utraconych klocków. Wartość 1 s: wartość założona przez zespół, do potwierdzenia. |
| NFR-04 | użyteczność | Twórca gier, który wcześniej nie używał aplikacji, w ciągu 60 minut od pierwszego uruchomienia samodzielnie tworzy prosty interaktywny projekt (obiekt gry, który porusza się po zdarzeniu „dotknięcie ekranu”); wymaganie spełnia co najmniej 4 z 5 uczniów. | N-03 | Must | Test na 5 uczniach podczas lekcji pilotażowej, czas mierzony stoperem. Próg 60 minut wynika z wywiadu (pytanie 2); próg 4 z 5 uczniów: wartość założona przez zespół, do potwierdzenia. |
| NFR-05 | użyteczność | Każdy klocek i przycisk „Stop” w edytorze ma obszar dotyku co najmniej 9 × 9 mm na ekranie telefonu o przekątnej 5,5 cala, a Twórca gier trafia w wybrany element w co najmniej 9 na 10 prób. | N-07, N-04 | Should | Pomiar rozmiaru elementów na telefonie z Androidem oraz test na 5 uczniach (po 10 prób każdy). Wartości 9 mm i 9 na 10: wartość założona przez zespół, do potwierdzenia. |
| NFR-06 | użyteczność | Komunikat o błędzie w programie z klocków pojawia się w ciągu 2 sekund od uruchomienia gry i pozwala co najmniej 4 z 5 uczniów wskazać błędny klocek w ciągu 2 minut, bez pomocy innej osoby. | N-08 | Should | Test na 5 uczniach z 3 programami z klocków zawierającymi błąd, czas mierzony stoperem. Wartości 2 s, 2 minuty i 4 z 5: wartość założona przez zespół, do potwierdzenia. |
| NFR-07 | kompatybilność | Edytor wyświetla się w całości, bez obciętych klocków i przycisków, na ekranach telefonów o przekątnej od 5,0 do 6,7 cala, w orientacji pionowej i poziomej. | N-07 | Should | Sprawdzenie na 3 telefonach z Androidem o przekątnych 5,0; 5,5 i 6,7 cala: 0 obciętych elementów. Zakres przekątnych: wartość założona przez zespół, do potwierdzenia. |
| NFR-08 | kompatybilność | Wyeksportowana gra otwiera się i uruchamia na innym telefonie z Androidem niż ten, na którym ją utworzono, w 10 z 10 prób, po przesłaniu pliku przez komunikator. | N-11, karta projektu | Must | Test na 2 różnych telefonach z Androidem, 10 prób. Liczba prób i sposób przesłania pliku: wartość założona przez zespół, do potwierdzenia. |
| NFR-09 | przenośność | Aplikację można uruchomić na komputerze z kontem bez uprawnień administratora, na którym instalowanie programów jest zablokowane, wykonując nie więcej niż 3 czynności Twórcy gier od pobrania aplikacji do widoku edytora. | N-06, karta projektu | Should | Test w pracowni szkolnej na komputerze z zablokowaną instalacją, 3 próby, liczenie czynności. Wartość 3 czynności: wartość założona przez zespół, do potwierdzenia. |
| NFR-10 | bezpieczeństwo | W ciągu 30 minut użytkowania aplikacji (układanie programu z klocków, zapis projektu gry, uruchomienie gry, eksport) system wysyła poza urządzenie 0 bajtów danych Twórcy gier. | karta projektu | Must | Test na telefonie z Androidem z rejestrowaniem ruchu sieciowego przez 30 minut: 0 połączeń wychodzących z danymi Twórcy gier. Czas 30 minut: wartość założona przez zespół, do potwierdzenia. |

## Reguły biznesowe (BR): Temirlan

| ID    | Reguła                                                                                                                       | Źródło                                              | Uwagi (których FR dotyczy)               |
| ----- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- | ---------------------------------------- |
| BR-01 | Odbiorca gry może tylko uruchomić wyeksportowaną grę, nie może jej zmieniać.                                                 | słownik: Odbiorca gry                               | FR-18                                    |
| BR-02 | Twórca gier układa program wyłącznie ze stałego zestawu klocków i nie może dodawać własnych.                                 | karta projektu, „Zakres IN” i „Główne założenia”    | FR-01, FR-03, FR-04, FR-05, FR-06, FR-07 |
| BR-03 | Projekt gry jest zapisywany wyłącznie lokalnie na urządzeniu Twórcy gier, bez kont użytkowników.                             | karta projektu, „Główne założenia”                  | FR-15, FR-16                             |
| BR-04 | Odbiorca gry otrzymuje wyeksportowaną grę od Twórcy gier jako plik, bez publikacji w sklepach z aplikacjami.                 | słownik: Odbiorca gry; karta projektu, „Zakres OUT” | FR-17, FR-18                             |
| BR-05 | Obiekt gry wykonuje przypisany mu program z klocków dopiero wtedy, gdy wystąpi zdarzenie, do którego ten program przypisano. | słownik: Zdarzenie                                  | FR-02, FR-10                             |
| BR-06 | Dane osobowe użytkowników nie są zbierane ani przetwarzane.                                                                  | karta projektu, „Główne założenia”                  | brak FR; zob. NFR-10                     |

## Ograniczenia: Daryna K.

- Aplikacja musi działać na telefonie z systemem Android oraz na komputerze (uzasadnienie: poza szkołą uczniowie mają głównie smartfon, a w pracowni szkolnej komputery stacjonarne lub laptopy; wywiad-1, pytanie 9, N-07, karta projektu)
- Na szkolnych komputerach nie można zakładać możliwości instalowania nowych programów (uzasadnienie: instalowanie nowych programów na szkolnych komputerach bywa zablokowane; wywiad-1, pytanie 6, N-06)
- Grafiki obiektów gry i teł muszą pochodzić z zasobów przygotowanych przez zespół lub z otwartych źródeł, na licencjach dopuszczających takie użycie (uzasadnienie: projekt korzysta z gotowego zestawu grafik, a warunki licencji narzucają ich autorzy; karta projektu, sekcja „Główne założenia”)
- Dokumentacja powstaje w pierwszym semestrze, a kod aplikacji w drugim, a zakres projektu zatwierdza prowadzący przedmiot (uzasadnienie: terminy i zasady oceny wynikają z przedmiotu; karta projektu, sekcje „Interesariusze” i „Wstępne ryzyka”)
- Projekt realizuje zespół pięciu osób (uzasadnienie: skład zespołu jest wskazany w karcie projektu, a zakres musi być wykonalny dla tego składu)
- Wybór technologii jest wstępny i wymaga potwierdzenia po wykonaniu prototypu (uzasadnienie: do potwierdzenia w ADR-002; karta projektu, sekcja „Wstępnie rozważane technologie”)

## Historyjki użytkownika: Daryna K.

#### US-01: Układanie programu z klocków i przypisanie go do zdarzenia
Wymagania: FR-01, FR-02, BR-02, BR-05 · Priorytet: Must

#### US-02: Zmiana zmiennej i reakcja za pomocą warunku
Wymagania: FR-03, FR-04, BR-02 · Priorytet: Must

#### US-03: Powtarzanie klocków za pomocą pętli
Wymagania: FR-05, BR-02 · Priorytet: Must

#### US-04: Umieszczenie obiektu gry w scenie i zmiana jego położenia
Wymagania: FR-06, FR-08, BR-02 · Priorytet: Must

#### US-05: Uruchomienie gry w edytorze
Wymagania: FR-10, BR-05 · Priorytet: Must

## Historyjki użytkownika: Daryna M.

#### US-06: Zatrzymanie uruchomionej gry przyciskiem „Stop”
Wymagania: FR-11, NFR-03 · Priorytet: Must

**Jako** Twórca gier **chcę** zatrzymać uruchomioną grę, **aby** nie stracić dotychczasowej pracy, gdy program z klocków się zawiesi.

Kryteria akceptacji:
- **Scenariusz 1: Zatrzymanie działającej gry**
  - **Given** uruchomiłem grę w edytorze, a program z klocków zawiera 12 klocków,
  - **When** naciskam przycisk „Stop”,
  - **Then** uruchomiona gra zostaje zatrzymana.
- **Scenariusz 2: Pętla, która się nie kończy**
  - **Given** uruchomiłem grę, w której program z klocków zawiera pętlę, która się nie kończy,
  - **When** naciskam przycisk „Stop”,
  - **Then** gra zostaje zatrzymana nie później niż 1 sekundę po naciśnięciu przycisku (NFR-03).
- **Scenariusz 3: Program z klocków po zatrzymaniu**
  - **Given** program z klocków zawierał 12 klocków przed uruchomieniem gry, a gra została zatrzymana przyciskiem „Stop”,
  - **When** wracam do programu z klocków,
  - **Then** program z klocków nadal zawiera 12 klocków, czyli 0 utraconych klocków (NFR-03).

#### US-07: Zapis projektu gry na urządzeniu
Wymagania: FR-15, BR-03 · Priorytet: Must

**Jako** Twórca gier **chcę** zapisać projekt gry na swoim urządzeniu, **aby** móc go później wczytać i dalej zmieniać.

Kryteria akceptacji:
- **Scenariusz 1: Zapis projektu gry**
  - **Given** ułożyłem program z klocków w projekcie gry „Las”,
  - **When** zapisuję projekt gry,
  - **Then** projekt gry „Las” jest zapisany na moim urządzeniu.
- **Scenariusz 2: Zapis bez konta użytkownika**
  - **Given** nie mam konta użytkownika i nie jestem zalogowany,
  - **When** zapisuję projekt gry „Las”,
  - **Then** projekt gry zostaje zapisany lokalnie na urządzeniu, bez prośby o założenie konta lub zalogowanie (BR-03).

#### US-08: Eksport gry do pliku
Wymagania: FR-17, BR-04 · Priorytet: Must

**Jako** Twórca gier **chcę** wyeksportować projekt gry do pliku, **aby** wysłać grę koledze tak, żeby otworzyła się na jego telefonie.

Kryteria akceptacji:
- **Scenariusz 1: Eksport projektu gry**
  - **Given** mam zapisany projekt gry „Las”,
  - **When** eksportuję projekt gry,
  - **Then** na moim urządzeniu powstaje plik wyeksportowanej gry „Las”.
- **Scenariusz 2: Przekazanie gry jako pliku**
  - **Given** mam plik wyeksportowanej gry „Las”,
  - **When** przesyłam ten plik Odbiorcy gry przez komunikator,
  - **Then** Odbiorca gry otrzymuje grę jako plik, bez publikacji gry w sklepie z aplikacjami (BR-04).

#### US-09: Uruchomienie otrzymanej gry przez Odbiorcę gry
Wymagania: FR-18, BR-01, BR-04, NFR-08 · Priorytet: Must

**Jako** Odbiorca gry **chcę** uruchomić grę otrzymaną od Twórcy gier na swoim telefonie, **aby** zagrać w nią, mimo że przesłane pliki nie zawsze otwierają się na innym urządzeniu.

Kryteria akceptacji:
- **Scenariusz 1: Uruchomienie otrzymanej gry**
  - **Given** otrzymałem przez komunikator plik wyeksportowanej gry „Las” utworzonej na innym telefonie,
  - **When** otwieram ten plik na swoim telefonie,
  - **Then** gra „Las” uruchamia się.
- **Scenariusz 2: Próba zmiany otrzymanej gry**
  - **Given** uruchomiłem otrzymaną wyeksportowaną grę „Las”,
  - **When** próbuję zmienić program z klocków tej gry,
  - **Then** system nie pozwala na zmianę i gra pozostaje taka, jaką przygotował Twórca gier (BR-01).
- **Scenariusz 3: Gra bez sklepu z aplikacjami**
  - **Given** otrzymałem wyeksportowaną grę „Las” jako plik, a gra nie jest opublikowana w sklepie z aplikacjami,
  - **When** otwieram ten plik,
  - **Then** gra uruchamia się bez pobierania jej ze sklepu z aplikacjami (BR-04).
- **Scenariusz 4: Uruchomienie na innym telefonie z Androidem**
  - **Given** plik wyeksportowanej gry „Las” przesłano przez komunikator 10 razy na inny telefon z Androidem,
  - **When** Odbiorca gry otwiera plik po każdym przesłaniu,
  - **Then** gra uruchamia się w 10 z 10 prób (NFR-08).

## Pytania otwarte: Temirlan

| Nr   | Pytanie                                                                                                                                      | Do kogo | Issue           | Status         |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------- | ------- | --------------- | -------------- |
| Q-01 | Jakie dokładnie funkcje i jaki interfejs są dla klienta niezbędne? Klient zaznaczył, że zakres pozostaje do doprecyzowania (Pytanie 1).      | klient  | do uzupełnienia | do sprawdzenia |
| Q-02 | Czy po użyciu przycisku awaryjnego zatrzymania gra wraca do stanu początkowego, czy zostaje w stanie, w którym ją zatrzymano (Pytanie 4)?    | klient  | do uzupełnienia | do sprawdzenia |
| Q-03 | Czy uczniowie mogą korzystać z własnych telefonów na lekcji, skoro klient wskazuje rozpraszanie się i problem z regulaminem (Pytania 9, 10)? | klient  | do uzupełnienia | do sprawdzenia |
| Q-04 | W jaki sposób uczeń ma dokończyć w domu na telefonie pracę zaczętą na szkolnym komputerze (Pytania 8, 15)?                                   | klient  | do uzupełnienia | do sprawdzenia |
| Q-05 | Ile czasu uczniowie utrzymują skupienie na jednym zadaniu? Odpowiedź wymaga lekcji pilotażowej (Pytanie 12).                                 | klient  | do uzupełnienia | do sprawdzenia |
| Q-06 | Jak dziś stopniuje Pan/Pani trudność zadań dla uczniów o różnym poziomie umiejętności? (N-09)                                                | klient  | do uzupełnienia | do sprawdzenia |
| Q-07 | Jak uczniowie uruchamiają dziś programy w pracowni, skoro na szkolnych komputerach instalowanie nowych programów bywa zablokowane? (N-06)    | klient  | do uzupełnienia | do sprawdzenia |
| Q-08 | Kto albo co podpowiada dziś uczniowi w domu, co poszło nie tak w jego pracy? (N-08)                                                          | klient  | do uzupełnienia | do sprawdzenia |
| Q-09 | Co powinien zobaczyć kolega, który po raz pierwszy uruchamia czyjąś grę, żeby od razu wiedzieć, co ma robić? (N-12)                          | klient  | do uzupełnienia | do sprawdzenia |
| Q-10 | Co dokładnie rozumie Pan/Pani przez animację w pierwszym projekcie ucznia? (N-03)                                                            | klient  | do uzupełnienia | do sprawdzenia |
