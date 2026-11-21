# ADR-002: Styl architektury — lokalna aplikacja bez serwera

**Status:** przyjęta
**Data:** 2026-11-21
**Autorzy:** Arsenii Liapin

## Kontekst

Projekt realizuje zespół pięciu osób. Dokumentacja powstaje w pierwszym semestrze, a kod aplikacji w drugim (Ograniczenia). System musi działać na telefonie oraz na komputerze, jako ta sama aplikacja, bez osobnego interfejsu (Ograniczenia, FR-21, N-07); formę tej aplikacji ustala ten ADR. Na szkolnych komputerach nie można zakładać możliwości instalowania nowych programów (Ograniczenia, N-06, NFR-09).

System nie ma kont użytkowników, a projekt gry jest zapisywany wyłącznie lokalnie na urządzeniu Twórcy gier (BR-03). Dane osobowe użytkowników nie są zbierane ani przetwarzane (BR-06), a system wysyła poza urządzenie 0 bajtów danych Twórcy gier (NFR-10). Wyeksportowana gra trafia do Odbiorcy gry jako plik przesłany przez komunikator, poza aplikacją (BR-04, P-02). Dalsza praca nad projektem gry na innym urządzeniu opiera się na pliku projektu gry przenoszonym ręcznie przez Twórcę gier (BR-03, P-03).

System składa się z kilku dużych części (edytor, interpreter, runner, zapis i eksport), za które odpowiadają różne osoby. Zmiana formatu programu z klocków lub danych do wyświetlenia może zepsuć pracę pozostałych osób (karta projektu, „Wstępne ryzyka”).

Wybór technologii (język, biblioteki) nie jest przedmiotem tego ADR i zostanie zapisany w ADR-003.

## Rozważane opcje

1. **Jedna lokalna aplikacja (modularny monolit) bez serwera.** Cały system działa na urządzeniu Twórcy gier lub Odbiorcy gry. Wewnątrz aplikacja jest podzielona na moduły z jasnymi granicami.
2. **Aplikacja i serwer.** Aplikacja na urządzeniu oraz serwer z kontami użytkowników i synchronizacją projektów gry w chmurze.
3. **Aplikacja webowa w przeglądarce.** System działa w przeglądarce, a aplikacja jest pobierana ze strony internetowej.

Porównanie opcji z wymaganiami:

| Wymaganie                                                      | Opcja 1: lokalna aplikacja                                                        | Opcja 2: aplikacja i serwer                              | Opcja 3: aplikacja webowa                                                                                                                 |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Otwarcie otrzymanej gry z komunikatora (N-11, P-02.4, NFR-08)  | spełnia: plik wyeksportowanej gry otwiera się w Modde bezpośrednio z komunikatora | spełnia, jak w opcji 1                                   | częściowo: plik trzeba zapisać i wczytać ręcznie na stronie; mechanizmy otwierania plików w przeglądarce różnią się między przeglądarkami |
| Działanie bez serwera do utrzymania                            | spełnia: aplikacja działa po zainstalowaniu                                       | nie spełnia: serwer z kontami i synchronizacją           | nie spełnia: aplikację trzeba udostępniać z serwera WWW przez cały czas używania                                                          |
| Brak kont, zapis wyłącznie lokalny (BR-03, zakres OUT)         | spełnia                                                                           | nie spełnia: konta i serwer są w zakresie OUT            | spełnia, jeśli projekt gry zostaje w przeglądarce                                                                                         |
| 0 bajtów danych Twórcy gier poza urządzeniem (NFR-10, BR-06)   | spełnia                                                                           | nie spełnia: synchronizacja wysyła projekt gry na serwer | spełnia, jeśli projekt gry zostaje w przeglądarce                                                                                         |
| Uruchomienie na komputerze bez instalowania programów (NFR-09) | trudniejsze: wymaga wersji aplikacji, która nie potrzebuje instalacji             | trudniejsze, jak w opcji 1                               | łatwiejsze: wystarczy przeglądarka                                                                                                        |
| Przeniesienie projektu gry na inne urządzenie (P-03, N-10)     | tylko ręcznie jako plik                                                           | automatycznie przez konto                                | tylko ręcznie jako plik                                                                                                                   |
| Wykonalność dla zespołu 5 osób w semestrze 2                   | jedna aplikacja do utrzymania                                                     | aplikacja i serwer do utrzymania                         | aplikacja i serwer WWW do utrzymania                                                                                                      |

## Decyzja

Wybieramy opcję 1: jedną lokalną aplikację (modularny monolit) bez serwera.

Moduły aplikacji odpowiadają katalogom repozytorium:

| Moduł                 | Katalog        | Odpowiedzialność                                                                                                                                                                                 |
| --------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| edytor                | `editor/`      | Układanie programu z klocków, umieszczanie obiektów gry w scenie, wybór grafiki z biblioteki grafik.                                                                                             |
| interpreter           | `interpreter/` | Wykonywanie programu z klocków po wystąpieniu zdarzenia, zatrzymanie gry przyciskiem „Stop” i przerwanie pętli, która się nie kończy.                                                            |
| runner                | `runner/`      | Rysowanie sceny i obiektów gry na ekranie, sterowanie dotykowe, wyświetlanie aktualnej wartości zmiennej, tryb odtwarzania wyeksportowanej gry bez możliwości zmiany programu z klocków (BR-01). |
| zapis i eksport       | `storage/`     | Zapis i wczytanie projektu gry na urządzeniu, eksport projektu gry do pliku wyeksportowanej gry.                                                                                                 |
| wspólny format danych | `contract/`    | Opis formatu projektu gry, programu z klocków i obiektu gry, z którego korzystają pozostałe moduły.                                                                                              |

Zasady:
- Moduły komunikują się przez format danych opisany w `contract/`.
- Moduł nie sięga do danych innego modułu.
- Zmiana formatu w `contract/` wymaga zgody osób odpowiedzialnych za moduły, które z niego korzystają.

Dlaczego nie opcja 2: konta użytkowników i serwer są w zakresie OUT (karta projektu, „Zakres OUT”), a synchronizacja projektów gry w chmurze wysyłałaby dane Twórcy gier poza urządzenie, czego zabrania NFR-10.

Dlaczego nie opcja 3: główny problem klienta przy przekazywaniu gier to pliki, które nie otwierają się na innym urządzeniu (N-11). Aplikacja zainstalowana na telefonie może otwierać plik wyeksportowanej gry bezpośrednio z komunikatora (P-02.4, NFR-08), a w aplikacji webowej Odbiorca gry musi zapisać plik i wczytać go ręcznie na stronie. Opcja 3 wymaga też serwera WWW, z którego aplikacja jest udostępniana przez cały czas jej używania, a z serwera do utrzymania rezygnujemy także w opcji 2. Opcja 3 ułatwiłaby jednak spełnienie NFR-09, ponieważ na szkolnym komputerze z zablokowaną instalacją wystarczyłaby przeglądarka.

## Konsekwencje

Co zyskujemy:
- Twórca gier nie potrzebuje konta użytkownika (BR-03), a aplikacja działa także bez dostępu do sieci.
- Dane Twórcy gier nie opuszczają urządzenia, co ułatwia spełnienie NFR-10 i BR-06.
- Nie ma serwera do utrzymania, więc zakres jest wykonalny dla zespołu 5 osób w semestrze 2.
- Podział na moduły odpowiada podziałowi ról w zespole, a wspólny format w `contract/` ogranicza ryzyko zależności między częściami systemu.

Co tracimy / jakie są ryzyka:
- Brak synchronizacji między urządzeniami. Projekt gry można przenieść na inne urządzenie tylko ręcznie jako plik (P-03.4). Sposób przeniesienia pozostaje nieustalony (Q-04).
- Odbiorca gry potrzebuje Modde, aby uruchomić wyeksportowaną grę. Do potwierdzenia z klientem (Q-13).
- Spełnienie NFR-09 jest trudniejsze niż w aplikacji webowej: potrzebna jest wersja aplikacji na komputer, która nie wymaga instalacji.
- Całe wykonywanie gry odbywa się na urządzeniu, więc wydajność zależy od telefonu Twórcy gier lub Odbiorcy gry (NFR-01, NFR-02).
- W jednej aplikacji łatwo obejść granice modułów. Jeśli moduły zaczną sięgać do cudzych danych, zmiana jednego modułu zepsuje pozostałe.

Co musimy zrobić:
- Zapisać wybór technologii w ADR-003 (status: proponowana) i potwierdzić go prototypem. (Arsenii)
- Podzielić moduły na komponenty na zajęciach 12. (zespół)