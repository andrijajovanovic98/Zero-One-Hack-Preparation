# Focus Areas — Banking / Industry / Insurance

A trackek várhatóan üzleti és ipari problémák körül lesznek. A felkészülést ilyen típusú feladatokra optimalizáljuk. Nem egyetlen konkrét use case-re készülünk, hanem olyan **építőkockákra, amelyek több trackben is felhasználhatók**.

---

## Banking

### Lehetséges problématípusok

- fraud detection
- anomaly detection
- suspicious transaction ranking
- document understanding (KYC, szerződések)
- risk scoring (credit, counterparty)
- categorization and prioritization

### Jellemző adatformák

- tranzakciós táblák (timestamp, amount, merchant, category, user_id)
- ügyfél profil adatok
- idősorok számlaegyenlegről
- scanned dokumentumok vagy strukturált PDF

### Tipikus metrikák

- precision @ top-K (fraud alerts esetén ez fontos, mert az emberi review költséges)
- recall adott precision mellett
- AUC-ROC, AUC-PR (PR jobb, ha nagyon imbalanced)
- kézben tartható false positive rate

### Készülni érdemes

- imbalanced classification trükkökre (SMOTE, class weights, threshold tuning)
- time-aware train/test splitre (leakage elkerülésére)
- magyarázhatóság alapokra (SHAP, feature importance) — a banki zsűri ezt várja

---

## Industry

### Lehetséges problématípusok

- predictive maintenance
- sensor anomaly detection
- time series forecasting
- quality deviation detection
- process optimization
- root cause analysis

### Jellemző adatformák

- multivariate idősorok (sok szenzor, magas mintavételi frekvencia)
- esemény logok (failure timestamps)
- gép konfigurációs metaadatok

### Tipikus metrikák

- MAE / RMSE / MAPE (forecasting)
- early warning window (mennyivel a hiba előtt jelez)
- false alarm rate
- time-to-detect

### Készülni érdemes

- rolling window feature engineeringre (mean, std, min, max, slope utolsó N lépésben)
- gyors anomaly baseline-okra (Isolation Forest, One-Class SVM, rolling z-score)
- Prophet / ARIMA / naive baseline-okra forecastinghoz
- FFT / spektrális feature-ökre, ha van magas frekvenciás jel

---

## Insurance

### Lehetséges problématípusok

- claim triage (melyik claim megy emberi review-ra)
- severity estimation (várható kifizetés összege)
- underwriting risk analysis
- document classification (claim form típusok)
- pattern detection in claims (fraud ringek)
- duplicate claim detection

### Jellemző adatformák

- claim adatok (structured fields + szabad szöveges leírás)
- ügyfél history
- scanned dokumentumok, fotók

### Tipikus metrikák

- regressziós hibák (severity)
- classification metrikák (triage)
- kézi review idő/költség megtakarítás szimulálva

### Készülni érdemes

- text embedding + classification kombóra (claim description → risk)
- egyszerű multi-modal pipeline-ra (text + structured)
- threshold tuningra, mert insurance-ben a cost-asymmetry erős

---

## Cross-cutting: mindhárom területen hasznos

Függetlenül attól, melyik track jön, ezek mindig jönnek jól:

- **tiszta train/validation/test split** — lehetőleg time-aware
- **baseline modell pár perc alatt** — logistic regression vagy random forest
- **legalább egy mérőszám** — ami üzletileg is érthető
- **egy magyarázó vizualizáció** — feature importance, confusion matrix, vagy ranked list
- **egy működő inference endpoint** — akár CLI script, akár FastAPI

---

## Cheat sheet: "melyik problématípus → mit próbálj először"

| Probléma | Első baseline | Ha marad idő |
|---|---|---|
| Fraud / anomaly (tabular) | Isolation Forest + logistic regression | XGBoost + SHAP |
| Classification (tabular) | Random Forest / XGBoost | LightGBM + threshold tuning |
| Regression (tabular) | Linear + Random Forest | LightGBM + feature engineering |
| Time series forecast | Naive (last value) + Prophet | LightGBM on lag features |
| Anomaly in time series | Rolling z-score | Isolation Forest on rolling features |
| Document classification | TF-IDF + logistic regression | Sentence-transformers + classifier |
| Image / photo | Pretrained ResNet features + classifier | Fine-tune only ha tényleg kell |

Kapcsolódó doksi: [Preparation Strategy](02-preparation-strategy.md) — itt vannak a konkrét előre megépítendő modulok.
