# Demo & Pitch — Bemutatás és prezentáció

A demo és a pitch **nem mellékes** — ezek a hackathon kimenő részei. Amit a zsűri ténylegesen lát, az dönt, nem a kód amit írtál.

---

## Demo Strategy

### A jó demo

- **gyors** — 60–120 másodperc alatt megmutatja a lényeget
- **stabil** — nem omlik össze, ha máshogy kattintasz
- **könnyen érthető** — nem kell előadás hozzá
- **látványosan megmutatja az értéket** — input ment be, konkrét output jött ki

### Demo format ötletek

| Forma | Mikor passzol |
|---|---|
| **Input → prediction** | Classification / regression problémáknál. Legegyszerűbb, leggyakoribb. |
| **Dashboard with detected risks** | Anomaly detection, fraud, monitoring feladatoknál. |
| **Before/after comparison** | Ha a megoldás egy meglévő folyamatot javít. |
| **Ranked list with explanation** | Ha sok elemből kell kiemelni a kritikusakat. |
| **Anomaly map / confidence score** | Time series, spatial adatok. |
| **Chat-like interface** | LLM-alapú megoldások (óvatosan — könnyen csúszik). |
| **Live feed / streaming** | Ha a problémának van real-time aspektusa. |

### Demo technikai szabályok

1. **Mentsd el a modellt fájlba.** A demo ne a training futtatásával kezdődjön. `pickle.dump(model, open('model.pkl', 'wb'))` péntek este, és kész.
2. **Legyen offline képes.** Ne függjön external API-tól, kivéve ha kritikus. Az LLM-hívásokat cache-eld.
3. **Teszteld 3x, különböző inputokkal.** Ha a second attempt crashol, az a zsűri előtt is crashol.
4. **Legyen egy happy path.** Ne legyenek útelágazások — a demo egy lineáris sztori.
5. **Screenshot backup.** Ha technikailag bedöglik, mutasd a screenshotot.

### Demo rule

> **Olyan demót csináljunk, amit stressz alatt is biztosan le tudunk futtatni.**

Ha egy feature csak a 3. próbára működik a saját laptopodon nyugodt körülmények között — az a zsűri előtt sosem fog működni.

### Demo fallback hierarchia

1. **Live Streamlit app** — legjobb
2. **Notebook, ami futva megvan** — biztos
3. **Recorded screen capture** — ha minden más fail
4. **Screenshot flow slide-okban** — végső megoldás

Legalább a 2. szintet **mindig készítsd el.**

---

## Pitch Strategy

A pitch legyen **egyszerű és üzletileg is érthető**. A zsűriben gyakran vannak nem-tech szakemberek.

### Javasolt szerkezet (8 slide, 3-5 perc)

#### Slide 1 — Problem

> Milyen problémát oldunk meg? Kinek a problémája ez?

Egy konkrét mondat. Nem "AI-t csinálunk", hanem pl. "banki csalási riasztásoknál a 70% false positive a review csapatot kimeríti".

#### Slide 2 — Why it matters

> Miért fontos üzletileg vagy operációsan? Mennyi pénz / idő / erőforrás van benne?

Számot dobj. Ha nincs konkrét számod, használj plausibilis becslést: "átlag európai bank évente X millió riasztást kezel, Y€ review költséggel".

#### Slide 3 — Data / Input

> Milyen adatból dolgoztunk? Milyen a szerkezete, mérete?

Egy screenshot az adatból vagy egy egyszerű táblázat. Ne részletezd — a zsűri 10 másodperc alatt lássa, miből dolgoztál.

#### Slide 4 — Approach

> Mi volt a technikai megközelítés?

1-2 mondat. Pl. "rolling feature engineering + XGBoost classifier + SHAP magyarázat a top predikciókhoz". Ne legyen túl technikai (neural architecture diagramot a Q&A-ba hagyd).

#### Slide 5 — Result

> Milyen mérhető eredményt értünk el? Miért jobb ez, mint a baseline?

**KONKRÉT SZÁM.** "0.92 AUC", "50% kevesebb false positive", "8 órával korábbi failure detection". Ez a slide a legfontosabb.

#### Slide 6 — Demo

> Live demo vagy recorded video.

60-90 másodperc. Mutasd meg az input → output útját. Ha megy, kattints gyorsan.

#### Slide 7 — Impact

> Mit jelent ez a való világban? Ha bevezetnék, mi változna?

Kapcsold vissza a Slide 2-re. "Ha a bank bevezeti, évente X€ megtakarítás / Y óra review idő felszabadul."

#### Slide 8 — Next steps

> Hogyan lehetne továbbvinni? Mi van még bennetek?

Ne legyél szerény, de legyél realista. "Következő lépés: integráció a meglévő case management rendszerbe, online learning a feedback alapján." Ez mutatja, hogy tovább is gondolkoztatok, nem csak hackathon-project.

---

## Pitch delivery tippek

### Időarány

- ~10% bevezető (Slide 1-2)
- ~20% adat + approach (Slide 3-4)
- ~20% eredmény (Slide 5)
- ~30% demo (Slide 6)
- ~15% impact + next steps (Slide 7-8)
- ~5% puffer

### Ki beszéljen

- **1 fő beszél** — nem váltogatjuk. Kivétel: demo közben, ha az kattintgat, aki csinálta.
- A beszélő a **Pitch Lead** — ő gyakorolt rá, ő ismeri a slide-okat.
- A többiek készen álljanak a **Q&A-ra**.

### Nyelv

- A helyszín Bécs, nemzetközi hackathon — **angolul pitcheljünk**, hacsak nem kifejezetten megengedik a németet/magyart.
- Előre **leírt forgatókönyv** segít, de tanuld meg — ne olvasd.
- Gyakorold fel 3x, legalább egyszer valaki előtt, aki nem ismeri a projektet.

---

## Q&A felkészülés

A pitch után gyakran **5-10 perc Q&A** van. Ide készülj.

### Tipikus zsűri kérdések

- "Hogy működne ez a valóságban?"
- "Mi történik, ha az adat zaja nagyobb?"
- "Hogy skálázódna 100x adatra?"
- "Miért ezt a modellt választottátok?"
- "Mi a baseline, amihez viszonyítotok?"
- "Hol van még hibája a modellnek?"
- "Mennyi idő lenne productionbe vinni?"
- "Mi a nagyobb versenytárs megoldás?"

### Válaszadási elvek

1. **Ne improvizálj többet, mint kell.** Ha nem tudsz valamire választ, mondd ki őszintén: "Ezt nem teszteltük, de a következő lépés lehetne."
2. **Legyen konkrét szám minden válaszban,** ha lehet.
3. **Ha nem értesz valamit a kérdésben, kérdezz vissza.** Jobb tisztázni, mint rossz választ adni.
4. **Ha a csapat másik tagja jobban tudja, add át a szót.**

---

## What Judges Usually Notice

A zsűri jellemzően ezeket figyeli:

- **tényleg értettétek-e a problémát** — látszik, hogy a csapat beleérezett, vagy csak ráhúztak egy modellt?
- **volt-e technikai mélység** — nem csak GPT-4 wrappert építettetek?
- **van-e kézzelfogható eredmény** — mérhető szám, működő demo?
- **mennyire tiszta a megoldás** — érthető, nem összecsapott?
- **mekkora a valós impact** — üzletileg is eladható?
- **mennyire hihető a demo** — stabilan fut, nem tűnik hack-nek?
- **mennyire összeszedett a csapat** — a Q&A-ban is profin válaszoltok?

**Nem elég csak sok technikai buzzwordöt használni.** "LLM-alapú agentic RAG rendszer" nem önmagában lenyűgöző, ha nem látszik mit csinál.

---

## Pitch deck templatek

### Stílus

- **1 fő idea per slide** — ne zsúfolj össze
- **max 15-20 szó per slide** — csak kulcsgondolatok, a beszélő részletez
- **nagy betűk** (24pt+) — a hátsó sorból is olvasható legyen
- **konzisztens színek** — max 3 szín, egy erős kiemelés
- **1 kép vagy diagram** egy slide-on — ne több

### Gyakori hibák

- text wall
- "szép" de üzenettelen slide-ok
- animated transitions (időpazarlás)
- sok ábra, amit nem magyarázol el
- végén egy "Thank you!" slide, az idő rovására

---

Kapcsolódó doksi: [Weekend Plan](06-weekend-plan.md) — hogyan jussatok el idáig.
