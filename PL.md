# Effort w Claude — ściągawka

**Effort nie robi Claude'a mądrzejszym. To, jak mądry jest Claude, zależy od modelu. Effort decyduje, ile Claude sprawdza własną pracę:** ile plików czyta, ile testów uruchamia i ile kroków robi, zanim wróci do ciebie. (Anthropic: Lydia Hallie, Thariq Shihipar)

W Claude Code zmienisz go komendą `/effort` (także w trakcie rozmowy). Poziomy: `low` · `medium` · `high` · `xhigh` · `max`.

## Który poziom do jakiego zadania

| Poziom | Do czego | Przykład |
|---|---|---|
| **low** | pomysły, szkice, drobne zmiany, wszystko, co od razu oglądasz | „napisz 3 wersje tego maila”, „zmień nazwy tych plików” |
| **medium** | zwykła codzienna praca | nowa funkcja, skrypt, który przejrzysz |
| **high** | wszędzie tam, gdzie błąd kosztowałby cię pieniądze albo są ukryte przypadki brzegowe | błąd w starym kodzie, sumy w arkuszu, który wyślesz klientowi |
| **max** | długie zadania, które Claude robi sam | zbudować i przetestować całą aplikację od początku do końca |

## Rutyna inżyniera z Anthropic

1. Daj Claude'owi zadanie i poproś, żeby **dopytał cię** o brakujące szczegóły.
2. **Buduj na low.**
3. **Przeglądaj i poprawiaj na low** — szybkie pętle, poprawiasz go w minutę.
4. **Na końcu przełącz na high**, żeby wszystko sprawdzić i przetestować.

## Co mówią liczby

- Ta sama prosta aplikacja fitness: **1,5 min na low, 67 min na max** (test Anthropic).
- Filtr bezpieczeństwa (sanitizer HTML): **1/5 na low → 5/5 na xhigh** — effort opłaca się przy długich zadaniach z ukrytymi pułapkami.
- Mój test (Opus 5.5, po 3 przebiegi): wyciąg z banku z podwójną płatnością, zwrotem i kwotą zapisaną z przecinkiem. **Low: dobrze 3/3. High: ok. 60% więcej tokenów wyjściowych, a 1 przebieg inaczej zrozumiał pytanie.**
- Większy effort nie naprawi źle zrozumianego pytania. Jeśli wynik jest zły, bo Claude inaczej odczytał zadanie, popraw prompt zamiast podkręcać effort.

## Szybka zasada

**Zaczynaj od low. Podnoś dopiero, gdy Claude pominął plik, pominął test albo czegoś nie sprawdził — albo gdy błąd kosztowałby cię pieniądze.**

Źródła: [Spending your effort — Thariq Shihipar](https://claude.dev/blog/spending-your-effort) · [Claude Code effort level and model selection — Lydia Hallie](https://claude.com/resources/articles/claude-model-and-effort-level-in-claude-code)

— Kris · @aipractically
