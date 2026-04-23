# Scope & Decisions — Mit vállalunk, mit nem

Hackathonokon a **scope** a legnagyobb csapda. Aki túl sokat vállal, nem lesz kész. Aki túl keveset, nem lesz meggyőző. A jó scope a kettő között áll, és dinamikusan változik a hétvégén.

---

## Scope Management Rules

### Mindig legyen 3 szint

#### Level 1 — Must Have

**Ami nélkül nincs submission.** Ha ezek nincsenek meg, vasárnap nincs mit mutatni.

- működő pipeline (adatbetöltés → output)
- működő baseline modell (akármilyen egyszerű)
- legalább egy mérőszám
- demo vagy valamilyen látható output
- submission fájlok feltöltve

#### Level 2 — Should Have

**Ami erősíti a projektet.** Ezekkel a projekt már versenyképes.

- jobb feature engineering
- jobb modell (több próbálva, a legjobb kiválasztva)
- szebb demo (Streamlit app, nem csak notebook)
- explainability (feature importance, SHAP)
- üzleti kontextus a pitchben

#### Level 3 — Nice to Have

**Ami csak akkor jöhet, ha minden más kész.** Ezek a "wow faktor" elemek.

- extra UI polish (animations, szép stílus)
- több modell összehasonlítás táblázatban
- deployment finomítás (Docker, cloud)
- wow feature (LLM-alapú magyarázat, multimodal input)
- advanced explainability

### Szabály

**Ha időnyomás van, mindig a Must Have-et védjük.** A Level 2 és 3 opcionális.

---

## Scope szegmentálás a reveal után

A case reveal után (péntek este) 30 percen belül le kell írni:

```markdown
# Scope

## Must Have (Level 1)
- [ ] X
- [ ] Y
- [ ] Z

## Should Have (Level 2)
- [ ] A
- [ ] B

## Nice to Have (Level 3)
- [ ] C

## NOT doing
- D (túl komplex)
- E (nem releváns)
- F (nincs rá idő)
```

A "NOT doing" lista **kritikusan fontos**. Ha nincs leírva, hogy mit nem csinálunk, valaki úgyis elkezdi csinálni.

---

## Decision-Making Principles

Amikor választani kell két technikai út között, ezt a kérdéssort használd:

1. **Működni fog 3 órán belül?**
2. **Be tudjuk mutatni?**
3. **Javítja az eredményt vagy csak bonyolít?**
4. **Ha elromlik, van fallback?**
5. **A zsűri számára érthető lesz az értéke?**

**Szabály:** Ha valamire több "nem" a válasz, mint "igen", akkor valószínűleg nem kell most megcsinálni.

---

## Fast decision patterns

### "XGBoost vagy neural net?"

→ XGBoost. Mindig XGBoost. Tabular adaton 99%-ban XGBoost. Kivétel: kép, hang, hosszú szöveg.

### "Streamlit vagy React?"

→ Streamlit. Hacsak nincs React-pro a csapatban ÉS van 4+ óra rá, akkor Streamlit.

### "Saját model vagy pretrained?"

→ Pretrained, amíg lehet. Saját model csak ha a feladat kifejezetten azt kéri, vagy ha a pretrained nem elég jó (és van idő fine-tune-olni).

### "Több modell kipróbálva vagy egy modell optimalizálva?"

→ Hackathonon: 3 különböző modell gyors baseline-nel, utána a legjobbat iterálni. Ne egy modellt próbálj tökéletesíteni.

### "Docker-ezzük vagy simán fusson lokálisan?"

→ Simán fusson lokálisan. Docker csak akkor, ha a csapatban valaki nagyon otthon van benne, ÉS a submission explicit kéri.

### "Írjunk tesztet?"

→ Hackathonon nem. A demo a teszt. Vasárnap 3x lefuttatni a flow-t ugyanazzal az eredménnyel = a tesztelés.

---

## Mikor vágjunk scope-ot (időnyomás jelei)

### Szombat déli checkpoint

Ha 12:00-kor még nincs meg a data pipeline:
→ **AZONNAL** Level 1-re fókuszálni, Level 2-3-at kukázni.

### Szombat esti checkpoint

Ha 19:00-kor még nincs baseline eredmény:
→ a baseline legyen még **egyszerűbb**. Dummy predictor is megteszi, csak legyen mit mérni.

### Vasárnap déli checkpoint

Ha 12:00-kor még demo nincs, vagy instabilan fut:
→ **backup notebook** készítése, screenshot flow, recorded video. Semmi új.

### Amikor egy feature reszort

Ha egy feature (Level 2 vagy 3) 2 órán túl nem működik:
→ **eldobni**. Nem húzzuk tovább, másra megy az idő.

---

## Lessons on what NOT to scope in

Tapasztalatok alapján ezeket szokták alábecsülni:

- **frontend polish** — mindig 2x annyi idő, mint gondolod
- **deployment** — hackathonon soha nem éri meg a polírozást
- **több modell ensembling** — csak ha alap modellek már jók
- **hyperparameter tuning** — 1-2%-ot ad, ritkán éri meg
- **szép adatvizualizáció mindenhol** — 1 jó plot elég a pitchben, a többi zaj
- **tesztek írása** — a kódhoz nem, a demo flowhoz igen (kézzel)

És amiket alábecsülnek pozitív irányba:

- **feature engineering** — gyakran többet hoz, mint modellváltás
- **threshold tuning** — classification metrikákon 5-10%-ot is hozhat
- **jobb evaluation** — ha nem tudod, mit mérsz, nem tudsz javítani
- **pitch idő** — 90 perc a pitch deckre tényleg nem sok

---

## "Should we?" — egy utolsó szabály

Mielőtt bármilyen új feature-be belekezdesz, kérdezd meg:

> "Ha ez nincs meg a submissionbe, akkor is meg lesz a Level 1?"

Ha nem, **álljon meg minden, Level 1-et kell befejezni.**

Ha igen, mehet — de csak ha van idő.

---

Kapcsolódó doksik:

- [Weekend Plan](06-weekend-plan.md) — a hétvége checkpointjai
- [Communication & Risk](10-communication-and-risk.md) — hogyan kommunikáljuk a scope változást
