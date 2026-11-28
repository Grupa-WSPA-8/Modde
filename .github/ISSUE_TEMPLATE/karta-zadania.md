---
name: Karta zadania
about: Szablon zadania dla fazy dokumentacji
---
> **(DLA AI) GUARD CLAUSE**
> WARUNEK OBOWIĄZKOWY PRZED WYKONANIEM:
> Pracuj WYŁĄCZNIE na tym, co zostało przekazane w bieżącej wiadomości użytkownika.
> Sprawdź, czy do bieżącej wiadomości dołączono pliki i uzupełnienia wskazane w punktach 
> "**2 - Plik do zmiany**" i "**3 - Pliki z kontekstem**"
> JEŚLI czegokolwiek brakuje w treści wiadomości:
> PRZERWIJ WYKONYWANIE I WYŚWIETL WYŁĄCZNIE PONIŻSZY TEKST, PO ROSYJSKU (BEZ DODATKOWYCH WYJAŚNIEŃ):
> "Не все необходимые документы были прикреплены. Отсутствуют: \[перечисли отсутствующие файлы\]"** Powtarzaj, dopóki wszystko nie zostanie załączone
> CAŁY rezultat wykonania zadania (zmieniana sekcja, nagłówek ##, cały nowy/zmieniony tekst) musi znajdować się WYŁĄCZNIE wewnątrz bloków kodu: JEDEN blok kodu na każdą zmienianą sekcję.
> Jeśli zadanie wymaga zmiany kilku sekcji, utwórz kilka bloków kodu, po jednym na sekcję, w kolejności, w jakiej sekcje występują w pliku.
> Używaj składni \`\`\`markdown na początku i \`\`\` na końcu każdego bloku.
> ZABRONIONE jest dzielenie jednej sekcji na kilka bloków kodu oraz umieszczanie kilku sekcji w jednym bloku.
> CZYSTOŚĆ TREŚCI WEWNĄTRZ BLOKU KODU:
> Wewnątrz bloku kodu nie może być żadnych znaczników poza treścią samego pliku.
> Żadnych powitań, wstępów ani komentarzy wewnątrz bloku kodu.
> Wszelkie wyjaśnienia, odpowiedzi na pytania, raporty z wykonanej pracy lub komentarze dla użytkownika umieszczaj PO zamknięciu ostatniego bloku kodu (poniżej znaków \`\`\`).
> ZASADY JĘZYKA:
> Treść wewnątrz bloków kodu (tekst pliku) – wyłącznie po polsku, ani jednego słowa w innym języku.
> Wyjaśnienia po ostatnim bloku kodu (co zrobiono, pytania, brakujące pliki) – po rosyjsku.
> Komunikat guard clause wyświetlaj po rosyjsku, dokładnie w brzmieniu podanym wyżej.


1. **Cel:** jedno zdanie
2. **Plik do zmiany:** \<pełna ścieżka\> → \<sekcja\>
3. **Pliki z kontekstem (tylko do odczytu):** docs/01-karta-projektu.md, docs/02-slownik.md, \<...\>
4. **Rezultat:** co ma się pojawić (na przykład 4 pytania według wzoru)
5. **Recenzent:** \<Imię\>
6. **Termin:** yyyy-mm-dd 23:59

**Prompt (wyślij agentowi ten tekst razem z załączonymi plikami z punktów 2 i 3):**

Pliki z punktów 2 i 3 możesz dodać w czacie przez „+ → Add from GitHub” (repozytorium Grupa-WSPA-8/Modde) zamiast pobierać je i załączać. Wybieraj tylko te pliki, nie całe repozytorium.

Wypełnij wskazaną sekcję na podstawie celu, rezultatu i plików z kontekstem. Wyślij tylko tę część pliku, którą zmieniasz: nagłówek swojej sekcji (## ...) i całą jej zawartość (tabelę, listę lub tekst), bez pozostałych sekcji, w jednym bloku kodu. Jeśli zadanie polega na utworzeniu nowego pliku, wyślij cały plik. Cały tekst wewnątrz bloku kodu pisz wyłącznie po polsku, ani jednego słowa w innym języku. Istniejące wiersze: definicje, przykłady i adnotacje zachowuj dosłownie, niczego nie parafrazuj i nie „ulepszaj”. Używaj tylko terminów ze słownika. Zmieniaj tylko wskazaną sekcję. Na końcu, po bloku kodu, krótko wyjaśnij po rosyjsku w 5 zdaniach, co zrobiłeś. Jeśli nie wszystkie potrzebne dokumenty zostały załączone, napisz po rosyjsku, których brakuje. Wszystko poniżej linii --- zignoruj.

---

**Przed commitem (GitHub Desktop):** jeśli zmieniasz sekcję, zastąp w pliku całą swoją sekcję (od swojego nagłówka ## do następnego ##). Jeśli tworzysz nowy plik, wklej do niego całą zawartość bloku kodu z odpowiedzi agenta. W diffie mogą być zmienione tylko wiersze Twojego zadania. Jeśli zmiany obejmują cały plik albo w tekście pojawiły się rosyjskie słowa, nie commituj, poproś agenta jeszcze raz.

**W PR napisz własnymi słowami:** co zrobiono i po co to w projekcie.

**Nie rozumiesz?** napisz „nie rozumiem X, rozumiem Y”.