# Weekend Plan — Friday / Saturday / Sunday

A hackathon hétvége 3 fázisra oszlik. Mindegyiknek más a hangulata, más a célja, más a veszélyzónája.

---

## Friday Night

### Objective

**A case gyors megértése és a scope lezárása.**

### Checklist a case reveal után (első 90 perc)

- [ ] pontosan mi a probléma?
- [ ] mi a bemenet?
- [ ] mi a kimenet?
- [ ] mi lesz a minimum működő megoldás (Level 1)?
- [ ] mi lesz a demo?
- [ ] mi lesz a mérőszám?
- [ ] milyen adatunk van? mennyi? milyen formátumban?
- [ ] van-e kimondott baseline a szervezők részéről?
- [ ] mi az, amiben BIZTOSAN nem akarunk részt venni?

### Output péntek éjfélig

- 1 mondatos probléma-definíció (írd le a repoba: `docs/problem.md`)
- 1 mondatos megoldási irány
- felosztott feladatok (ki mit csinál szombat reggelig)
- **működő adatbetöltés** (a starter modulokkal ez 20 perc kell legyen)
- baseline terv (melyik 2-3 modellt próbáljuk először)

### Nagyon fontos

**Péntek este még ne akarjunk mindent megépíteni. Először világos döntéseket kell hozni.**

Aki péntek este modellt kezd tanítani, az már elvesztette a scope harcot. Péntek este **értünk meg és döntünk**.

### Péntek esti veszélyzónák

- túl sokat vitatkozni a megközelítésen
- már este modellre ugrani, adat-exploration helyett
- "majd hajnalig dolgozunk" — rossz ötlet, szombatra kell energia
- **nem dokumentálni** a problem statementet (másnap már mást fogtok rá emlékezni)

### Péntek éjszaka

Pihenjetek! Szombat hosszú nap lesz.

---

## Saturday

### Objective

**Megépíteni a működő rendszert. Szombat estére legyen egy end-to-end demo, még ha csúnya is.**

### Prioritási sorrend (ne térj el)

1. adat pipeline (lehetőleg reggel 11-ig)
2. baseline modell (lehetőleg dél körül)
3. mérés (ne spórold ki!)
4. inference vagy demo flow (délutáni nagy task)
5. jobb modell vagy extra feature (csak ha fent kész)
6. pitch anyag vázlata (este)

### Saturday checkpoints

- **10:00** — mindenki beérkezett, tervegyeztetés 15 perc
- **12:00** — data pipeline fut-e? ha nem, veszélyzóna
- **15:00** — baseline eredménye megvan?
- **17:00** — demo flow működik-e end-to-end (még ha gagyi is)?
- **19:00** — pitch outline megvan?
- **21:00** — napzáró: mit kell holnap?
- **22:30** — tessék abbahagyni, aludni

### Saturday danger zones

- **túl sokat vitatkozni az irányon** — szombat a csinálás napja, nem a vita
- **túl sok modellt kipróbálni eredmény nélkül** — 3 modell max, utána a legjobbat iteráld
- **túl korán UI-ra menni** — baseline és mérés legyen meg először
- **túl későn elkezdeni a pitch-et** — 19:00-ig legyen outline
- **nem commitolni** — este 10-kor ne derüljön ki, hogy 6 óra munka elveszett

### Saturday end goal

Szombat estére legyen:

- működő adat pipeline
- működő baseline modellel
- mérhető eredmény (akárcsak 1 szám)
- demo vázlat (akár notebook, akár Streamlit)
- pitch outline

**Ha mindez megvan, a hackathont már nem veszíthetitek el — csak javíthattok rajta.**

---

## Sunday

### Objective

**Finish, polish, simplify, rehearse.**

A kulcs szó: **stabilizálás**. Semmi új nagy kockázat.

### Reggeli prioritások

- [ ] submission biztosítása (értsd: tesztben feltöltési flow)
- [ ] kód stabilizálása (nem új feature, hanem bugfix)
- [ ] demo biztosítása (próbáld ki 3x, különböző inputokkal)
- [ ] 3–5 perces pitch begyakorlása
- [ ] backup plan előkészítése (ha eltörik a demo, mit mutatsz?)

### Sunday timeline (példa, ha 16:00-kor submission)

| Idő | Teendő |
|---|---|
| 09:00 | Reggeli sync, mi a terv |
| 09:30–11:30 | Utolsó javítások, stabilizálás |
| 11:30–12:30 | Demo end-to-end próba + backup screenshot készítése |
| 12:30–13:30 | Pitch próba 1x, csapat feedback |
| 13:30–14:00 | Ebéd |
| 14:00–14:45 | Pitch próba 2x |
| 14:45–15:30 | Submission összerakása + feltöltés |
| 15:30–16:00 | **Puffer** (ide bármi belefér: technikai pánik, wifi down, stb.) |
| 16:00 | Submission lock |
| Utána | Pitch prezentáció |

**Fontos:** a submission deadline előtt minimum 30 perc puffer legyen. Valami mindig elromlik.

### Sunday rule

**Vasárnap már ne vállaljunk nagy új technikai kockázatot.**

Amit vasárnap csinálunk:

- stabilizálás
- egyszerűsítés
- kommunikáció
- rehearsing

Amit vasárnap **NEM** csinálunk:

- új modell architektúra
- új feature engineering
- új library behúzása
- Docker / deployment tökéletesítése
- új UI komponens

### Sunday anti-patterns

- "még egy utolsó improvement" — NEM, stabilizálás van
- "majd a pitch közben improvizálok" — gyakorold be rendesen
- "a demo valószínűleg működni fog" — próbáld ki 3x, különben nem fog

---

## End-of-weekend retrospective (opcionális, de ajánlott)

A hackathon után, hazafelé vagy másnap, 30 perc retrospektíva a csapattal:

1. Mit csinálnánk újra pontosan így?
2. Mit csinálnánk másképp?
3. Mi volt a legjobb döntés?
4. Mi volt a legrosszabb döntés?
5. Mit tanultunk egymásról?

Írd le valahol. A legjobb tanulságokat pedig add hozzá ehhez a repóhoz, hogy a következő hackathonra jobbak legyünk.

---

Kapcsolódó doksik:

- [Scope & Decisions](07-scope-and-decisions.md) — hogyan hozzatok jó döntéseket időnyomás alatt
- [Demo & Pitch](08-demo-and-pitch.md) — hogyan készüljön a demo és pitch
- [Checklists](11-checklists.md) — submission checklist
