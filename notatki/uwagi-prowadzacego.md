# Uwagi prowadzącego — zajęcia 24.10.2026

Zebrane z nagrania (`transkrypcja_zajecia_2026-10-24_oczyszczona.txt`). Część uwag dotyczyła innych zespołów, ale odnoszą się do wszystkich projektów.

## Uwagi do naszego projektu (przychodnia)

- **Aktor, który nic nie robi, nie może istnieć.** Dziedziczy się wyłącznie zachowanie (przypadki użycia). Aktor w hierarchii musi mieć swoje przypadki.
- **Prawie nie ma zależności między przypadkami użycia** — trzeba ich aktywnie szukać. Przykład prowadzącego: lekarz przegląda harmonogram/wizytę i z tego poziomu zleca zabieg pielęgniarzowi (`«extend»`).
- **Zakres był za szeroki** („przychodnie, gabinety stomatologiczne, centra rehabilitacji”) — wybrać jedno i szczegółowo opisać, jak ta przychodnia działa.
- Propozycja wizyta: forma (teleporada / stacjonarna) została przyjęta, ale padło pytanie, czym konkretnie różnią się podklasy. **Każda podklasa musi mieć własne cechy** (atrybuty lub metody), a nie tylko nazwę.

## Diagram przypadków użycia

### Poziom abstrakcji
- Na diagramie zostają tylko przypadki **uruchamiane bezpośrednio przez aktora** (poziom 1).
- Przypadek wywoływany tylko w ramach innego (np. zmiana statusu w ramach przeglądu) to poziom 2 — wypada z diagramu.
- Przypadek bez aktora = zły poziom albo brakująca asocjacja.

### Zależności
- **Include vs extend:** jeśli pasuje jedno i drugie, zostaw **extend** — „extend może być wykorzystany jako include, a odwrotnie nie”. Przykład: klient przegląda rezerwacje i przy okazji jedną potwierdza → `Potwierdzenie «extend» Przeglądanie`.
- Między przypadkami **różnych aktorów zwykle nie ma zależności** (inna sesja). Korzystanie z tych samych danych to za mało. Wyjątek: aktor odziedziczony = ta sama osoba.
- Nie łączyć przypadków z różnych przebiegów systemu (między nimi upływa czas).
- Warunki przy `«extend»` są pożądane (np. potwierdzenie / zaliczka zależne od liczby osób).
- Przypadek połączony z kilkoma aktorami różnych kategorii jest podejrzany — sprawdzić, czy każdy realizuje go podobnie.
- **Między przypadkami nie ma asocjacji**, tylko zależności.

### Aktorzy
- Szukać funkcji wspólnych i wynosić je do aktora abstrakcyjnego (np. *Użytkownik zarejestrowany* → *Przeglądanie rezerwacji*).
- Nie tworzyć aktora abstrakcyjnego dla jednej funkcji.
- Aktor czasowy: podać częstotliwość lub moment. Aktor-system: podać jaki system. Sam „System” jako aktor jest niedopuszczalny.

### Nazwy
- Nazwa przypadku musi zawierać formę czasownika (*sprawdzenie, dodawanie, anulowanie*), nie warunek ani informację („brak potwierdzenia zaliczki” ✗).

### Wygląd
- **Bez kolorów, ale z tłem** — eksport: styl *Transparent* + **PNG with background**. Diagram bez tła jest mało czytelny.
- Hierarchia dziedziczenia rośnie **w dół**, notacja łączna (jeden wspólny trójkąt).
- Aktorzy spoza hierarchii — **po prawej stronie**, nie wstawieni między aktorów z hierarchii.
- Aktorzy na zewnątrz, w środku tylko przypadki użycia. Prostokąt systemu opcjonalny.
- Zależności nie mogą się nakładać ani nieczytelnie krzyżować.
- Extension pointy tylko tam, gdzie potrzebne.
- Visual Paradigm **Community Edition**, nie wersja próbna.

## Wymagania i diagram klas

- Ok. **10–12 przypadków użycia**, diagram klas **10–15 klas**. Gdy wychodzi więcej — wyciąć spójną grupę funkcji, nie pojedyncze elementy.
- Wymagania muszą być szczegółowe: co jest pamiętane o każdym obiekcie (jak w tekście *Restauracje*).
- Przypadek, o którym nie ma nic w części opisowej (np. raporty bez opisu ich zawartości), **wylatuje**. Z opisu mogą też wyniknąć nowe przypadki.
- **Dziedziczenie nietrywialne:**
  - nie może dotyczyć osób („zawsze się da, ale wygląda tak samo w każdym systemie”),
  - zwykły rozłączny podział jest trywialny — potrzebne: nierozłączne (overlapping), wieloaspektowe, dynamiczne lub wielokrotne,
  - każda podklasa ma własne cechy,
  - musi wynikać wprost z tekstu wymagań (przykład: koncerty plenerowe/w sali + indywidualne/zespołowe).
- Najłatwiejsze: nierozłączne i wieloaspektowe; dynamiczne dość często; wielokrotne najrzadziej.
- Projekt powinien odwzorowywać coś realnego — łatwiej rozszerzać wymagania.

## Terminarz (stan z 24.10)

- Następne zajęcia: scenariusz przypadku użycia + diagram aktywności, uszczegółowienie wymagań.
- Kolejne: diagram klas.
- Diagram przypadków użycia można zaktualizować, gdy wymagania będą w miarę ostateczne.

---

# Uwagi prowadzącego — zajęcia 14.11.2026 (omówienie scenariuszy)

Z nagrania `transkrypcja_zajecia_2026-11-14_oczyszczona.txt`. Prowadzący omawiał scenariusze wszystkich zespołów — z naszych: *Zlecenie zabiegu*, *Rezerwacja wizyty*, *Wystawienie dokumentu medycznego*.

## Uwagi do naszych scenariuszy

### Zlecenie zabiegu
- Scenariusz mówi „w trakcie obsługi wizyty”, ale **na diagramie nie ma takiej zależności** (np. `«extend»` z *Dodawania opisu wizyty*) → scenariusz niezgodny z diagramem.
- „System wyświetla dane pacjenta i wizyty” — **jakie dane?** Wypisać konkretne pola (np. imię, nazwisko, PESEL — rzadko wszystkie).
- „Zalecenia” — doprecyzować, że to opis tekstowy.
- Lista pielęgniarzy — **co widać o każdym** (imię, nazwisko, identyfikator?).
- Podsumowanie — jakie dokładnie pola.
- „System rejestruje zlecenie” = **operacja wewnętrzna** → usunąć.
- 2c (brak gabinetu zabiegowego) — w scenariuszu nigdzie nie wybieramy gabinetu, więc nie ma podstaw, żeby to stwierdzić. Albo dodać świadomy wybór gabinetu (i ująć to w modelu), albo usunąć.
- 5a (powiadomienie się nie wysłało) — to błąd techniczny, nie przebieg biznesowy → usunąć.

### Rezerwacja wizyty
- Pytanie, czy rezerwacja ma być **tylko dla pacjenta**. Skoro celem jest ograniczenie telefonów, to po co recepcja zmienia terminy? → **pracownik recepcji praktycznie nie ma roli**. Trzeba to świadomie rozstrzygnąć.
- Brakuje szczegółów: co o każdej usłudze, co o każdym lekarzu, co o terminie (godzina rozpoczęcia? czas trwania?).
- Wyświetlenie rodzajów wizyty i wybór → **jeden punkt**.
- „System sprawdza” = operacja wewnętrzna → usunąć.
- Kropki w numeracji niepotrzebne.
- 2a „system nie może wyświetlić listy” = wyjątek techniczny → usunąć.
- Lista oczekujących: „system zapisuje wpis” = wewnętrzne; może za to poinformować, że zapisał. Zapis kończy przypadek użycia.
- „Termin zajęty w międzyczasie” — zostaje.
- Potwierdzenie wizyty to **osobny przypadek użycia**, nie część rezerwacji.
- Warunek końcowy za mało szczegółowy.

### Wystawienie dokumentu medycznego
- Zalogowanie **nie jest** warunkiem początkowym.
- Status „potwierdzona” jak wyżej. Jeśli dokument można wystawić **tylko w trakcie wizyty**, to jest to przypadek **wewnętrzny (poziom 2)** i wypada z diagramu. Jeśli ma zostać na poziomie 1, musi dać się uruchomić **bezpośrednio przez lekarza**, bez kontekstu — wtedy lekarz najpierw wybiera wizytę. **To samo dotyczy Zlecenia zabiegu.** Trzeba zdecydować.
- Wyświetlenie rodzajów dokumentów + wybór → jeden punkt.
- Co jest w formularzu? Wypisać pola.
- „System nadaje numer, zapisuje” = wewnętrzne.
- „Lekarz wpisał błędne dane” — jakie dane mogą być błędne?
- **Najważniejsze:** brakuje osobnych wątków dla **recepty, skierowania i zwolnienia** — każdy ma inne pola do wypełnienia.

## Ogólne zasady pisania scenariuszy

- **Zalogowanie to nie warunek początkowy** — to wynika z modelu.
- Warunek początkowy = co **musi istnieć w systemie** (np. „istnieje zaplanowana teleporada przypisana do lekarza”). Jeśli nie istnieje — przepływ alternatywny („brak teleporad”).
- **Żadnych operacji wewnętrznych** (system generuje, sprawdza, zapisuje, rejestruje, nadaje numer, przypisuje). Zostaje tylko to, co aktor **widzi na ekranie** i co **wprowadza**. Można dać komunikat w stylu „wyświetla potwierdzenie zapisania”.
- **Akcja + reakcja w jednym punkcie** — mniej punktów.
- **Konkretne dane:** wypisać, co jest wyświetlane i wprowadzane (pola, kolumny listy). Chodzi o to, żeby dało się sprawdzić, czy model (diagram klas) te informacje ma.
- Przypadek uruchamiany **bezpośrednio przez aktora nie ma kontekstu** — najpierw trzeba wybrać obiekt (lista z określonymi informacjami, np. aktualna teleporada wyróżniona na górze, ale z możliwością wyboru innej).
- Jeśli przypadek da się uruchomić i bezpośrednio, i z innego (`«extend»`) — pokazać oba starty: jeden w przepływie głównym, drugi jako wątek alternatywny, **i zaznaczyć zależność na diagramie**.
- Czynności poza systemem (rozmowa, badanie, telefon) nie są krokami — najwyżej start i zakończenie.
- **Numeracja alternatyw powiązana z krokiem głównym:** `5a`, zagnieżdżone `5aa`, `5ab`. Na końcu wątku: dokąd wracamy (który krok) albo że przypadek się kończy.
- Formułowanie decyzji: „Aktor zdecydował się na wybór innego miejsca” zamiast „Aktor wybiera inne miejsce”.
- **Pomijamy błędy techniczne** (serwer, wysyłka maila, brak listy) — zakładamy, że system działa poprawnie.
- System zewnętrzny (np. płatności): napisać tylko, że jest uruchamiany i z jakim statusem wracamy — bez szczegółów jego działania.
- Przypadek „tylko przeglądanie” to za mało — przeglądamy *po coś*. Ustalić, jakie operacje są dostępne na liście: jedna w przepływie głównym, reszta w alternatywnych.
- Mieć pod ręką **diagram przypadków użycia przy każdym scenariuszu** i trzymać go aktualnym.
- **Spójność ponad wszystko:** zmiana w jednym miejscu → poprawić wszędzie (scenariusz, diagram, wymagania, model).

## Zadanie na kolejne zajęcia

- **Diagram klas** na podstawie wymagań — z informacjami potrzebnymi do realizacji przypadków użycia. Czego brakuje w wymaganiach — dopisać, co źle sformułowane — poprawić.
- Omówienie za tydzień–dwa. Później będzie drugi diagram klas z rozszerzeniami.
- Później: diagram aktywności do scenariusza — przy tej okazji poprawić scenariusz (i diagram przypadków użycia).
