# Team Roles — Szerepkörök és felelősségek

Nem kell, hogy mindenki csak egy dolgot csináljon, de **legyen fő felelősségi kör**. Ez csökkenti a lábra-lépést és az "én azt hittem te csinálod" problémát.

Ha 2-3 fős a csapat, a szerepek összevonhatók. 4+ fő esetén érdemes külön tartani.

---

## 1. ML / Modeling Lead

### Felelősség

- modellek kiválasztása és kipróbálása
- baseline építése és iterálása
- train és eval futtatása
- feature ötletek és tesztelésük
- hyperparam tuning (csak ha marad idő!)

### Főként mivel tölti az időt

- notebook / `src/models/` fájlok
- sklearn, xgboost, lightgbm
- metrikák olvasása, összehasonlítása

### Typikus hiba, amit kerülni kell

- túl sok modell kipróbálása eredmény nélkül
- baseline előtt fancy modelbe ugrás
- "még 2 óra és 0.5%-ot javítok rajta" csapda

---

## 2. Data / Pipeline Lead

### Felelősség

- adat tisztítás (missing, outlier, duplicate)
- input pipeline (load + preprocess)
- feature engineering közösen az ML Lead-del
- fájlstruktúra és reproducibility (seed, split rögzítése)
- adat dokumentáció (mi micsoda)

### Főként mivel tölti az időt

- `src/data/` fájlok
- pandas, polars
- Jupyter exploration (`notebooks/exploration.ipynb`)

### Typikus hiba, amit kerülni kell

- data leakage (idő-független split idősoron)
- túl sok idő adattisztításon, nem marad modellre
- preprocessing túlbonyolítása

### Critical skill

**Gyorsan tudjon választ adni arra, hogy "milyen az adat".** Ha a reveal után 30 percen belül nem mondja el a csapatnak mennyi sor, milyen oszlopok, mennyi missing, milyen a target eloszlás — akkor a csapat vakon fejleszt.

---

## 3. Product / Demo Lead

### Felelősség

- demo flow megtervezése és lekódolása
- UX logika (mit lát a zsűri?)
- use case értelmezése üzleti oldalról
- final presentation visual oldala
- **biztosítja, hogy a demo vasárnapra működjön**

### Főként mivel tölti az időt

- `src/demo/app.py` (Streamlit)
- pitch/assets screenshotok
- beszélgetés a többiekkel, hogy mit akarunk megmutatni

### Typikus hiba, amit kerülni kell

- túl korán UI-ra menni (még baseline sincs)
- túl bonyolult demo (sok kattintás, sok input)
- demo dependency a folyamatban változó modellre (→ mentsen egy pickle-t!)

### Critical skill

**Tudja kimondani, hogy "ez nem fér be a demóba" — még akkor is, ha valaki 4 órát dolgozott rajta.**

---

## 4. Pitch / Integration Lead

### Felelősség

- storytelling (probléma → megoldás → impact)
- slide deck összerakása
- final narrative megírása
- feature-k összefűzése és átadása a demóba
- deadline management (submission időben!)
- submission folyamat ismerete (mit kell feltölteni, hova, mikorra)

### Főként mivel tölti az időt

- `pitch/` mappa
- slides (Google Slides / Canva / Keynote)
- beszélgetés a csapattal a narratíváról

### Typikus hiba, amit kerülni kell

- pitchet az utolsó 2 órára hagyni
- csak technikai dolgokról beszélni, üzleti impact nélkül
- zsűri kérdéseket nem gyakorolni előre

### Critical skill

**Tud 90 másodpercben elmondani egy sztorit, ami értelmes annak, aki most találkozik a projekttel először.** Ezt gyakoroljátok, mielőtt a zsűri előtt mondja.

---

## Szerepek összevonása kisebb csapatban

### 2 fős csapat

- **Person A:** ML + Data (minden, ami kód)
- **Person B:** Demo + Pitch (minden, ami ember felé néz)

### 3 fős csapat

- **Person A:** ML Lead
- **Person B:** Data + Demo
- **Person C:** Pitch + támogatja a másik kettőt

### 4 fős csapat

Teljes felosztás, minden szerep külön személy.

---

## Mindenkitől elvárt

Függetlenül attól, ki melyik szerepben van:

- **commit early, commit often** — ne tartson mindenki 4 óra munkát uncommitted helyen
- **writing down decisions** — ha nagy döntés születik, írja le valaki 2 mondatban a repoba vagy a csatornába
- **respect timeboxing** — ha valaki azt mondja "45 perc múlva checkpoint", az kőbe van vésve
- **ask for help early** — 30 perc elakadás után szólj

---

## Konfliktus-kezelés

### "Nem értünk egyet, hogy X modellt vagy Y modellt használjuk"

**Szabály:** aki ML Lead, döntsön, 5 percen belül. Nem demokrácia, idő van.

### "A demo lassabb mint gondoltuk, kevesebb feature fér bele"

**Szabály:** Product / Demo Lead dönt mit vág, konzultálva a többiekkel. Cél: amit mutatunk, az stabilan működjön.

### "A pitch és a tényleges projekt kicsit eltér"

**Szabály:** a pitch a projektet tükrözze. Soha ne ígérjünk a zsűrinek olyat, amit a demóban nem mutatunk meg.

---

Kapcsolódó doksi: [Communication & Risk](10-communication-and-risk.md) — a blokkoló eszkalálás és a shared truth szabályok.
