# Checklists — Amit vinni kell és amit ellenőrizni

---

## What To Bring

### Technikai

* [ ] laptop
* [ ] töltő (kritikus!)
* [ ] hosszabbító, ha van (a helyszínen versengés lesz a konnektorokért)
* [ ] egér, ha kell
* [ ] fejhallgató (zajkioltó ideális)
* [ ] GitHub hozzáférés + 2FA backup kódok
* [ ] előre belőtt environment (teszt: sanity check script lefut)
* [ ] HDMI / USB-C adapter a prezentációra
* [ ] USB stick backup-nak (pitch deck, demo video)
* [ ] mobil hotspot képesség (SIM-en data)

### Személyes

* [ ] víz (nagy kulacs)
* [ ] kényelmes ruha
* [ ] pulcsi / réteges öltözet (a helyszín hideg lehet)
* [ ] basic hygiene cuccok
* [ ] ha ott alszotok: váltóruha, fogkefe
* [ ] szemüveg / kontaktlencse, ha kell
* [ ] gyógyszerek, ha szeded

### Snack / Energia (a szervezés kiegészítése)

* [ ] dió / mandula / trail mix
* [ ] banán / alma
* [ ] protein szelet
* [ ] tea / kávé (ha függő vagy, ne most akarj leállni)
* [ ] **nem csak cukor** — crash hullámvasút rossz időzítés lenne

### Mentális

* [ ] ne akarj tökéleteset
* [ ] legyél gyors döntésekre kész
* [ ] fogadd el, hogy a hackathon kontrollált káosz

---

## Personal Preparation Checklist

### 1–2 héttel előtte

* [ ] csapat véglegesítve (mindenki tudja, jön-e)
* [ ] repo kész
* [ ] stack fix, requirements.txt commitolva
* [ ] minimum egy mini-projekt kész
* [ ] pitch template kész
* [ ] szerepek kiosztva (lásd [04-team-roles.md](04-team-roles.md))

### 3–5 nappal előtte

* [ ] environment check **mindenki gépén**
* [ ] package install test — futnak a kulcs importok?
* [ ] notebookok lefutnak?
* [ ] mindenki hozzáfér a repohoz?
* [ ] workflow egyeztetve (branch, PR, kommunikáció)
* [ ] mini-hackathon retro tanulságai beépítve
* [ ] pitch deck template előkészítve

### Előző nap

* [ ] laptop feltöltve
* [ ] belépések ellenőrizve (GitHub, Kaggle, Hugging Face ha kell)
* [ ] alap fájlok / notebookok előkészítve
* [ ] utazás / érkezés megszervezve (időben ott legyünk)
* [ ] mentálisan **kipihenni, amennyire lehet**
* [ ] normál vacsora, ne részegedj le

### Eseménynap reggel

* [ ] reggeli
* [ ] töltő, laptop, adapter a táskában
* [ ] GitHub login működik?
* [ ] Discord / Slack értesítések beállítva
* [ ] VPN / wifi beállítások tesztelve

---

## Environment Sanity Check

Futtasd ezt a Python scriptet **3–5 nappal** az esemény előtt:

```python
import sys
print(f"Python: {sys.version}")

# Core
import numpy, pandas, sklearn
print(f"numpy: {numpy.__version__}")
print(f"pandas: {pandas.__version__}")
print(f"sklearn: {sklearn.__version__}")

# Modeling
import xgboost, lightgbm
print(f"xgboost: {xgboost.__version__}")
print(f"lightgbm: {lightgbm.__version__}")

# Viz
import matplotlib, seaborn, plotly
print(f"matplotlib: {matplotlib.__version__}")
print(f"seaborn: {seaborn.__version__}")
print(f"plotly: {plotly.__version__}")

# Demo / API
import streamlit, fastapi
print(f"streamlit: {streamlit.__version__}")
print(f"fastapi: {fastapi.__version__}")

# Teszt: tudsz-e Streamlit app-ot indítani?
# parancssorból: streamlit hello

print("\nAll imports OK. You're ready.")
```

Ha bármi failel → **most** fixáld, ne péntek este.

---

## Friday Night Checklist (case reveal után)

### Első 45 perc

* [ ] problémát **egy mondatban** leírtuk
* [ ] bemenet / kimenet formátum tiszta
* [ ] mérőszám(ok) kiválasztva
* [ ] use case üzleti értéke érthető
* [ ] Level 1 / 2 / 3 scope felvázolva

### Első 2 óra

* [ ] adat letöltve és ellenőrizve
* [ ] feladatok felosztva (mindenki tudja, mit csinál)
* [ ] branch stratégia működik
* [ ] első exploration notebook fut

### Péntek éjfél előtt

* [ ] 1 mondatos probléma-definíció commitolva a repo-ba
* [ ] induló adatpipeline fut
* [ ] baseline terv megvan
* [ ] szombat reggeli sync időpont kitűzve

---

## Saturday Checkpoints

### Szombat dél

* [ ] adat pipeline stabil (bárki le tudja futtatni)
* [ ] első baseline modell fut + mérve van
* [ ] legalább egy metrika kiszámolva és értelmezve
* [ ] scope revízió: reális-e még a terv?

### Szombat este (21:00 körül)

* [ ] működő baseline (legalább Level 1 kész!)
* [ ] mérhető eredmény megvan
* [ ] demo vázlat készül
* [ ] pitch outline megvan
* [ ] mindenki tudja a vasárnapi szerepét

### Szombat éjjel

* [ ] git push
* [ ] pitch deck első verzió mentve
* [ ] alvás (legalább 4–5 óra)

---

## Sunday / Submission Checklist

### Vasárnap reggel

* [ ] submission formátum ellenőrizve (mit kérnek?)
* [ ] demo **frissen indított gépen** lefut
* [ ] pitch deck komplett
* [ ] mindenki kipihent — ha valaki totál kint van, pótold a szerepét

### Submission előtt 1 órával

* [ ] minden kód pusholva
* [ ] README frissítve (setup instructions, hogyan fut a demo)
* [ ] pitch deck PDF-be mentve (backup)
* [ ] demo video rögzítve (backup)
* [ ] submission form kitöltve, de még nem küldve (double-check)

### Submission után

* [ ] confirmation email / screenshot lementve
* [ ] pitch rehearsal min. 2×
* [ ] Q&A szerepkörök tisztázva (ki válaszol mire)
* [ ] laptop töltve, adapter kész

### Prezentáció előtt 15 perccel

* [ ] toilet break
* [ ] víz, fejhallgató le
* [ ] laptop setup a színpadon teszt
* [ ] demo happy path inputja előkészítve
* [ ] mély levegő

---

## Post-hackathon (opcionális, de értékes)

### Esemény után 1 héten belül

* [ ] retro: mi ment jól, mi ment rosszul
* [ ] learnings leírva (ebbe a repóba is!)
* [ ] kapcsolatok a többi csapattal / mentorokkal fenntartva
* [ ] portfóliós verzió készítése: README rendben, demo élesben is fut
* [ ] blog post vagy LinkedIn post (opcionális)

### Esemény után 2–4 héten belül

* [ ] ha megnyerhető a projekt / folytatható: következő lépések megtervezése
* [ ] ha nem: az itt szerzett tapasztalat beépítése a következő hackathon-felkészülésbe

---

## Quick Reference — Egy oldal

Vedd ezt printben magaddal, vagy legyen mindenki telefonján:

```
ZERO ONE HACK — POCKET GUIDE
============================

PHASES:
  FRI: understand case, scope, baseline plan
  SAT: pipeline + baseline + demo + pitch outline
  SUN: polish, rehearse, submit, pitch

RULES:
  1. Working > perfect
  2. Baseline first, always
  3. Scope: Must / Should / Nice
  4. Timebox: stuck 30min → ask
  5. Demo-driven: can you show it?

WHEN STUCK:
  - ask team (Discord)
  - try simpler approach
  - cut the feature

WHEN DOUBTFUL:
  - does it work in 3h?
  - can we demo it?
  - is there a fallback?
  - will judges understand?

FINAL MOTTO:
  Build fast. Cut scope. Keep it real.
  Demo what works.
```
