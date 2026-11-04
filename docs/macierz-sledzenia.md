# Macierz śledzenia — Modde

**Wersja:** 0.1

| Potrzeba / źródło                                   | Wymaganie                                                       | Historyjka                 | Priorytet |
| --------------------------------------------------- | --------------------------------------------------------------- | -------------------------- | --------- |
| N-02, N-07                                          | FR-01 Dodanie klocka metodą „przeciągnij i upuść”               | US-01                      | Must      |
| N-03                                                | FR-02 Przypisanie programu z klocków do zdarzenia               | US-01                      | Must      |
| N-05                                                | FR-03 Zmiana wartości zmiennej klockiem                         | US-02                      | Must      |
| N-05                                                | FR-04 Warunek (wykonanie klocków tylko przy spełnieniu pytania) | US-02                      | Must      |
| N-05                                                | FR-05 Pętla (powtarzanie klocków)                               | US-03                      | Must      |
| N-03                                                | FR-06 Zmiana położenia obiektu gry                              | US-04                      | Must      |
| karta projektu                                      | FR-07 Sprawdzenie kolizji obiektów gry                          | — (Should, bez historyjki) | Should    |
| N-03                                                | FR-08 Umieszczenie obiektu gry w scenie                         | US-04                      | Must      |
| karta projektu                                      | FR-09 Wybór grafiki z biblioteki grafik                         | — (Should, bez historyjki) | Should    |
| N-01, N-05                                          | FR-10 Uruchomienie gry w edytorze                               | US-05                      | Must      |
| N-04                                                | FR-11 Zatrzymanie gry przyciskiem „Stop”                        | US-06                      | Must      |
| N-04                                                | FR-12 Przerwanie programu z nieskończoną pętlą                  | — (Could, bez historyjki)  | Could     |
| N-08                                                | FR-13 Komunikat o błędzie w programie z klocków                 | — (Should, bez historyjki) | Should    |
| N-05, N-12                                          | FR-14 Podgląd wartości zmiennej w trakcie gry                   | — (Should, bez historyjki) | Should    |
| karta projektu                                      | FR-15 Zapis projektu gry                                        | US-07                      | Must      |
| karta projektu                                      | FR-16 Wczytanie projektu gry                                    | — (Should, bez historyjki) | Should    |
| N-11                                                | FR-17 Eksport gry do pliku                                      | US-08                      | Must      |
| N-11                                                | FR-18 Uruchomienie wyeksportowanej gry przez Odbiorcę gry       | US-09                      | Must      |
| N-12                                                | FR-19 Sterowanie obiektem gry dotykiem                          | — (Should, bez historyjki) | Should    |
| karta projektu                                      | FR-20 Otwarcie przykładowego projektu gry                       | — (Could, bez historyjki)  | Could     |
| karta projektu                                      | FR-21 Działanie aplikacji także na komputerze                   | — (Should, bez historyjki) | Should    |
| N-12                                                | NFR-01 Reakcja na dotknięcie nie później niż 100 ms             | — (NFR: sprawdzane testem) | Should    |
| N-01, karta projektu                                | NFR-02 Co najmniej 30 klatek na sekundę                         | — (NFR: sprawdzane testem) | Should    |
| N-04                                                | NFR-03 Zatrzymanie gry w czasie do 1 s                          | US-06                      | Must      |
| N-03                                                | NFR-04 Pierwszy projekt ucznia w ciągu 60 minut                 | — (NFR: sprawdzane testem) | Must      |
| N-07, N-04                                          | NFR-05 Obszar dotyku elementów co najmniej 9 × 9 mm             | — (NFR: sprawdzane testem) | Should    |
| N-08                                                | NFR-06 Zrozumiały komunikat o błędzie w ciągu 2 s               | — (NFR: sprawdzane testem) | Should    |
| N-07                                                | NFR-07 Edytor mieści się na ekranach 5,0–6,7 cala               | — (NFR: sprawdzane testem) | Should    |
| N-11, karta projektu                                | NFR-08 Wyeksportowana gra otwiera się na innym telefonie        | US-09                      | Must      |
| N-06, karta projektu                                | NFR-09 Uruchomienie na komputerze bez instalacji                | — (NFR: sprawdzane testem) | Should    |
| karta projektu                                      | NFR-10 Brak wysyłania danych poza urządzenie                    | — (NFR: sprawdzane testem) | Must      |
| słownik: Odbiorca gry                               | BR-01 Odbiorca gry tylko uruchamia grę                          | US-09                      | Must      |
| karta projektu, „Zakres IN” i „Główne założenia”    | BR-02 Stały zestaw klocków                                      | US-01, US-02, US-03, US-04 | Must      |
| karta projektu, „Główne założenia”                  | BR-03 Projekt zapisywany lokalnie, bez kont                     | US-07                      | Must      |
| słownik: Odbiorca gry; karta projektu, „Zakres OUT” | BR-04 Gra przekazywana jako plik, bez sklepów                   | US-08, US-09               | Must      |
| słownik: Zdarzenie                                  | BR-05 Program wykonuje się po zdarzeniu                         | US-01, US-05               | Must      |
| karta projektu, „Główne założenia”                  | BR-06 Brak danych osobowych                                     | — (Must, bez historyjki)   | Must      |

Jeden wiersz to jedno wymaganie. Priorytet reguły biznesowej wynika z najwyższego priorytetu powiązanych z nią wymagań. Pusta komórka oznacza pytanie. Historyjki powstają tylko dla wymagań Must, więc pozostałe wiersze nie mają jej celowo.
