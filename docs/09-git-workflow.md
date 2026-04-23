# Git Workflow & Repository Structure

Hackathon alatt a git célja nem a szépség — a **biztonság** és az **átláthatóság**. Egy elveszett 2 órás munka drágább, mint egy ronda commit history.

---

## Branching

### Egyszerű branch modell (ajánlott 2–4 fős csapatra)

* `main` → stabil, **demo-kész** állapot
* `dev` → integráció (opcionális, csak nagyobb csapatnál)
* `feature/*` → egyéni feladatok

### Példa branchek

* `feature/data-pipeline`
* `feature/baseline-model`
* `feature/demo-ui`
* `feature/pitch-assets`
* `feature/fraud-explainer`

### Szabály

**`main` mindig működjön.** Ha valaki lehúzza a `main`-t, simán lefut a demo. Ha ez sérül, azonnal álljon meg minden más munka, amíg vissza nincs állítva.

---

## Commit szabály

Egyszerű, rövid, világos commitok. Az ige imperatívuszban.

### Jó példák

* `add baseline training pipeline`
* `implement anomaly scoring`
* `prepare pitch draft`
* `fix preprocessing bug`
* `add SHAP explainability to demo`
* `update README with demo instructions`

### Rossz példák

* `stuff` ❌
* `wip` ❌ (csak ha azonnal felülírod)
* `final version` ❌ (sosem az)
* `fixed lots of things` ❌

### Rule

> **Hackathon alatt a commit célja nem a szépség, hanem a biztonság és az átláthatóság.**

### Commit gyakoriság

* Legalább **2 óránként** commit, akár csak WIP
* Minden működő milestone után egy commit (pl. "baseline trains successfully")
* Lefekvés / szünet előtt mindig commit + push

---

## Push és pull

### Pull először, aztán dolgozz

```bash
git pull origin main
# csak most kezdj dolgozni
```

### Ha konfliktus van

1. **Ne pánikolj.**
2. Nézd meg, mit változott mindkét oldalon.
3. Ha nem világos, kérdezd meg azt, akivel ütközöl.
4. **Soha ne `reset --hard`** a másik munkájára.

### Force push szabály

`--force` vagy `--force-with-lease` **csak a saját feature branchedre**. Sose `main`-re.

---

## Pull Requests (opcionális, de ajánlott)

Ha van idő:

* minden feature branchet PR-on keresztül mergelj
* 5 perces önreview is elég
* legalább a commit üzenete legyen értelmes

Ha sietsz:

* direkt push `main`-re, de **commit üzenetben mondd el, mi változott**
* nagyobb változásoknál kérj gyors nézést Discordon

---

## `.gitignore` — kötelező elemek

```gitignore
# Python
__pycache__/
*.pyc
*.pyo
.venv/
venv/
env/
*.egg-info/
.ipynb_checkpoints/

# Data — SOHA ne commitolj nagy adatot
data/raw/
data/processed/
*.csv
*.parquet
*.h5
# (kivéve ha tényleg kicsi és repo-ban a helye)

# Model artifacts
*.pkl
*.joblib
*.pt
*.ckpt
outputs/models/

# Secrets
.env
.env.local
*.key
credentials.json

# OS / editor
.DS_Store
Thumbs.db
.vscode/
.idea/
*.swp
```

### Kritikus szabály

**Sose commitolj:**
* API kulcsot
* jelszót
* adatbázis credential-t
* nagy (>10MB) bináris fájlt

Ha mégis megtörtént → **azonnal** rotáld a kulcsot és tisztítsd a git historyból (vagy hozz létre új repot).

---

## Suggested Repository Structure

```text
zero-one-hack-prep/
│
├── README.md                     # főoldal, navigáció
├── docs/                         # részletes doksik (ez a mappa)
├── requirements.txt              # függőségek
├── pyproject.toml                # opcionális, modern alternative
├── .gitignore
├── .env.example                  # minta env változók (kulcsok NÉLKÜL)
│
├── notebooks/
│   ├── 01_exploration.ipynb
│   ├── 02_baseline.ipynb
│   └── 03_experiments.ipynb
│
├── data/
│   ├── raw/                      # .gitignore-olt
│   └── processed/                # .gitignore-olt
│
├── src/
│   ├── __init__.py
│   ├── data/
│   │   ├── load.py               # adat betöltés
│   │   ├── preprocess.py         # cleaning, feature eng.
│   │   └── validate.py           # sanity checks
│   ├── models/
│   │   ├── train.py
│   │   ├── predict.py
│   │   └── evaluate.py
│   ├── demo/
│   │   └── app.py                # Streamlit / FastAPI entry
│   └── utils/
│       ├── helpers.py
│       └── plots.py
│
├── outputs/
│   ├── figures/
│   ├── models/                   # .gitignore-olt
│   └── reports/
│
├── pitch/
│   ├── outline.md
│   ├── deck.pdf                  # vagy link
│   └── assets/
│
└── tests/                        # opcionális
    └── test_pipeline.py
```

Ez csak kiindulópont. A lényeg, hogy **gyorsan eligazodjon benne mindenki**.

---

## Gyakori git hibák és megoldások

### "Véletlenül felülírtam valakinek a fájlját"

```bash
git reflog              # látod minden commitod hash-ét
git checkout <hash> -- <file>   # visszaállítod egy adott fájlt
```

### "Commitoltam, amit nem akartam"

```bash
git reset --soft HEAD~1  # commit visszavonva, változások megmaradnak
```

### "Egy nagy fájlt véletlenül hozzáadtam, és lassú a push"

```bash
git rm --cached <file>
echo "<file>" >> .gitignore
git commit -m "remove big file from tracking"
```

Ha már pusholva volt és méret-limit miatt nem jön vissza, használj `git filter-repo`-t, vagy a végső esetben hozz létre új repot.

### "Merge conflict és félek a mergelni"

Kérj segítséget. Komolyan. Egy rossz merge kétszer annyi időbe kerül, mint egy közös 10 perces megoldás.

---

## Final git szabály

> **Commit early, commit often, push regularly.**

A fejben maradt munka elveszhet. A nem-pusholt munka elveszhet. A gépen lévő fájlok elveszhetnek. Csak az számít, ami a `origin` távoli repón van.
