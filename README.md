# README

## Overview

Ez a repository a **Zero One Hack: Vienna's Supercompute AI Hackathon** felkészülésére készült.

A cél nem csak az, hogy “majd ott kitalálunk valamit”, hanem hogy a csapat már az esemény előtt rendelkezzen:

* közös technikai alappal,
* egy gyorsan újrahasznosítható projektstruktúrával,
* előre kiosztott szerepekkel,
* begyakorolt workflow-val,
* pitch sablonnal,
* és olyan technikai rutinokkal, amelyek 36 órás nyomás alatt is működnek.

Ez a repo tehát egy **hackathon operating system** a csapat számára.

---

## Main Goal

A fő célunk:

**a hackathon hétvégéjén a lehető leggyorsabban eljutni a case reveal pillanatától egy működő AI megoldásig, amelyet be lehet mutatni, mérni lehet, és el lehet adni a zsűri előtt.**

Nem a cél:

* túlbonyolított architektúra építése,
* tökéletes kódminőség hajszolása,
* felesleges feature-ök gyártása,
* túl sok idő elköltése designra,
* vagy irreális scope vállalása.

A cél:

* gyors értelmezés,
* gyors baseline,
* mérhető eredmény,
* működő demo,
* erős pitch.

---

## What Makes This Hackathon Different

Ez nem egy klasszikus “csináljunk egy appot OpenAI API-val” hackathon.

Itt az lesz a fontos, hogy:

* ténylegesen legyen valamilyen modell vagy modellezési logika,
* legyen kimutatható eredmény,
* legyen valós technikai mélység,
* és a megoldás ne csak egy UI mockup vagy wrapper legyen.

Ezért a felkészülésnek 4 pillére van:

1. **Problem solving under uncertainty**
   Gyorsan tudjunk értelmezni egy új use case-et.

2. **Technical execution under time pressure**
   Kevés idő alatt stabil baseline-t tudjunk összerakni.

3. **Team coordination**
   Ne egymást akadályozzuk, hanem párhuzamosan haladjunk.

4. **Storytelling and pitching**
   A végén világosan el tudjuk mondani, hogy mit építettünk és miért értékes.

---

## Team Philosophy

A hackathonon nem az nyer, aki a legszebb kódot írja, hanem az, aki:

* jól választ scope-ot,
* gyorsan hoz döntéseket,
* nem blokkolja a csapatot,
* és a végére kézzelfogható eredményt mutat.

Ezért a csapat működési elvei:

### 1. Working beats perfect

Először működjön. Az optimalizálás és szépítés csak utána jöhet.

### 2. Baseline first

Mindig legyen egy egyszerű, de működő első verzió.

### 3. Demo-driven development

Úgy fejlesztünk, hogy a végén demonstrálni tudjuk.

### 4. Timeboxing

Nem ülünk egy problémán végtelen ideig. Ha elakadunk, vágunk vagy egyszerűsítünk.

### 5. Clarity over cleverness

Hackathon alatt az egyszerű, érthető megoldás gyakran jobb, mint a bonyolult okosság.

---

## Recommended Focus Areas

Mivel a trackek várhatóan üzleti és ipari problémák körül lesznek, a felkészülést ilyen típusú feladatokra optimalizáljuk:

### Banking

Lehetséges problématípusok:

* fraud detection
* anomaly detection
* suspicious transaction ranking
* document understanding
* risk scoring
* categorization and prioritization

### Industry

Lehetséges problématípusok:

* predictive maintenance
* sensor anomaly detection
* time series forecasting
* quality deviation detection
* process optimization

### Insurance

Lehetséges problématípusok:

* claim triage
* severity estimation
* underwriting risk analysis
* document classification
* pattern detection in claims

A felkészülés során nem egyetlen konkrét use case-re készülünk, hanem olyan építőkockákra, amelyek több trackben is felhasználhatók.

---

## Preparation Strategy

## Phase 1 — Foundation

Ebben a szakaszban felépítjük a közös alapokat.

### Feladatok

* csapat véglegesítése
* technológiai stack eldöntése
* szerepkörök meghatározása
* közös repo létrehozása
* standard workflow kialakítása
* gyors kommunikációs szabályok rögzítése

### Kimenet

A csapatnak legyen:

* közös GitHub repo-ja
* branch stratégia
* task lista
* alap mappastruktúra
* induló README

---

## Phase 2 — Reusable Technical Starter

A cél, hogy a hackathonon ne nulláról induljunk.

### Előre elkészítendő modulok

#### 1. Data loading layer

* CSV / JSON / parquet beolvasás
* alap validáció
* hiányzó értékek kezelése
* oszloptípusok ellenőrzése

#### 2. Preprocessing layer

* feature selection
* basic encoding
* scaling
* egyszerű train/validation split

#### 3. Modeling layer

* baseline classification model
* baseline regression model
* anomaly detection baseline
* idősort kezelő alapsablon

#### 4. Evaluation layer

* pontosság / precision / recall / F1
* MAE / RMSE
* confusion matrix
* egyszerű vizualizációk

#### 5. Inference layer

* egy gyors script vagy API, ami egy inputból predikciót ad

#### 6. Demo layer

* nagyon egyszerű UI vagy notebook demo
* lehetőleg gyorsan prezentálható formában

---

## Recommended Stack

A hackathonhoz olyan stack kell, ami gyors, ismert és megbízható.

### Core

* Python
* Jupyter / notebooks
* pandas vagy polars
* numpy
* scikit-learn

### Modeling

* XGBoost / LightGBM / CatBoost
* PyTorch csak akkor, ha tényleg szükséges

### API / Demo

* FastAPI
* Streamlit
* vagy minimál React frontend, ha valaki gyors benne

### Visualization

* matplotlib
* plotly
* seaborn opcionális

### Collaboration

* GitHub
* GitHub Projects vagy egyszerű task board
* Discord / WhatsApp / Slack a gyors kommunikációhoz

### Optional

* Docker csak akkor, ha nem lassít
* MLflow csak akkor, ha valaki már nagyon rutinos benne

Hackathon alatt az eszköz akkor jó, ha gyorsít, nem akkor, ha imponál.

---

## Suggested Team Roles

Nem kell, hogy mindenki csak egy dolgot csináljon, de legyen fő felelősségi kör.

### 1. ML / Modeling Lead

Felelőssége:

* modellek kiválasztása
* baseline építés
* train és eval
* feature ötletek

### 2. Data / Pipeline Lead

Felelőssége:

* adat tisztítás
* input pipeline
* preprocessing
* fájlstruktúra és reproducibility

### 3. Product / Demo Lead

Felelőssége:

* demo flow
* UX logika
* use case értelmezés üzleti oldalról
* final presentation visual side

### 4. Pitch / Integration Lead

Felelőssége:

* storytelling
* slide deck
* final narrative
* feature-k összefűzése
* deadline management

Ha 2-3 fős a csapat, ezek a szerepek összevonhatók.

---

## Before The Event: What We Should Practice

## 1. One mini banking project

Példa:

* tranzakciós adathalmaz
* csalásgyanús rekordok jelölése
* baseline classifier
* rangsorolás és rövid magyarázat

## 2. One mini industry project

Példa:

* szenzor idősorok
* anomália keresés
* failure probability becslés
* egyszerű dashboard

## 3. One pressure test session

Legalább egyszer csináljunk egy 6–10 órás mini-hackathont.

### Menet

* 1 óra: problémaértelmezés
* 2 óra: adat + baseline
* 2 óra: javítások
* 1 óra: demo
* 1 óra: pitch

### Cél

Nem a tökéletes eredmény, hanem annak begyakorlása, hogyan dolgozunk együtt időnyomás alatt.

---

## Hackathon Weekend Plan

## Friday Night

### Objective

A case gyors megértése és a scope lezárása.

### Checklist

* pontosan mi a probléma?
* mi a bemenet?
* mi a kimenet?
* mi lesz a minimum működő megoldás?
* mi lesz a demo?
* mi lesz a mérőszám?

### Output péntek éjfélig

* 1 mondatos probléma-definíció
* 1 mondatos megoldási irány
* felosztott feladatok
* működő adatbetöltés
* baseline terv

Nagyon fontos: péntek este még ne akarjunk mindent megépíteni. Először világos döntéseket kell hozni.

---

## Saturday

### Objective

Megépíteni a működő rendszert.

### Prioritási sorrend

1. adat pipeline
2. baseline modell
3. mérés
4. inference vagy demo flow
5. jobb modell vagy extra feature
6. pitch anyag

### Saturday danger zones

* túl sokat vitatkozni az irányon
* túl sok modellt kipróbálni eredmény nélkül
* túl korán UI-ra menni
* túl későn elkezdeni a pitch-et

### Saturday end goal

Szombat estére legyen:

* működő baseline
* mérhető eredmény
* demo vázlat
* pitch outline

---

## Sunday

### Objective

Finish, polish, simplify, rehearse.

### Reggeli prioritások

* submission biztosítása
* kód stabilizálása
* demo biztosítása
* 3–5 perces pitch begyakorlása
* backup plan előkészítése

### Sunday rule

Vasárnap már ne vállaljunk nagy új technikai kockázatot.

Amit vasárnap csinálunk:

* stabilizálás
* egyszerűsítés
* kommunikáció
* rehearsing

---

## Scope Management Rules

Hackathonokon a scope a legnagyobb csapda.

### Mindig legyen 3 szint

#### Level 1 — Must Have

Ami nélkül nincs submission:

* működő pipeline
* működő baseline
* legalább egy mérőszám
* demo vagy output

#### Level 2 — Should Have

Ami erősíti a projektet:

* jobb feature engineering
* jobb modell
* szebb demo
* explainability

#### Level 3 — Nice to Have

Ami csak akkor jöhet, ha minden más kész:

* extra UI polish
* több modell összehasonlítás
* deployment finomítás
* wow feature

Ha időnyomás van, mindig a Must Have-et védjük.

---

## Decision-Making Principles

Amikor választani kell két technikai út között, ezt a kérdéssort használjuk:

1. működni fog 3 órán belül?
2. be tudjuk mutatni?
3. javítja az eredményt vagy csak bonyolít?
4. ha elromlik, van fallback?
5. a zsűri számára érthető lesz az értéke?

Ha valamire több “nem” a válasz, mint “igen”, akkor valószínűleg nem kell most megcsinálni.

---

## Demo Strategy

A demo nem mellékes. A demo az egyik legerősebb része a projektnek.

### A jó demo:

* gyors
* stabil
* könnyen érthető
* látványosan megmutatja az értéket

### Demo format ötletek

* input → prediction
* dashboard with detected risks
* before/after comparison
* ranked list with explanation
* anomaly map / confidence score

### Demo rule

Olyan demót csináljunk, amit stressz alatt is biztosan le tudunk futtatni.

---

## Pitch Strategy

A pitch legyen egyszerű és üzletileg is érthető.

## Javasolt szerkezet

### Slide 1 — Problem

Milyen problémát oldunk meg?

### Slide 2 — Why it matters

Miért fontos üzletileg vagy operációsan?

### Slide 3 — Data / Input

Milyen adatból dolgoztunk?

### Slide 4 — Approach

Mi volt a technikai megközelítés?

### Slide 5 — Result

Milyen mérhető eredményt értünk el?

### Slide 6 — Demo

Mit tud a rendszer?

### Slide 7 — Impact

Mit jelent ez a való világban?

### Slide 8 — Next steps

Hogyan lehetne továbbvinni?

---

## What Judges Usually Notice

A zsűri jellemzően ezeket figyeli:

* tényleg értettétek-e a problémát,
* volt-e technikai mélység,
* van-e kézzelfogható eredmény,
* mennyire tiszta a megoldás,
* mekkora a valós impact,
* mennyire hihető a demo,
* mennyire összeszedett a csapat.

Ezért nem elég csak sok technikai buzzwordöt használni.

---

## Git Workflow

### Branching javaslat

* `main` → stabil állapot
* `dev` → integráció
* feature branchek → egyedi feladatok

Példák:

* `feature/data-pipeline`
* `feature/baseline-model`
* `feature/demo-ui`
* `feature/pitch-assets`

### Commit szabály

Egyszerű, rövid, világos commitok:

* `add baseline training pipeline`
* `implement anomaly scoring`
* `prepare pitch draft`
* `fix preprocessing bug`

### Rule

Hackathon alatt a commit célja nem a szépség, hanem a biztonság és az átláthatóság.

---

## Suggested Repository Structure

```text
zero-one-hack-prep/
│
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── exploration.ipynb
│   └── experiments.ipynb
├── data/
│   ├── raw/
│   └── processed/
├── src/
│   ├── data/
│   │   ├── load.py
│   │   └── preprocess.py
│   ├── models/
│   │   ├── train.py
│   │   ├── predict.py
│   │   └── evaluate.py
│   ├── demo/
│   │   └── app.py
│   └── utils/
│       └── helpers.py
├── outputs/
│   ├── figures/
│   ├── models/
│   └── reports/
└── pitch/
    ├── outline.md
    └── assets/
```

Ez csak kiindulópont. A lényeg, hogy gyorsan eligazodjon benne mindenki.

---

## Communication Rules

### 1. Rövid státuszok

Ne hosszú magyarázatok legyenek, hanem világos update-ek:

* mit csinálsz most,
* mi kész,
* mi blokkol,
* mi kell segítségként.

### 2. Egyértelmű ownership

Minden tasknak legyen gazdája.

### 3. Blocker escalation

Ha valaki 30–45 percig elakad, jelezze.

### 4. Shared truth

A fontos döntéseket írjuk le röviden a repóban vagy jegyzetben.

---

## Risk Management

### Kockázat 1 — Nem értjük gyorsan a case-et

Megoldás:

* első 30–45 percben csak értelmezés
* írjuk le a problem statementet

### Kockázat 2 — Túl nagy scope

Megoldás:

* must / should / nice felosztás

### Kockázat 3 — Modell nem működik jól

Megoldás:

* baseline mindig legyen
* fallback egyszerűbb modellel

### Kockázat 4 — Demo eltörik

Megoldás:

* legyen backup notebook vagy screenshot flow

### Kockázat 5 — Szétcsúszik a csapat

Megoldás:

* fix checkpointok
* rövid szinkronok

---

## What To Bring

Technikai:

* laptop
* töltő
* hosszabbító, ha van
* egér, ha kell
* fejhallgató
* GitHub hozzáférés
* előre belőtt environment

Személyes:

* víz
* kényelmes ruha
* pulcsi
* basic hygiene cuccok
* ha ott alszotok: váltóruha

Mentális:

* ne akarj tökéleteset
* legyél gyors döntésekre kész
* fogadd el, hogy a hackathon kontrollált káosz

---

## Personal Preparation Checklist

### 1–2 héttel előtte

* csapat véglegesítve
* repo kész
* stack fix
* minimum egy mini-projekt kész
* pitch template kész

### 3–5 nappal előtte

* environment check
* package install test
* notebookok működnek
* mindenki hozzáfér a repohoz
* workflow egyeztetve

### Előző nap

* laptop feltöltve
* belépések ellenőrizve
* alap fájlok előkészítve
* mentálisan kipihenni, amennyire lehet

---

## Success Definition

Siker nem csak az, ha nyerünk.

Siker az is, ha:

* profi módon dolgozunk együtt,
* erős technikai projektet rakunk össze,
* építünk valami demonstrálhatót,
* tanulunk a tempóról és a döntéshozásról,
* kapcsolatokat építünk,
* és utána ezt referenciaként is tudjuk használni.

A valódi cél:
**egy olyan projektet építeni, ami hackathonon is megállja a helyét, de utána is érdemes róla beszélni.**

---

## Final Team Motto

> Build fast. Cut scope. Keep it real. Demo what works.

---

## Next Steps

Közvetlenül a repo létrehozása után:

1. hozzuk létre a mappastruktúrát
2. osszuk ki a szerepeket
3. készítsünk egy banking mini-projektet
4. készítsünk egy industry mini-projektet
5. tartsunk egy próba-hackathont
6. finomítsuk a starter poolt

---

## Optional Future Additions

Később ebbe a repóba bekerülhet:

* pitch sablon
* submission checklist
* judge Q&A prep
* quick experiment template
* reusable notebook template
* feature engineering cheat sheet
* anomaly detection cheat sheet
* time series quickstart
* classification quickstart
* demo day checklist

---

## Owner

Prepared for Zero One Hack Vienna 2026.
