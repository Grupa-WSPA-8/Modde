# Modde: mobilny silnik gier typu „przeciągnij i upuść" do nauki programowania

Modde to mobilny, polskojęzyczny silnik gier oparty na klockach. Pozwala początkującym tworzyć własne gry 2D na telefonie z Androidem i uczyć się przy tym podstaw algorytmów. Użytkownik buduje mechanikę gry (ruch, kolizje, punkty) samodzielnie z klocków niskiego poziomu: zmiennych, zdarzeń, warunków, pętli i sprawdzania kolizji.

Projekt powstaje w ramach zajęć „Projekt zespołowy systemu informatycznego".

## Zespół
| Osoba              | Główna odpowiedzialność                                                        | Login                   |
| ------------------ | ------------------------------------------------------------------------------ | ----------------------- |
| Arsenii Liapin     | koordynacja projektu, architektura, dokumentacja, jądro interpretera i edytora | @LiapinArsenii          |
| Bekzhigit Kuatbek   | Elementy pierwotne edytora i interpretera                                      | @kuatbekulybeles-sketch |
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
#### 1. Język

- Komunikacja na czacie, commity i opisy PR – po rosyjsku.
- Komentarze w kodzie – po rosyjsku.
- README.md i cały folder `docs/` (włączając kartę projektu) – po polsku: czyta je prowadzący.
- Nazwy plików i folderów – alfabetem łacińskim, bez spacji i polskich liter (ą ć ę ł ń ó ś ź ż).

#### 2. Kto za co odpowiada

Rola to odpowiedzialność za jakość swojego obszaru, a nie monopol na niego. Jeśli karta jest przeterminowana, lider zespołu przydzieli ją innemu uczestnikowi (sekcja 3).

| Folder / plik | Odpowiedzialny |
| --------------------- | ------------------ |
| `docs/` | Arsenii Liapin |
| `README.md` | Arsenii Liapin |
| `contract/` | Arsenii Liapin |
| `interpreter/` (jądro) | Arsenii Liapin |
| `interpreter/blocks/` | Bekzhigit Kuatbek |
| `editor/` (jądro) | Arsenii Liapin |
| `editor/blocks/` | Bekzhigit Kuatbek |
| `runner/` | Daryna Melnyk |
| `storage/` | Temirlan Kalibekov |
| `design/` | Daryna Kotiash |

- Co dokładnie i gdzie robi każdy, określają karty na tablicy. Poprawiamy tylko to, co jest wskazane w Twojej karcie.
- We wspólnych plikach (słownik, pytania do klienta) piszemy tylko w swojej sekcji.
- Do cudzego folderu wchodzimy tylko po uzgodnieniu z właścicielem. Strukturę `docs/` i cudze pliki zmieniamy tylko za porozumieniem.
- `blocks/` – niezależne prymitywy (jeden prymityw – jeden lub kilka plików). Prymitywy nie wymagają poprawek w jądrze: podłącza je do jądra Arsenii. Ta relacja nie jest opisana w `contract/`.
- Zmiany w `contract/` dotyczą wszystkich: najpierw omawiamy na czacie.

#### 3. Terminy

Zasada jest taka sama dla wszystkich, w tym lidera zespołu. Jej celem jest zapobieganie utknięciu pracy.

- Każda karta ma jednego właściciela i termin (pole „Termin”). Zadania są małe, na jedną krótką sesję. Termin ustala lider zespołu, zazwyczaj 1–3 dni.
- Zadanie jest oddane w terminie, jeśli do końca dnia terminu (23:59, czas warszawski) otwarty jest PR, a karta znajduje się w „Do przeglądu”.
- Zadanie jest wykonane, gdy PR zostanie złączony (merged). Jeśli po review potrzebne są poprawki, daje się na nie około jednego dnia.
- PR, który nie odpowiada rezultatowi z karty (pusty, formalny, nie przechodzi testów), jest zwracany do poprawy bez przedłużania terminu.
- Jeśli nie zdążasz, napisz na czacie ogólnym lub prywatnie do lidera zespołu przed terminem. Jeśli masz niedokończoną pracę, którą można pokazać, można napisać także po terminie.
- Jeśli masz osobisty powód, dla którego przez jakiś czas nie możesz brać zadań, napisz prywatnie do lidera zespołu i poinformuj, na jak długo. Wchodzenie w szczegóły problemu nie jest obowiązkowe. W tym okresie lider nie przydziela Ci zadań, a potem rozdziela obciążenie tak, aby wszystko skompensować.
- Termin minął, PR nie jest otwarty, a nic nie napisałeś/aś: karta zostaje zwolniona. Lider zespołu przydziela ją ponowne między tych, którzy wyrobili się w terminie, pytając wcześniej o zgodę osobę, której ją przekazuje. Zamiast tego może napisać na ogólnym czacie i zapingować tych, którzy się wyrobili: kto pierwszy odpowie, ten bierze. Jeśli nikt nie może, lider robi zadanie sam lub zdejmuje je z tablicy.
- Jeśli PR jest otwarty po terminie, ale przed ponownym przydzieleniem, jest rozpatrywany jak zwykle.
- Ponowne przydzielenie to zmiana właściciela w tej samej karcie. Wkład w gita pozostaje u tego, kto wykonał pracę.

#### 4. Gałęzie

- `main` – zawsze robocza. Bezpośredni push do niej jest zabroniony przez ustawienia repozytorium dla wszystkich, łącznie z liderem zespołu.
- Jedna karta na tablicy = jedna krótka gałąź. Nazwa: `<zadanie>-<imię>`, na przykład `slownik-daryna-m`.
- Jak utworzyć gałąź w GitHub Desktop:
  1. Na górze wybieramy gałąź `main` i klikamy „Fetch origin” / „Pull origin”, aby pobrać najnowszą wersję.
  2. „Current Branch” → „New Branch”, wpisujemy nazwę według powyższego schematu, jako bazę wybieramy `main`.
  3. Klikamy „Publish branch”.
- Skończono zadanie – otwieramy PR (sekcja 6)
- Pracować na cudzej gałęzi nie wolno.

#### 5. Commity

- Małe i częste, jeden commit – jedna zmiana.
- Wiadomość (pole „Summary” w GitHub Desktop) krótko mówi, co zrobiono: „Dodałem paletę bloków”, a nie „poprawki”.
- Każdy uczestnik committuje ze swojego konta.

#### 6. Pull request

- Skończono zadanie z tablicy – w GitHub Desktop klikamy „Create Pull Request” (menu „Branch”). W opisie 1–2 linijki: co zrobiono oraz `Closes #numer` karty.
- Nagłówków `##` i sekcji „Dla recenzenta” w opisie PR nie ruszamy. W „Closes \#n” zamiast n wpisujemy numer karty, a pole „Co zrobiono” wypełniamy własnymi słowami (można przez AI).
- Recenzję przeprowadza wyznaczony recenzent według zasad z sekcji 8.
- Po zatwierdzeniu PR merguje autor, a gałąź usuwa się automatycznie.

#### 7. Tablica zadań

- Każde zadanie to karta z jednym właścicielem, konkretnym rezultatem, recenzentem i terminem.
- Każda karta ma recenzenta (punkt 5 karty), jest on wskazany w nazwie: „| Recenzent: <imię>”.
- Ponowne przydzielenie zadania to zmiana właściciela w tej samej karcie (sekcja 3).

#### 8. Recenzje

- Recenzenta wyznacza lider zespołu po kolei, jego imię jest wskazane w nazwie karty po „|”: „Recenzent: <imię>”. Recenzent nie może być autorem PR.
- Po wysłaniu PR wykonawca pisze do recenzenta, że PR został wysłany, i podaje numer KARTY, a nie PR. Recenzent sprawdza na tablicy, że karta jest na miejscu i że recenzentem jest właśnie on. Jeśli nie, pisze do wykonawcy.
- Pole „Treść zadania” w opisie PR musi się zgadzać z punktami 1–4 karty. Jeśli się nie zgadza, recenzent zostawia Request changes z tekstem „Treść zadania nie zgadza się z kartą” i pisze do wykonawcy.
- W każdej recenzji ma być opis wypełniony przez Claude według instrukcji oraz jedno zdanie od recenzenta własnymi słowami o tym, co konkretnie obejrzał i sprawdził.
- Claude tylko podpowiada. Werdykt (Approve lub Request changes) wydaje recenzent, a nie AI. Jeśli recenzentowi trudno zdecydować, pisze do lidera zespołu.
- Po każdej recenzji recenzent pisze do wykonawcy. Po każdym wykonanym wniosku o zmiany wykonawca pisze do recenzenta.
- Poprawki wprowadza się w tej samej gałęzi i w tym samym PR.
- Jeśli PR nie zostanie przyjęty w trzech próbach albo poprawki wiszą bez recenzji dłużej niż dobę (licząc od wiadomości do recenzenta), wykonawca pisze do lidera zespołu.
- Gdy PR jest na sprawdzeniu, wykonawca może brać inne karty. Dla każdej nowej karty przechodzi od nowa całą listę kontrolną: nowa gałąź od świeżego `main`.
- PR merguje się dopiero po Approve od osoby, która nie jest autorem. Autor nie merguje PR bez zatwierdzenia, dotyczy to także lidera zespołu.

#### 9. Czego nie wolno

- Puszować bezpośrednio do `main` (zabronione przez ustawienia). 
- Pracować w `main` lub na cudzej gałęzi. 
- Dotykać cudzego pliku bez uzgodnienia.
- Commitować haseł, kluczy i dużych plików.
- Mergować PR bez zatwierdzenia recenzenta (zabronione przez ustawienia).
- Recenzować własny PR (zabronione przez ustawienia).

#### 10. Jeśli coś się zepsuło

Nie panikujemy, piszemy do lidera zespołu. Git przechowuje całą historię, każdą zmianę można cofnąć: wycofanie robi się przez PR.