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
| NFR-01 | wydajność | Reakcja obiektu gry na dotknięcie ekranu przez Odbiorcę gry jest widoczna na ekranie nie później niż 100 ms po dotknięciu, w scenie z 50 obiektami gry, na telefonie z Androidem z 3 GB pamięci RAM. | N-12 |  | Pomiar na telefonie z Androidem: 20 dotknięć, w co najmniej 19 z nich czas ≤ 100 ms. Wartość 100 ms oraz parametry telefonu: wartość założona przez zespół, do potwierdzenia. |
| NFR-02 | wydajność | W trakcie uruchomionej gry system rysuje średnio co najmniej 30 klatek na sekundę, w scenie z 50 obiektami gry, przez 5 minut ciągłej gry, na telefonie z Androidem z 3 GB pamięci RAM. | N-01, karta projektu |  | Pomiar liczby klatek na sekundę na telefonie z Androidem w 3 uruchomieniach po 5 minut. Wartości 30 klatek, 50 obiektów, 5 minut i 3 GB: wartość założona przez zespół, do potwierdzenia. |
| NFR-03 | niezawodność | Od naciśnięcia przycisku „Stop” do zatrzymania uruchomionej gry mija nie więcej niż 1 sekunda, także gdy program z klocków zawiera pętlę, która nie kończy się, a po zatrzymaniu liczba klocków w programie z klocków jest równa liczbie sprzed uruchomienia (0 utraconych klocków). | N-04 |  | Test na 10 programach z klocków z pętlą bez końca, na telefonie z Androidem: 10 z 10 zatrzymań w czasie ≤ 1 s i 0 utraconych klocków. Wartość 1 s: wartość założona przez zespół, do potwierdzenia. |
| NFR-04 | użyteczność | Twórca gier, który wcześniej nie używał aplikacji, w ciągu 60 minut od pierwszego uruchomienia samodzielnie tworzy prosty interaktywny projekt (obiekt gry, który porusza się po zdarzeniu „dotknięcie ekranu”); wymaganie spełnia co najmniej 4 z 5 uczniów. | N-03 |  | Test na 5 uczniach podczas lekcji pilotażowej, czas mierzony stoperem. Próg 60 minut wynika z wywiadu (pytanie 2); próg 4 z 5 uczniów: wartość założona przez zespół, do potwierdzenia. |
| NFR-05 | użyteczność | Każdy klocek i przycisk „Stop” w edytorze ma obszar dotyku co najmniej 9 × 9 mm na ekranie telefonu o przekątnej 5,5 cala, a Twórca gier trafia w wybrany element w co najmniej 9 na 10 prób. | N-07, N-04 |  | Pomiar rozmiaru elementów na telefonie z Androidem oraz test na 5 uczniach (po 10 prób każdy). Wartości 9 mm i 9 na 10: wartość założona przez zespół, do potwierdzenia. |
| NFR-06 | użyteczność | Komunikat o błędzie w programie z klocków pojawia się w ciągu 2 sekund od uruchomienia gry i pozwala co najmniej 4 z 5 uczniów wskazać błędny klocek w ciągu 2 minut, bez pomocy innej osoby. | N-08 |  | Test na 5 uczniach z 3 programami z klocków zawierającymi błąd, czas mierzony stoperem. Wartości 2 s, 2 minuty i 4 z 5: wartość założona przez zespół, do potwierdzenia. |
| NFR-07 | kompatybilność | Edytor wyświetla się w całości, bez obciętych klocków i przycisków, na ekranach telefonów o przekątnej od 5,0 do 6,7 cala, w orientacji pionowej i poziomej. | N-07 |  | Sprawdzenie na 3 telefonach z Androidem o przekątnych 5,0; 5,5 i 6,7 cala: 0 obciętych elementów. Zakres przekątnych: wartość założona przez zespół, do potwierdzenia. |
| NFR-08 | kompatybilność | Wyeksportowana gra otwiera się i uruchamia na innym telefonie z Androidem niż ten, na którym ją utworzono, w 10 z 10 prób, po przesłaniu pliku przez komunikator. | N-11, karta projektu |  | Test na 2 różnych telefonach z Androidem, 10 prób. Liczba prób i sposób przesłania pliku: wartość założona przez zespół, do potwierdzenia. |
| NFR-09 | przenośność | Aplikację można uruchomić na komputerze z kontem bez uprawnień administratora, na którym instalowanie programów jest zablokowane, wykonując nie więcej niż 3 czynności Twórcy gier od pobrania aplikacji do widoku edytora. | N-06, karta projektu |  | Test w pracowni szkolnej na komputerze z zablokowaną instalacją, 3 próby, liczenie czynności. Wartość 3 czynności: wartość założona przez zespół, do potwierdzenia. |
| NFR-10 | bezpieczeństwo | W ciągu 30 minut użytkowania aplikacji (układanie programu z klocków, zapis projektu gry, uruchomienie gry, eksport) system wysyła poza urządzenie 0 bajtów danych Twórcy gier. | karta projektu |  | Test na telefonie z Androidem z rejestrowaniem ruchu sieciowego przez 30 minut: 0 połączeń wychodzących z danymi Twórcy gier. Czas 30 minut: wartość założona przez zespół, do potwierdzenia. |

## Reguły biznesowe (BR): Temirlan

| ID | Reguła | Źródło | Uwagi (których FR dotyczy) |
|---|---|---|---|
| BR-01 | Odbiorca gry może tylko uruchomić wyeksportowaną grę, nie może jej zmieniać. | słownik: Odbiorca gry | |
| BR-02 | Odbiorca gry otrzymuje wyeksportowaną grę od Twórcy gier. | słownik: Odbiorca gry | |
| BR-03 | Twórca gier może wczytać zapisany projekt gry i dalej go zmieniać. | słownik: Projekt gry | |
| BR-04 | Wyeksportowaną grę można udostępnić innej osobie i uruchomić na innym urządzeniu niż to, na którym ją utworzono. | słownik: Wyeksportowana gra | |
| BR-05 | Obiekt gry ma grafikę, położenie na ekranie i własne zmienne. | słownik: Obiekt gry | |
| BR-06 | Obiekt gry wykonuje przypisany mu program z klocków dopiero wtedy, gdy wystąpi zdarzenie, do którego ten program przypisano. | słownik: Zdarzenie | |
| BR-07 | Dane osobowe użytkowników nie są zbierane ani przetwarzane. | karta projektu | |

## Ograniczenia: Daryna K.

- Aplikacja musi działać na telefonie z systemem Android oraz na komputerze (uzasadnienie: poza szkołą uczniowie mają głównie smartfon, a w pracowni szkolnej komputery stacjonarne lub laptopy; wywiad-1, pytanie 9, N-07, karta projektu)
- Na szkolnych komputerach nie można zakładać możliwości instalowania nowych programów (uzasadnienie: instalowanie nowych programów na szkolnych komputerach bywa zablokowane; wywiad-1, pytanie 6, N-06)
- Grafiki obiektów gry i teł muszą pochodzić z zasobów przygotowanych przez zespół lub z otwartych źródeł, na licencjach dopuszczających takie użycie (uzasadnienie: projekt korzysta z gotowego zestawu grafik, a warunki licencji narzucają ich autorzy; karta projektu, sekcja „Główne założenia”)
- Dokumentacja powstaje w pierwszym semestrze, a kod aplikacji w drugim, a zakres projektu zatwierdza prowadzący przedmiot (uzasadnienie: terminy i zasady oceny wynikają z przedmiotu; karta projektu, sekcje „Interesariusze” i „Wstępne ryzyka”)
- Projekt realizuje zespół pięciu osób (uzasadnienie: skład zespołu jest wskazany w karcie projektu, a zakres musi być wykonalny dla tego składu)
- Wybór technologii jest wstępny i wymaga potwierdzenia po wykonaniu prototypu (uzasadnienie: do potwierdzenia w ADR-002; karta projektu, sekcja „Wstępnie rozważane technologie”)

## Historyjki użytkownika: Daryna K.

- (do uzupełnienia)
## Historyjki użytkownika: Temirlan

- (do uzupełnienia)
## Pytania otwarte: Temirlan

| Nr | Pytanie | Do kogo | Issue | Status |
|---|---|---|---|---|
| Q-01 | Jakie dokładnie funkcje i jaki interfejs są dla klienta niezbędne? Klient zaznaczył, że zakres pozostaje do doprecyzowania (Pytanie 1). | klient | do uzupełnienia | do sprawdzenia |
| Q-02 | Czy po użyciu przycisku awaryjnego zatrzymania gra wraca do stanu początkowego, czy zostaje w stanie, w którym ją zatrzymano (Pytanie 4)? | klient | do uzupełnienia | do sprawdzenia |
| Q-03 | Czy uczniowie mogą korzystać z własnych telefonów na lekcji, skoro klient wskazuje rozpraszanie się i problem z regulaminem (Pytania 9, 10)? | klient | do uzupełnienia | do sprawdzenia |
| Q-04 | W jaki sposób uczeń ma dokończyć w domu na telefonie pracę zaczętą na szkolnym komputerze (Pytania 8, 15)? | klient | do uzupełnienia | do sprawdzenia |
| Q-05 | Ile czasu uczniowie utrzymują skupienie na jednym zadaniu? Odpowiedź wymaga lekcji pilotażowej (Pytanie 12). | klient | do uzupełnienia | do sprawdzenia |
| Q-06 | Jak uczeń o mniejszym doświadczeniu ma przechodzić do trudniejszych zadań, skoro samouczków i ścieżki nauki krok po kroku nie planujemy? (N-09) | klient | do uzupełnienia | do sprawdzenia |
| Q-07 | Jak uczniowie uruchamiają dziś programy w pracowni, skoro na szkolnych komputerach instalowanie nowych programów bywa zablokowane? (N-06) | klient | do uzupełnienia | do sprawdzenia |
| Q-08 | Kto albo co podpowiada dziś uczniowi w domu, co poszło nie tak w jego pracy? (N-08) | klient | do uzupełnienia | do sprawdzenia |
| Q-09 | Co odbiorca gry powinien zobaczyć na ekranie na samym początku, żeby wiedzieć, co ma robić? (N-12) | klient | do uzupełnienia | do sprawdzenia |
| Q-10 | Co dokładnie rozumie Pan/Pani przez animację w pierwszym projekcie ucznia? (N-03) | klient | do uzupełnienia | do sprawdzenia |
