# Projekt zespołowy systemu informatycznego cz. 1
## Materiały do zajęć 1

---

# A. Karta projektu

## KARTA PROJEKTU — WERSJA 0.1

### 1. Podstawowe informacje

**Nazwa projektu:**

Mobilny silnik gier typu „Drag and drop” do nauki programowania

**Krótka nazwa / akronim:**

Modde (Mobile Oriented Drag&Drop Engine)

**Zespół:**

| Imię i nazwisko | Rola główna | Kontakt / login repozytorium          |
| Arsenii Liapin  | Project manager / Runtime | LiapinArsenii           |
| Daryna Melnyk   | Dokumentacja / tester     | melnukdarina1111-blip   |
| Daryna Kotiash  | Graphic designer          | daritiash               |
| Bekzigit Kuatbek| Editor                    | kuatbekulybeles-sketch  |

---

## 2. Problem

### Jaki problem chcemy rozwiązać?

Narzędzia do nauki programowania przez tworzenie gier są projektowane głównie pod komputer, a wielu młodych ludzi ma na co dzień tylko telefon. Brakuje wygodnego, mobilnego edytora, w którym początkujący stworzy własną grę i nauczy się podstaw algorytmów.

---

## 3. Kogo dotyczy problem?

Problem dotyczy każdego, kto chce zacząć uczyć się programowania, a nie ma pod ręką komputera:

- Uczniowie szkół podstawowych i średnich: chcą tworzyć własne gry, ale mają głównie telefon.
- Nauczyciele i prowadzący zajęcia: potrzebują narzędzia, które uczniowie mogą uruchomić na własnych urządzeniach.
- Początkujący hobbyści: chcą spróbować swoich sił w tworzeniu gier bez instalowania ciężkiego oprogramowania.

---

## 4. Cel systemu

Celem systemu jest mobilny, polskojęzyczny edytor gier oparty na klockach, który pozwala początkującym tworzyć własne gry na telefonie i uczyć się przy tym podstaw algorytmów.

---

## 5. Użytkownicy systemu

| Użytkownik / rola | Do czego będzie używał systemu? |
|---|---|
| Twórca gier | Układa program z klocków, testuje swoją grę i eksportuje ją. |
| Odbiorca gry| Otwiera wyeksportowaną grę i w nią gra. |

---

## 6. Interesariusze

| Interesariusz                     | Dlaczego system jest dla niego istotny? |
|-----------------------------------|-----------------------------------------|
| Prowadzący zajęcia / Nauczyciel   | Otrzymuje gotowe narzędzie dydaktyczne, które może wdrożyć na lekcjach bez konieczności
                                    | posiadania przez szkołę pracowni komputerowej.
| Rodzice                           | Zyskują bezpieczną i edukacyjną alternatywę dla bezmyślnego spędzania czasu na telefonie  
                                    | przez dzieci (nauka przez twórczość).
| Twórcy platform edukacyjnych      | Mogą traktować system jako uzupełnienie materiałów do nauki podstaw informatyki i 
                                    | logiki.
| Społeczność Open Source           | Otrzymuje projekt silnika, który w przyszłości można rozwijać, tłumaczyć na inne języki i 
                                    | rozbudowywać o nowe klocki.

---

## 7. Zakres IN

Co system **będzie** realizował?

1. Mobilny interfejs edytora (UI) przystosowany do ekranów dotykowych (smartfony i tablety).
2. System "Drag and drop" do układania klocków logicznych i instrukcji.
3. Środowisko uruchomieniowe (runtime) do wykonywania logiki gry napisane w Pythonie.
4. Podstawowa biblioteka gotowych obiektów graficznych i sprite'ów do użycia w grach.
5. Mechanizm testowania/podglądu tworzonej gry bezpośrednio na urządzeniu mobilnym.
6. Możliwość zapisywania i wczytywania projektu gry w pliku lokalnym.
7. Polskojęzyczny interfejs oraz komunikaty o błędach dostosowane dla początkujących.

---

## 8. Zakres OUT

Czego system **nie będzie** realizował?

1. Zaawansowanego wsparcia dla grafiki 3D (silnik obsługuje wyłącznie 2D).
2. Kompilacji gry do natywnych plików .apk lub .ipa z poziomu telefonu (eksport tylko do formatu projektu).
3. Wbudowanego sklepu z grami lub serwerowej chmury do hostowania i udostępniania gier online.
4. Zaawansowanego systemu multiplayer (gry będą w pełni lokalne, jednoosobowe).
5. Pełnoprawnego edytora kodu tekstowego (wszystko odbywa się za pomocą bloków wizualnych).

---

## 9. Najważniejsze funkcje

Wymieńcie maksymalnie 10 funkcji.

1. Wizualny edytor klocków: Łączenie bloków logicznych (ruch, warunki, pętle) metodą przeciągnij i upuść.
2. Paleta zasobów: Wybór i dodawanie postaci, tła oraz elementów otoczenia do sceny.
3. Edytor sceny (Scene Editor): Rozmieszczanie obiektów na planszy za pomocą dotyku.
4. Tryb podglądu (Play Mode): Natychmiastowe uruchomienie gry w celu przetestowania napisanego skryptu.
5. System zmiennych i warunków: Proste operacje logiczne ułatwiające naukę algorytmów.
6. Zapis i odczyt projektu: Serializowanie stanu gry do pliku w późniejszej edycji.
7. Obsługa zdarzeń dotykowych: Reagowanie gry na kliknięcia, przeciąganie i gesty gracza.
8. Zarządzanie pętlą gry (Game Loop): Kontrolowanie czasu i klatek animacji w module runtime.
9. Polskojęzyczne podpowiedzi i błędy: Wyjaśnianie błędów logicznych w kodzie blokowym w czytelnym dla ucznia języku.
10. Modułowa architektura: Czysty podział na logikę, interfejs i renderer ułatwiający pracę zespołową.

---

## 10. Główne obiekty / dane

Jakiego rodzaju informacje system prawdopodobnie będzie przechowywał?

Przykład:

- użytkownik,
- rezerwacja,
- sala.

Dla naszego systemu:

1. Projekt gry (Project): Główny kontener przechowujący metadane, sceny i ustawienia całej gry.
2. Scena (Scene): Plansza lub poziom, na którym rozmieszczone są obiekty w danym momencie.
3. Obiekt gry (GameObject / Sprite): Element graficzny na scenie posiadający pozycję (x, y) i przypisane skrypty.
4. Klocek / Skrypt (Block / Behavior): Pojedyncza instrukcja logiczna lub struktura sterująca (np. "jeśli dotknięto, to...").
5. Zmienna (Variable): Przechowywana w grze wartość (np. wynik punktowy, stan zdrowia gracza).

## 11. Główne założenia

Przykład:

> Zakładamy, że każdy użytkownik posiada konto.

....................................................................................

....................................................................................

---

## 12. Wstępne ryzyka

Co może utrudnić wykonanie projektu?

| Ryzyko | Dlaczego może być problemem? |
|---|---|
| | |
| | |
| | |

---

## 13. Wstępnie rozważane technologie

Ta część **nie jest najważniejsza na tym etapie**.

Frontend:

....................................................................................

Backend:

....................................................................................

Baza danych:

....................................................................................

Inne:

....................................................................................

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
