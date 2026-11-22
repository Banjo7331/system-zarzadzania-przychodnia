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
