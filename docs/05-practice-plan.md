# Practice Plan — Mini-projektek és pressure test

A felkészülés legfontosabb része **nem a sztereotip tanulás**, hanem a **valódi futásgyakorlás**: ugyanolyan típusú feladatokat megcsinálni, mint amik a hackathonon lesznek, időnyomás alatt.

---

## 1. Mini banking project

### Cél

Gyakorolni a "tabular classification + magyarázhatóság" flow-t.

### Feladat

- tranzakciós adathalmaz (pl. Kaggle: [Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) vagy [IEEE-CIS Fraud Detection](https://www.kaggle.com/c/ieee-fraud-detection))
- csalásgyanús rekordok jelölése
- baseline classifier (logistic regression → random forest → xgboost)
- rangsorolás: top-100 legkockázatosabb tranzakció
- rövid magyarázat: mi alapján jelölte (SHAP vagy feature importance)

### Time box

**Maximum 6 óra, 2 ülésben.**

### Deliverable

- notebook, ami végig fut
- `scripts/train.py`, ami reprodukálja a modellt
- rövid README a repo-részben
- 1 db plot: feature importance
- 1 db plot: ROC curve vagy PR curve
- 1 szám: F1 vagy AUC a test seten

### Amire figyelj

- **time-aware split** — ne random split legyen, hanem a későbbi tranzakciók legyenek a test set
- **imbalanced** target kezelése: `class_weight='balanced'` vagy `scale_pos_weight`
- **threshold tuning** — ne default 0.5 legyen, hanem amit az F1 maximalizál

---

## 2. Mini industry project

### Cél

Gyakorolni a "time series + anomaly" flow-t.

### Feladat

- szenzor idősorok (pl. Kaggle: [NASA Turbofan Engine Degradation](https://www.kaggle.com/datasets/behrad3d/nasa-cmaps), vagy [Bearing Dataset](https://www.kaggle.com/datasets/brjapon/gearbox-fault-diagnosis))
- anomália keresés (isolation forest vagy rolling z-score)
- failure probability becslés utolsó N lépés alapján
- egyszerű dashboard: idővonal + anomáliák kiemelve

### Time box

**Maximum 6 óra, 2 ülésben.**

### Deliverable

- notebook, ami végigfut
- `scripts/detect_anomalies.py`
- Streamlit dashboard: `streamlit run app.py` és látszik a grafikon
- 1 szám: mennyivel a failure előtt jelez a modell (early warning window)

### Amire figyelj

- **feature engineering idősoron**: rolling mean/std/min/max, slope, FFT ha kell
- **ne data leakage**: jövőbeli értékek ne kerüljenek a feature-be
- **vizualizálj** — az anomaly detection egyik fő eladhatósága, hogy látszik a plot

---

## 3. Pressure test session

**Legalább egyszer csináljunk egy 6–10 órás mini-hackathont.**

### Miért

Nem a tökéletes eredmény a cél, hanem hogy begyakoroljuk, **hogyan dolgozunk együtt időnyomás alatt**. Ez deríti ki a lyukakat a workflow-ban.

### Setup

- válasszunk egy olyan Kaggle competition-t vagy public datasetet, amit a csapatból **senki sem látott még**
- idő: 8 óra (pl. szombat 10:00 – 18:00)
- mindenki a saját szerepében
- commit minden 30 percben

### Menet (8 órás változat)

| Idő | Fókusz |
|---|---|
| 0:00–0:45 | Problem understanding, scope, adatok megismerése |
| 0:45–2:00 | Data pipeline + első baseline |
| 2:00–4:00 | Modell iteráció + evaluation |
| 4:00–5:00 | Demo flow összerakása |
| 5:00–6:30 | Finomítás (vagy pitch, ha korábban kész) |
| 6:30–7:30 | Pitch deck + próba |
| 7:30–8:00 | Retrospektíva |

### Retrospektíva kérdései

A teszt után 30 perc retrospektíva, a következő kérdések körül:

1. Mi működött jól?
2. Hol veszítettünk a legtöbb időt?
3. Mi blokkolta a csapatot?
4. Mit csinálnánk másképp legközelebb?
5. Miből kellene még előre starter?

A válaszokat írjuk le a repoba (pl. `docs/retrospective-YYYY-MM-DD.md`), hogy legyen tanulság.

---

## 4. Pitch próba (külön alkalom)

Nem kell hackathonhoz kötni, bárki csapattag gyakorolhat pitchet egy korábbi projektről.

### Formátum

- 90 másodperces pitch
- 3 felvétel egymás után
- utána csapat feedback

### Mit figyelünk

- érthető-e annak, aki nem ismeri a projektet
- van-e **konkrét szám** benne (eredmény, impact)
- van-e egyértelmű "mit csinál ez" mondat az elején
- eladja-e az üzleti értéket, vagy csak technikailag beszél

---

## 5. Submission dry run

Ez gyakran kimarad, de nagyon fontos.

**1 héttel a hackathon előtt**: menjetek végig egy fake submissionön.

- nyissa meg valaki a competition/hackathon szabályokat
- nézzétek meg: hova kell feltölteni? milyen formátumban? mekkora fájlokban?
- töltsetek fel **valamit** (akár egy üres placeholder-t) a submission felületre, ha van
- győződjetek meg, hogy mindenkinek van hozzáférése

**Szabály:** a submission nem a vasárnap délutáni meglepetés része. Azt előre kell tudni.

---

## Közös tanulság, amit mindig le kell vonni

Minden próba után, írd be ebbe a listába, amit tanultatok:

- `docs/lessons-learned.md` — retro tanulságok gyűjtőhelye
- mielőtt a következő próbába belemész, olvasd át
- a hackathon előtt pár nappal olvassátok át közösen

**A tanulás csak akkor ér valamit, ha a következő futásban alkalmazod.**

---

Kapcsolódó doksi: [Weekend Plan](06-weekend-plan.md) — a hackathon időbeosztása, amit ezzel a gyakorlással készítesz elő.
