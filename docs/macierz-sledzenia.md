# Macierz śledzenia — Modde

**Wersja:** 0.2

| Potrzeba / źródło | Wymaganie | Historyjka | Priorytet | Proces |
| --- | --- | --- | --- | --- |
| N-02, N-07 | FR-01 Dodanie klocka metodą „przeciągnij i upuść” | US-01 | Must | P-01.4, P-03.1, P-03.7 |
| N-03 | FR-02 Przypisanie programu z klocków do zdarzenia | US-01 | Must | P-01.5, P-01.8, P-01.9 |
| N-05 | FR-03 Zmiana wartości zmiennej klockiem | US-02 | Must | P-01.4 |
| N-05 | FR-04 Warunek (wykonanie klocków tylko przy spełnieniu pytania) | US-02 | Must | P-01.4 |
| N-05 | FR-05 Pętla (powtarzanie klocków) | US-03 | Must | P-01.4 |
| N-03 | FR-06 Zmiana położenia obiektu gry | US-04 | Must | P-01.4 |
| karta projektu | FR-07 Sprawdzenie kolizji obiektów gry | — (Should, bez historyjki) | Should | — (brak kroku, do sprawdzenia) |
| N-03 | FR-08 Umieszczenie obiektu gry w scenie | US-04 | Must | P-01.2 |
| karta projektu | FR-09 Wybór grafiki z biblioteki grafik | — (Should, bez historyjki) | Should | P-01.3 |
| N-01, N-05 | FR-10 Uruchomienie gry w edytorze | US-05 | Must | P-01.6, P-01.7, P-01.9 |
| N-04 | FR-11 Zatrzymanie gry przyciskiem „Stop” | US-06 | Must | P-01.10, P-01.11 |
| N-04 | FR-12 Przerwanie programu z nieskończoną pętlą | — (Could, bez historyjki) | Could | — (brak kroku, tylko wyjątek W-02 w P-01, do sprawdzenia) |
| N-08 | FR-13 Komunikat o błędzie w programie z klocków | — (Should, bez historyjki) | Should | P-01.7 |
| N-05, N-12 | FR-14 Podgląd wartości zmiennej w trakcie gry | — (Should, bez historyjki) | Should | P-01.7, P-02.7 |
| karta projektu, N-10 | FR-15 Zapis projektu gry | US-07 | Must | P-01.12, P-01.13, P-03.2, P-03.3, P-03.8 |
| karta projektu, N-10 | FR-16 Wczytanie projektu gry | — (Should, bez historyjki) | Should | P-01.1, P-03.5, P-03.6 |
| N-11 | FR-17 Eksport gry do pliku | US-08 | Must | P-02.1, P-02.2 |
| N-11 | FR-18 Uruchomienie wyeksportowanej gry przez Odbiorcę gry | US-09 | Must | P-02.4, P-02.5 |
| N-12 | FR-19 Sterowanie obiektem gry dotykiem | — (Should, bez historyjki) | Should | P-02.6, P-02.7 |
| karta projektu | FR-20 Otwarcie przykładowego projektu gry | — (Could, bez historyjki) | Could | P-01.1 |
| karta projektu, N-10 | FR-21 Działanie aplikacji także na komputerze | — (Should, bez historyjki) | Should | P-03.1 |
| N-03 | FR-22 Utworzenie nowego projektu gry z pustą sceną | US-10 | Must | P-01.1 |
| N-10, N-11 | FR-23 Komunikat o niewczytanym projekcie gry | — (Should, bez historyjki) | Should | P-03.6 (wyjątek) |
| N-12 | NFR-01 Reakcja na dotknięcie nie później niż 100 ms | — (NFR: sprawdzane testem) | Should | P-02.7 |
| N-01, karta projektu | NFR-02 Co najmniej 30 klatek na sekundę | — (NFR: sprawdzane testem) | Should | — (wymaganie przekrojowe) |
| N-04 | NFR-03 Zatrzymanie gry w czasie do 1 s | US-06 | Must | P-01.10, P-01.11 |
| N-03 | NFR-04 Pierwszy projekt ucznia w ciągu 60 minut | — (NFR: sprawdzane testem) | Must | — (wymaganie przekrojowe) |
| N-07, N-04 | NFR-05 Obszar dotyku elementów co najmniej 9 × 9 mm | — (NFR: sprawdzane testem) | Should | P-03.7 |
| N-08 | NFR-06 Zrozumiały komunikat o błędzie w ciągu 2 s | — (NFR: sprawdzane testem) | Should | — (brak kroku, tylko wyjątek W-01 w P-01, do sprawdzenia) |
| N-07 | NFR-07 Edytor mieści się na ekranach 5,0–6,7 cala | — (NFR: sprawdzane testem) | Should | P-03.6 |
| N-11, karta projektu | NFR-08 Wyeksportowana gra otwiera się na innym telefonie | US-09 | Must | P-02.4 |
| N-06, karta projektu | NFR-09 Uruchomienie na komputerze bez instalacji | — (NFR: sprawdzane testem) | Should | P-03.1 |
| karta projektu | NFR-10 Brak wysyłania danych poza urządzenie | — (NFR: sprawdzane testem) | Must | P-02.3 |
| słownik: Odbiorca gry | BR-01 Odbiorca gry tylko uruchamia grę | US-09 | Must | P-02.5 |
| karta projektu, „Zakres IN” i „Główne założenia” | BR-02 Stały zestaw klocków | US-01, US-02, US-03, US-04 | Must | P-01.4 |
| karta projektu, „Główne założenia”; N-10 | BR-03 Projekt zapisywany lokalnie, bez kont | US-07, US-10 | Must | P-01.12, P-01.13, P-03.3, P-03.4, P-03.6, P-03.8 |
| słownik: Odbiorca gra; karta projektu, „Zakres OUT”; N-11 | BR-04 Gra przekazywana jako plik, bez sklepów | US-08, US-09 | Must | P-02.2, P-02.3, P-02.5 |
| słownik: Zdarzenie | BR-05 Program wykonuje się po zdarzeniu | US-01, US-05 | Must | P-01.5, P-01.9 |
| karta projektu, „Główne założenia” | BR-06 Brak danych osobowych | — (Must, bez historyjki) | Must | — (reguła przekrojowa, brak kroku) |
