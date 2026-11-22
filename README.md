# System zarządzania przychodnią

Projekt z przedmiotu **Modelowanie systemów informatycznych (MSI)**, SGGW, semestr zimowy 2026/27.

**Zespół:** Ćwikilewicz, Cylwik, Lachor

## Zawartość

| Folder | Co jest w środku |
|---|---|
| `wymagania/` | wymagania wstępne (punkty 1–5) — `.docx` do edycji, `.pdf` do oddania |
| `diagramy/` | diagramy UML — eksporty `.png` (projekt `.vpp` z Visual Paradigm też tutaj) |
| `scenariusze/` | scenariusze przypadków użycia |
| `polecenia/` | treści zadań, wzory i materiały od prowadzącego |
| `notatki/` | uwagi prowadzącego z zajęć i transkrypcje nagrań |

Zanim zaczniesz poprawki, przeczytaj [`notatki/uwagi-prowadzacego.md`](notatki/uwagi-prowadzacego.md).

## Zasady pracy

1. **Jeden plik = jedna osoba naraz.** Pliki `.docx` i `.vpp` są binarne — git nie połączy dwóch równoczesnych zmian. Zanim zaczniesz edytować plik, napisz na grupie, że go bierzesz.
2. **Nie pushujemy na `main`.** Każda zmiana idzie przez gałąź i pull request:
   ```bash
   git checkout main && git pull
   git checkout -b nazwa-zmiany
   # edycja plików
   git add . && git commit -m "Co zmieniłem"
   git push -u origin nazwa-zmiany
   ```
   Potem na GitHubie: **Compare & pull request** → reszta zespołu akceptuje → **Merge**.
3. Do każdego `.docx` dołączamy aktualny `.pdf`, a do `.vpp` aktualny eksport `.png`, żeby dało się przejrzeć zmiany bez otwierania programów.
4. Diagramy eksportujemy z **Visual Paradigm Community Edition**, styl *Transparent*, **PNG with background**.
