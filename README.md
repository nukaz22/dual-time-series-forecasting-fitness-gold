# A Dual Study on Gold Prices and Personal Fitness Tracking Data

Dieses Projekt kombiniert zwei unterschiedliche Zeitreihenquellen zur Anwendung, Analyse und zum Vergleich klassischer und moderner Forecasting-Methoden.

- Teil 1: Selbst erhobene Fitnesszeitreihe (Trainingsdauer pro Tag)
- Teil 2: Öffentliche Finanzdaten (Tagesgenaue Goldpreise)

Ziel ist die Untersuchung saisonaler Muster, Trendverläufe, Stationarität und Modellgüte mit Fokus auf MAE, RMSE, MAPE und R².

## Projektinhalt

- `SS25_FOEM_ipynb_Part1_Nurullah_Kazak.ipynb`: Analyse und Vorhersage selbst erfasster Fitnessdaten
- `SS25_FOEM_ipynb_Part2_Nurullah_Kazak.ipynb`: Forecasting öffentlicher Goldpreisdaten
- `SS25_FOEM_FinalPaper_Nurullah_Kazak.pdf`: Wissenschaftlicher Abschlussbericht

## Methodenübersicht

Beide Zeitreihen wurden hinsichtlich folgender Punkte analysiert:

- Visuelle Trendanalyse und statistische Tests (ADF)
- Transformationen (Logarithmus, Differenzierung)
- Saisonalitätsprüfung mittels STL-Decomposition
- ACF/PACF-basierte Modellinitialisierung
- Modelle:
  - Naive Forecast
  - ARIMA
  - Prophet

## Ergebnisse

### Fitnessdaten (Teil 1)

- Starke Nicht-Stationarität in Rohdaten
- Saisonale Trainingsmuster (Wochenstruktur)
- Prophet konnte kurzfristige Entwicklungen besser erfassen als ARIMA

### Goldpreise (Teil 2)

- Hohe Volatilität und langfristiger Aufwärtstrend ab 2020
- Prophet zeigte im Testzeitraum bessere Prognosegüte (MAPE ≈ 13.4%) als ARIMA und Naive Forecast
- ARIMA (1,1,1) basierend auf ACF/PACF, Prophet trainiert auf log-transformierter Serie

## Forecasting-Metriken (Goldpreis – Vergleich auf Testdaten)

| Modell   | MAE     | RMSE     | MAPE (%) | R²      |
|----------|---------|----------|----------|---------|
| Naive    | 13,641  | 15,625   | 20.27    | -3.20   |
| ARIMA    | 13,636  | 15,620   | 20.26    | -3.20   |
| Prophet  |  9,071  | 10,724   | 13.38    | -0.98   |

## Voraussetzungen

```bash
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
prophet
pmdarima
