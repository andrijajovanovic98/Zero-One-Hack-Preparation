# Communication & Risk Management

A hackathon technikai projekt, de csapatjáték. A legjobban szétcsúsznak a csapatok pont akkor, amikor egyébként a technika már működne.

---

## Communication Rules

### 1. Rövid státuszok

Ne hosszú magyarázatok legyenek, hanem világos update-ek:

* **Mit csinálsz most?** (1 mondat)
* **Mi kész?** (konkrét)
* **Mi blokkol?** (konkrét — nem "nehéz")
* **Mi kell segítségként?**

### Jó példa

> "Dolgozom a baseline-on, XGBoost fitel most. CSV pipeline kész. Blokkol a dataset imbalance — valakinek van ötlete SMOTE-on kívül? Segítség: 5 perc, ha valaki tudja."

### Rossz példa

> "Hát csinálom a dolgokat, nézegetem az adatot, valami furcsa lehet benne, majd szólok."

---

### 2. Egyértelmű ownership

Minden tasknak legyen **egy** gazdája. Ha "mi csináljuk", az azt jelenti, hogy senki sem.

#### Task board minimum

Egy egyszerű Kanban (GitHub Projects / Linear / Trello / akár Notion) 4 oszloppal:

* **Backlog** — amit még nem kezdtél el
* **In Progress** — épp csinálod (max 1–2 task / fő)
* **Review / Test** — kész, de ellenőrizni kell
* **Done**

#### Task szabály

* Task címe konkrét: ~~"modell"~~ → "XGBoost baseline with F1 eval"
* Minden taskhoz név tartozik
* Ha valami 2 óránál hosszabb, bontsd szét

---

### 3. Blocker escalation

Ha valaki **30–45 percig** elakad, jelezze. Nem 2 óra múlva. Nem "majd szólok, ha tényleg baj van".

#### Escalation protocol

1. **0–30 perc**: próbálkozol egyedül
2. **30 perc**: írj a csoport chat-be: "elakadtam X-en, bárki segít?"
3. **45 perc**: ha még mindig nincs megoldás, rövid pair session (5–10 perc)
4. **60 perc**: döntés — vagy kivágjuk a feature-t, vagy más veszi át, vagy alternatív megközelítés

### Szabály

**Senki sem veszít pontot azzal, hogy segítséget kér.** A projekt veszít pontot a néma elakadással.

---

### 4. Shared truth

A fontos döntéseket írjuk le röviden — a repóban, pinned chat üzenetben, vagy közös doksiban. Kimondva elfelejtjük.

#### Mit írjunk le?

* **scope döntések** ("úgy döntöttünk, csak bináris classification")
* **technikai döntések** ("XGBoost-ot használunk, LightGBM helyett, mert X")
* **felelősségek** ("demo Kata, pitch Gergő, data Anna")
* **timeline-ok** ("szombat 22:00-ig baseline kész")
* **ismert limitációk** ("test set-re nincs időnk nagy CV-t futtatni")

---

### 5. Channel hygiene

Válassz **egy** elsődleges csatornát és ragaszkodj hozzá.

| Csatorna  | Használat                                     |
|-----------|-----------------------------------------------|
| Discord/Slack | gyors update, blocker, döntés               |
| GitHub    | kód, PR review, issue                         |
| Docs (közös)| scope, roadmap, pitch outline               |
| Szóban / face-to-face | kritikus döntés, vita              |

Ne legyen 4 helyen ugyanaz a beszélgetés. Eltűnnek a döntések.

---

## Risk Management

A hackathon tele van kockázattal. Ezek a leggyakoribbak, és a preventív megoldásuk.

### Kockázat 1 — Nem értjük gyorsan a case-et

**Jelei:** 1 óra telt el és még mindig arról beszélünk, "mit is kell csinálni".

**Megoldás:**

* első 30–45 percben **csak** értelmezés, nem kód
* írjuk le a problem statementet 1 mondatban
* tegyünk fel mentor / szervező kérdést, ha szabad
* ha 1 órával később sem világos → válasszunk egy értelmezést és mozduljunk el; pontosíthatjuk később

---

### Kockázat 2 — Túl nagy scope

**Jelei:** "meg kell csinálni A, B, C, D, E-t is". Szombat estére még a C sem működik.

**Megoldás:**

* **must / should / nice** felosztás, lásd [07-scope-and-decisions.md](07-scope-and-decisions.md)
* minden 4 órában scope review: "ez még reális?"
* ha nem → vágunk

---

### Kockázat 3 — Modell nem működik jól

**Jelei:** baseline F1 = 0.4, nem tudjuk, miért.

**Megoldás:**

* **baseline** mindig legyen, még akkor is, ha gyenge — minimum a probléma ki van merítve
* fallback egyszerűbb modellel (pl. logistic regression — érthető, magyarázható)
* fókusz váltás: ha a modell nem jó, a **narratíva** és a megközelítés lehet érdekes
* néha az "ez miért nehéz probléma" pitch erősebb, mint a "86%-ot értünk el"

---

### Kockázat 4 — Demo eltörik

**Jelei:** 10 perccel a prezi előtt a Streamlit nem indul.

**Megoldás:**

* legyen **backup notebook** — kézzel végigléptethető
* legyen **backup screenshot flow** — PDF-ben előre lementve
* legyen **felvett videó** a demo-ról — ha minden más megy, ezt mutasd
* **frissen indított gépen** teszteld a demót vasárnap reggel

---

### Kockázat 5 — Szétcsúszik a csapat

**Jelei:** idegeskedés, hangos vita, valaki duzzogva félrevonul.

**Megoldás:**

* **fix checkpointok** — 3 sync a hétvégén, nem több, nem kevesebb
* **rövid szinkronok** — max 15 perc, nem "megbeszéljük a stratégiát" típusú
* **szünet** — ha feszült a hangulat, 15 perc egyedül, aztán vissza
* **ne személyeskedj** — "ez a kód rossz" nem személyes, "te rosszul kódolsz" az
* ha tartós a feszültség: a Pitch / Integration Lead hívja össze a csapatot 10 percre és beszéljétek meg röviden

---

### Kockázat 6 — Elfogy az idő a pitch-re

**Jelei:** szombat 23:00 van és még nincs slide deck.

**Megoldás:**

* pitch outline **szombat délre** legyen
* pitch first draft **szombat estére**
* vasárnap csak polish és rehearsal
* ha csúsztunk: Pitch Lead **leállíthatja** a technikai munkát, hogy ki legyen rendben a pitch

---

### Kockázat 7 — Egy csapattag kiesik (beteg, nem jön el)

**Jelei:** reggel pár óra előtt: "nem tudok menni".

**Megoldás:**

* ismerd a csapattag kódját / felelősségét — legalább nagy vonalakban
* a repóban minden legyen — ne "csak az ő gépén"
* ha kiesik: scope-ot vágunk, a szerepét felosztjuk
* ne próbáld "megcsinálni helyette mindent" — scope-ot vágunk

---

### Kockázat 8 — Gépi kiesés (laptop, net, áram)

**Megoldás:**

* kód a git-en van — ne csak lokálisan
* modell artifactok git-en vagy cloud-on (pl. Drive, HuggingFace)
* a laptop töltője mindig legyen nálad
* ha van időd, egy backup gépre is klónozd a repót
* mobil hotspot legyen backup, ha a wifi megdől

---

## Energy management

Technikai részlet, de gyakran ez dönt.

### Aludj

Komolyan. Hackathonra készülésből erről szokott a legkevesebb cikk szólni.

* péntek előtti éjjel: 7–8 óra
* péntek éjjel: 5–6 óra (ha lehet)
* szombat éjjel: 4–5 óra minimum
* vasárnapi pitch **fáradt emberrel el fog bukni**

### Egyél

* **ne** csak energiaital és csoki
* legalább egy igazi étel naponta
* snack: dió, banán, joghurt — stabilabb energia

### Pihenj

* 2 óránként 5 perc szünet, legalább állj fel
* 1× sétálj ki a szobából 15 percre

### Mentális

* **ne akarj tökéleteset**
* légy **gyors döntésekre kész**
* fogadd el, hogy a hackathon **kontrollált káosz**
* a jó csapatmorál több projektet visz át, mint a jó kód
