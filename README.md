# Analiza i wizualizacja danych — Heart Disease

Praca zaliczeniowa z przedmiotu *Analiza i wizualizacja danych — Pandas, Data Frame*
(WSB Merito Chorzów, 2025/2026 lato). Statystyczna analiza publicznego zbioru
**UCI Heart Disease (Cleveland)**: od statystyki opisowej, przez wnioskowanie
(testy hipotez, korelacja, regresja, ANOVA, proporcje), po model predykcyjny
(regresja logistyczna + ROC/AUC).

## Sekcja projektowa
- Członkowie: Michał Wesołowski, Szymon Woźny
- Grupa dziekańska: _(do uzupełnienia)_
- Tytuł projektu: Analiza czynników ryzyka choroby serca

## Pytania badawcze
1. Czy poziom cholesterolu różni się między pacjentami z chorobą serca i bez? (test t / Mann–Whitney)
2. Czy maksymalne tętno zależy od wieku? (korelacja + regresja prosta)
3. Czy maksymalne tętno można przewidzieć z wieku, ciśnienia i obniżenia ST? (regresja wieloraka)
4. Czy maksymalne tętno różni się między typami bólu w klatce? (ANOVA + Tukey)
5. Czy częstość choroby zależy od płci, a dławica wysiłkowa od statusu choroby? (test proporcji / chi-kwadrat)
6. Jak modelować prawdopodobieństwo choroby serca? (regresja logistyczna + ROC/AUC)

Każda analiza zawiera **sprawdzenie założeń** i — gdy potrzeba — odporną alternatywę.

## Uruchomienie
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

## Struktura
```
analysis.ipynb        # główna narracja (RQ1–RQ6)
raport.docx           # raport z wynikami i wnioskami (Word)
prezentacja.pptx      # prezentacja (PowerPoint, 12 slajdów)
data/raw/             # surowe dane UCI + dokumentacja
data/README.md        # źródło, licencja, słownik zmiennych
figures/              # wygenerowane wykresy
requirements.txt
submission.txt        # plik oddawany w Moodle (link do repo/OneDrive)
```

## Źródło danych
UCI ML Repository — Heart Disease Data Set (Detrano i in., 1989). Szczegóły w `data/README.md`.
