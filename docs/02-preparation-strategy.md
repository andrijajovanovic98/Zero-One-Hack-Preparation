# Preparation Strategy — Phase 1 & 2

A felkészülés két fázisra oszlik: alapok lerakása, majd egy újrahasznosítható technikai starter összerakása.

---

## Phase 1 — Foundation

Ebben a szakaszban felépítjük a közös alapokat.

### Feladatok

- csapat véglegesítése
- technológiai stack eldöntése → lásd [Tech Stack](03-tech-stack.md)
- szerepkörök meghatározása → lásd [Team Roles](04-team-roles.md)
- közös repo létrehozása (ez az!)
- standard workflow kialakítása → lásd [Git Workflow](09-git-workflow.md)
- gyors kommunikációs szabályok rögzítése → lásd [Communication & Risk](10-communication-and-risk.md)

### Kimenet

A csapatnak legyen:

- közös GitHub repo-ja
- branch stratégia
- task lista
- alap mappastruktúra
- induló README (ez)
- egyeztetett kommunikációs csatorna (Discord / WhatsApp / Slack)

### Definition of Done

Phase 1 akkor kész, ha:

- [ ] minden csapattag hozzáfér a repóhoz és tud rá pusholni
- [ ] mindenki tudja, mi az ő fő felelőssége
- [ ] meg van egy fix kommunikációs csatorna
- [ ] mindenki fel tudja húzni az env-et saját gépen (fut a `python -c "import pandas, sklearn, xgboost"` hiba nélkül)

---

## Phase 2 — Reusable Technical Starter

A cél, hogy a hackathonon **ne nulláról induljunk**. Péntek este a case reveal után csak a domain-specifikus részeket kelljen írni, ne az infrastruktúrát.

### Előre elkészítendő modulok

#### 1. Data loading layer

`src/data/load.py`

- CSV / JSON / parquet beolvasás egységes interfészen
- alap validáció (sor/oszlopszám, duplikátumok, üres oszlopok)
- hiányzó értékek jelzése (mennyi, hol)
- oszloptípusok ellenőrzése és castingja
- **bonus:** automata profilozó (describe + nunique + missing %) egy függvényben

#### 2. Preprocessing layer

`src/data/preprocess.py`

- numerikus / kategorikus oszlop auto-detektálás
- basic encoding (OneHot small, TargetEncoder large cardinality)
- scaling (StandardScaler / RobustScaler)
- train/validation split (random + **time-aware** változat!)
- outlier handling opcionális flag

#### 3. Modeling layer

`src/models/train.py`

- baseline classification (logistic regression + random forest + xgboost)
- baseline regression (linear + random forest + xgboost)
- anomaly detection baseline (isolation forest + one-class SVM)
- idősor kezelő alapsablon (Prophet wrapper + naive baseline)
- **fontos:** egységes `fit(X, y) → model` interfész, hogy cserélhetőek legyenek

#### 4. Evaluation layer

`src/models/evaluate.py`

- classification: accuracy, precision, recall, F1, AUC-ROC, AUC-PR, confusion matrix
- regression: MAE, RMSE, MAPE, R²
- threshold tuning helper (cost-asymmetric esetre)
- egyszerű vizualizációk: feature importance plot, ROC curve, residual plot
- **bonus:** "evaluate_all(model, X_val, y_val) → dict + figures" one-liner

#### 5. Inference layer

`src/models/predict.py`

- egy gyors script vagy API, ami egy inputból predikciót ad
- batch mode (CSV in → CSV out)
- single-row mode (dict in → dict out)
- FastAPI endpoint sablonnal

#### 6. Demo layer

`src/demo/app.py`

- Streamlit app sablon, ami:
  - betölt egy modellt
  - enged fájlt uploadolni
  - vagy manuálisan paramétert állítani
  - mutat eredményt + egy vizualizációt
- fallback: Jupyter notebook, ami végigmegy a flow-n (ha Streamlit eltörik)

---

## Előre megépítendő mini starterek

Jó, ha van 2–3 "drop-in" notebook:

- **classification_starter.ipynb** — load → preprocess → 3 baseline → evaluate → feature importance
- **anomaly_starter.ipynb** — load → preprocess → isolation forest → ranked list → top-N inspect
- **timeseries_starter.ipynb** — load → resample → naive + prophet → MAE/RMSE → plot

Ezekben csak az adatbetöltést kell átírni a hackathon hétvégéjén.

---

## Milestone timeline (előtte 2 hét)

| Hét | Fókusz | Deliverable |
|---|---|---|
| T-2 | Phase 1 + starter skeletonok | repo + env + 3 üres notebook fut |
| T-1 | 2 mini-projekt + pitch sablon | kitöltött notebookok + slide deck template |
| T-3 nap | Pressure test + finomítás | lefutott 8 órás próba hackathon |
| T-1 nap | Environment check + pihenés | minden gépen zöld env, korán aludni |

Részletek: [Practice Plan](05-practice-plan.md) és [Checklists](11-checklists.md).
