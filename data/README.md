# Dane — UCI Heart Disease (Cleveland)

## Źródło
- UCI Machine Learning Repository — *Heart Disease Data Set*.
- Plik użyty: `raw/processed.cleveland.data` (303 obserwacje, podzbiór 14 atrybutów).
- Pobrano: 2026-05-26 z
  `https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/processed.cleveland.data`
- Dokumentacja: `raw/heart-disease.names`.
- Twórcy danych: Robert Detrano (V.A. Medical Center, Long Beach & Cleveland Clinic Foundation)
  oraz A. Janosi, W. Steinbrunn, M. Pfisterer. Cytowanie: Detrano i in. (1989).
- Licencja: UCI ML Repository (do użytku naukowego/edukacyjnego z podaniem źródła).

## Format pliku surowego
CSV bez nagłówka, 14 kolumn, braki danych oznaczone `?` (w `ca` i `thal`).

## Słownik zmiennych (14 atrybutów)
| # | Zmienna | Typ | Opis / kodowanie |
|---|---------|-----|------------------|
| 1 | `age` | ciągła | wiek (lata) |
| 2 | `sex` | binarna | 1 = mężczyzna, 0 = kobieta |
| 3 | `cp` | kategorialna | typ bólu w klatce: 1 typowa dławica, 2 nietypowa dławica, 3 ból niedławicowy, 4 bezobjawowy |
| 4 | `trestbps` | ciągła | ciśnienie spoczynkowe (mm Hg) |
| 5 | `chol` | ciągła | cholesterol w surowicy (mg/dl) |
| 6 | `fbs` | binarna | cukier na czczo > 120 mg/dl (1 = tak) |
| 7 | `restecg` | kategorialna | spoczynkowe EKG: 0 norma, 1 nieprawidłowości ST-T, 2 przerost LK |
| 8 | `thalach` | ciągła | maksymalne osiągnięte tętno |
| 9 | `exang` | binarna | dławica wysiłkowa (1 = tak) |
| 10 | `oldpeak` | ciągła | obniżenie ST (wysiłek vs spoczynek) |
| 11 | `slope` | kategorialna | nachylenie odcinka ST: 1 rosnące, 2 płaskie, 3 opadające |
| 12 | `ca` | porządkowa | liczba dużych naczyń (0–3) barwionych fluoroskopią |
| 13 | `thal` | kategorialna | 3 = norma, 6 = wada stała, 7 = wada odwracalna |
| 14 | `num` → `target` | binarna | oryg. 0–4 (stopień zwężenia); binaryzacja: 0 = brak choroby, ≥1 = choroba |

## Czyszczenie (realizowane w `analysis.ipynb`)
1. Wczytanie z nazwami kolumn, `?` → `NaN`.
2. `ca`, `thal` → typ numeryczny; obsługa braków (usunięcie ~6 wierszy lub imputacja — udokumentowana).
3. Binaryzacja celu: `target = (num > 0).astype(int)`.
4. Rzutowanie zmiennych kategorialnych na `category` do analiz grupowych.
