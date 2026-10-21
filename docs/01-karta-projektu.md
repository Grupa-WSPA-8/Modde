# KARTA PROJEKTU — WERSJA 0.3

## 1. Podstawowe informacje

**Nazwa projektu:**

Mobilny silnik gier typu „przeciągnij i upuść" do nauki programowania

**Krótka nazwa / akronim:**

Modde (Mobile Oriented Drag&Drop Engine)

**Zespół:**

| Imię i nazwisko    | Rola główna                                                 | Kontakt / login repozytorium |
| ------------------ | ----------------------------------------------------------- | ---------------------------- |
| Arsenii Liapin     | Project manager / interpreter / architektura / dokumentacja | @LiapinArsenii               |
| Bekzigit Kuatbek   | Edytor (edytor programów z klocków)                         | @kuatbekulybeles-sketch      |
| Daryna Melnyk      | Runner (wyświetlanie gry) / testy                           | @melnukdarina1111-blip       |
| Daryna Kotiash     | Projektant graficzny / UI                                   | @daritiash                   |
| Temirlan Kalibekov | Zapis i eksport projektów (storage) / model danych          | @timakalibekov               |

---

## 2. Problem

### Jaki problem chcemy rozwiązać?

Narzędzia do nauki programowania przez tworzenie gier są projektowane głównie pod komputer, a wielu młodych ludzi ma na co dzień tylko telefon. Brakuje wygodnego, mobilnego silnika, w którym początkujący stworzy własną grę i nauczy się podstaw algorytmów.

---

## 3. Kogo dotyczy problem?

Problem dotyczy każdego, kto chce zacząć uczyć się programowania, a nie ma pod ręką komputera:

- **Uczniowie szkół podstawowych i średnich:** chcą tworzyć własne gry, ale mają głównie telefon.
- **Nauczyciele i prowadzący zajęcia:** potrzebują narzędzia, które uczniowie mogą uruchomić na własnych urządzeniach.
- **Początkujący hobbyści:** chcą spróbować swoich sił w tworzeniu gier bez instalowania ciężkiego oprogramowania.

---

## 4. Cel systemu

Celem systemu jest mobilny, polskojęzyczny edytor gier oparty na klockach, który pozwala początkującym tworzyć własne gry na telefonie i uczyć się przy tym podstaw algorytmów.

---

## 5. Użytkownicy systemu

| Użytkownik / rola | Do czego będzie używał systemu?                              |
| ----------------- | ------------------------------------------------------------ |
| **Twórca gier**   | Układa program z klocków, testuje swoją grę i eksportuje ją. |
| **Odbiorca gry**  | Otwiera wyeksportowaną grę i w nią gra.                      |

---

## 6. Interesariusze

| Interesariusz | Dlaczego system jest dla niego istotny? |
|---|---|
| **Nauczyciele informatyki / prowadzący zajęcia** | Mogą wykorzystać edytor na lekcjach, ale nie mają w nim osobnej roli. |
| **Rodzice i opiekunowie** | Chcą, by dziecko uczyło się w bezpiecznym narzędziu, które nie zbiera danych. |
| **Szkoły** | Potrzebują narzędzia, które działa na telefonach uczniów i nie wymaga instalacji na komputerach. |
| **Prowadzący przedmiot** | Ocenia projekt i zatwierdza jego zakres. |
| **Zespół projektowy** | Odpowiada za zaprojektowanie i wykonanie systemu. |

---

## 7. Zakres IN

Co system **będzie** realizował?

1. Polskojęzyczny edytor programów z klocków, dostosowany do ekranu dotykowego telefonu.
2. Stały zestaw klocków niskiego poziomu (ok. 20): zmienne, pozycja x i y, warunki, pętle, zdarzenia oraz sprawdzanie kolizji (w stylu „czy w tym miejscu jest obiekt typu X?").
3. Interpreter wykonujący program ułożony z klocków.
4. Runner rysujący wynik działania programu na ekranie (sceny 2D, postacie, tła).
5. biekty gry 2D z grafiką, położeniem x i y oraz własnymi zmiennymi, umieszczane w scenie, ze sterowaniem dotykowym.
6. Zapis i wczytywanie projektów lokalnie na urządzeniu użytkownika.
7. Eksport gotowej gry do pliku, który można otworzyć i uruchomić na innym telefonie.
8. Dwa gotowe przykładowe projekty (gra z widokiem z góry i prosta platformówka) pokazujące możliwości silnika.

---

## 8. Zakres OUT

Czego system **nie będzie** realizował?

1. Kont użytkowników i logowania.
2. Platformy do udostępniania gier (galerii online, komentarzy, ocen).
3. Samouczków i ścieżki nauki krok po kroku.
4. Panelu nauczyciela i zarządzania klasą.
5. Gier 3D i zaawansowanej fizyki.
6. Trybu wieloosobowego.
7. Natywnych aplikacji i publikacji w sklepach z aplikacjami.
8. Gotowego systemu ruchu i fizyki (grawitacja, skoki): użytkownik buduje je sam z klocków. Ewentualnie jako rozszerzenie, jeśli starczy czasu.

---

## 9. Najważniejsze funkcje

1. Składanie programu z klocków metodą „przeciągnij i upuść".
2. Dobór postaci i teł z gotowej biblioteki grafik.
3. Definiowanie zdarzeń i reakcji (dotknięcie ekranu, kolizja, upływ czasu).
4. Warunki, pętle i zmienne (w tym licznik punktów).
5. Uruchomienie i test gry bezpośrednio w edytorze.
6. Sterowanie dotykowe w grze.
7. Sprawdzanie programu: czytelne komunikaty o błędach i zabezpieczenie przed zawieszeniem telefonu (np. nieskończona pętla).
8. Zapis i wczytanie projektu na urządzeniu.
9. Eksport gry do pliku.
10. Uruchomienie wyeksportowanej gry przez odbiorcę.

---

## 10. Główne obiekty / dane

Dla naszego systemu:

1. **Projekt gry:** nazwa, sceny i ustawienia.
2. **Program z klocków:** układ klocków i ich parametry.
3. **Obiekt gry:** postać lub tło, jego grafika, położenie i właściwości.
4. **Zmienna gry:** np. wynik, liczba żyć.
5. **Wyeksportowana gra:** plik z grą gotową do uruchomienia przez odbiorcę.

---

## 11. Główne założenia

- Zakładamy, że użytkownik nie zakłada konta, a projekty zapisuje wyłącznie lokalnie na własnym urządzeniu.
- Zakładamy, że system nie zbiera ani nie przetwarza danych osobowych.
- Zakładamy, że użytkownik ma telefon z nowoczesną przeglądarką, w której działa aplikacja.
- Zakładamy gotowy, ograniczony zestaw grafik przygotowany przez zespół lub pochodzący z otwartych źródeł.
- Zakładamy jeden szablon gry 2D oraz stały zestaw klocków, bez możliwości dodawania własnych.
- Zakładamy interfejs wyłącznie w języku polskim.

---

## 12. Wstępne ryzyka

| Ryzyko                                                       | Dlaczego może być problemem?                                                                                                                                                                           |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Zakres zbyt duży na jeden semestr** (zgłoszone w recenzji) | Edytor, interpreter i runner to trzy duże części. Ograniczamy to stałym, niewielkim zestawem klocków niskiego poziomu, jednym modelem obiektów 2D, brakiem kont, samouczków i platformy udostępniania. |
| **Obsługa dotykowa edytora na małym ekranie**                | Przeciąganie i precyzyjne układanie klocków na telefonie jest trudne i może zniechęcać użytkowników.                                                                                                   |
| **Zależności między częściami systemu**                      | Zmiana formatu programu lub danych do wyświetlenia psuje pracę pozostałych osób. Ograniczamy to wspólnym, opisanym kontraktem między częściami.                                                        |
| **Nierówne obciążenie i różne doświadczenie zespołu**        | Kluczowe części systemu opierają się na jednej lub dwóch osobach. Ograniczamy to małym zakresem i jasnym podziałem zadań.                                                                              |
| **Wydajność na słabszych telefonach**                        | Błędny lub zbyt rozbudowany program użytkownika może zawiesić grę lub przeglądarkę.                                                                                                                    |

---

## 13. Wstępnie rozważane technologie

Ta część nie jest najważniejsza na tym etapie. Poniżej zapisano technologie rozważane wstępnie. Ostateczny wybór zostanie potwierdzony po wykonaniu prototypu i zapisany w ADR-001.

Platforma:

Aplikacja na system Android. Na etapie prac rozwojowych możliwość uruchamiania także na komputerze.

Język programowania:

Python (rozważany jako główny język całego systemu).

Interfejs i edytor:

Kivy (biblioteka do interfejsów dotykowych), do ustalenia po prototypie.

Interpreter i runner:

Python, z wykorzystaniem Kivy lub innej biblioteki do grafiki 2D (do ustalenia po prototypie).

Przechowywanie danych:

Lokalnie na urządzeniu, w plikach projektu (bez serwera i kont). Eksport gry do pliku.

Inne:

Git i GitHub, Markdown, Mermaid, narzędzie do makiet interfejsu (do ustalenia).

---

# B. Formularz wyboru tematu

## WYBÓR TEMATU PROJEKTU

**Zespół:**

....................................................................................

### Temat 1 — preferowany

**Nazwa:**

....................................................................................

**Problem:**

....................................................................................

**Główni użytkownicy:**

....................................................................................

**Dlaczego chcemy realizować ten temat?**

....................................................................................

---

### Temat 2

**Nazwa:**

....................................................................................

**Problem:**

....................................................................................

---

### Temat 3

**Nazwa:**

....................................................................................

**Problem:**

....................................................................................

---

## Własny temat

Jeżeli zespół proponuje własny temat:

**Nazwa:**

....................................................................................

**Problem:**

....................................................................................

**Dlaczego temat ma odpowiednią skalę projektu semestralnego?**

....................................................................................

....................................................................................

---

## Decyzja prowadzącego

- [ ] temat zaakceptowany,
- [ ] temat zaakceptowany po zmianie zakresu,
- [ ] temat wymaga ponownego opracowania.

### Uwagi

....................................................................................

....................................................................................

---

# C. Formularz podziału ról

## ZESPÓŁ PROJEKTOWY

**Nazwa projektu:**

....................................................................................

| Obszar odpowiedzialności | Osoba główna | Osoba wspierająca |
|---|---|---|
| koordynacja projektu | | |
| analiza wymagań | | |
| procesy biznesowe | | |
| architektura | | |
| baza danych | | |
| UI/UX | | |
| implementacja | | |
| testowanie | | |
| dokumentacja | | |

---

## Zasada

Każdy członek zespołu:

- zna cały projekt,
- wykonuje zadania projektowe,
- ma przynajmniej jeden obszar głównej odpowiedzialności.

Role mogą ulegać zmianie.

---

## Koordynator zespołu

**Imię i nazwisko:**

....................................................................................

Koordynator odpowiada za:

- pilnowanie terminów,
- organizację pracy,
- kontrolę tablicy zadań,
- upewnienie się, że projekt jest spójny.

Koordynator:

**nie jest przełożonym pozostałych studentów.**

---

# D. Pierwsze zadanie zespołowe

## ZADANIE 1 — OD POMYSŁU DO KARTY PROJEKTU

### Cel

Waszym zadaniem jest przygotowanie pierwszej wersji koncepcji systemu.

---

## Etap 1 — wybierzcie problem

Nie zaczynajcie od technologii.

Odpowiedzcie:

### Co obecnie działa źle albo nieefektywnie?

....................................................................................

....................................................................................

### Kto doświadcza tego problemu?

....................................................................................

### Jak obecnie radzi sobie bez projektowanego systemu?

....................................................................................

---

## Etap 2 — określcie cel

Uzupełnijcie:

> Celem projektowanego systemu jest...

....................................................................................

....................................................................................

---

## Etap 3 — wskażcie użytkowników

Minimum:

**2 różne role użytkowników.**

Optymalnie:

**3–5 ról.**

| Rola | Potrzeba |
|---|---|
| | |
| | |
| | |
| | |

---

## Etap 4 — określcie zakres

### IN

Co system będzie realizował?

Minimum 5 pozycji.

### OUT

Czego system celowo nie będzie realizował?

Minimum 3 pozycje.

---

## Etap 5 — określcie główne funkcje

Wybierzcie:

### 3 funkcje najważniejsze

1. ................................................................................
2. ................................................................................
3. ................................................................................

### Funkcje dodatkowe

....................................................................................

....................................................................................

---

## Etap 6 — podzielcie odpowiedzialność

Wypełnijcie formularz ról.

Każda osoba musi mieć wskazany przynajmniej jeden obszar odpowiedzialności.

---

## Etap 7 — przygotujcie prezentację

Macie maksymalnie:

# 2 minuty

Musicie odpowiedzieć na pięć pytań:

1. Jaki jest temat?
2. Jaki problem rozwiązujecie?
3. Kto będzie użytkownikiem?
4. Jakie są trzy najważniejsze funkcje?
5. Czego system nie będzie realizował?

---

# E. Kryteria akceptacji zadania

Zadanie jest wykonane, jeżeli:

- [ ] zespół posiada temat,
- [ ] problem został opisany,
- [ ] określono cel,
- [ ] wskazano użytkowników,
- [ ] wskazano interesariuszy,
- [ ] określono zakres IN,
- [ ] określono zakres OUT,
- [ ] określono główne funkcje,
- [ ] członkowie zespołu mają role,
- [ ] karta projektu 0.1 została utworzona.

---

# F. Autokontrola zespołu

Przed oddaniem odpowiedzcie TAK/NIE.

| Pytanie | TAK/NIE |
|---|---|
| Czy rozwiązujemy konkretny problem? | |
| Czy potrafimy wskazać użytkowników? | |
| Czy mamy więcej niż jedną rolę użytkownika? | |
| Czy system zawiera rzeczywisty proces? | |
| Czy system będzie przechowywał dane? | |
| Czy występują reguły biznesowe? | |
| Czy zakres jest możliwy do wykonania? | |
| Czy wiemy, czego świadomie nie wykonujemy? | |
| Czy projekt jest czymś więcej niż prostym CRUD-em? | |

Jeżeli na kilka pytań odpowiedź brzmi **NIE**, należy ponownie zastanowić się nad zakresem.

---

# G. Praca po pierwszych zajęciach

## Studenci stacjonarni

Do następnego spotkania przygotować:

1. kartę projektu 0.2,
2. dopracowany zakres IN/OUT,
3. listę interesariuszy,
4. minimum 10 terminów do słownika dziedzinowego,
5. repozytorium projektu.
