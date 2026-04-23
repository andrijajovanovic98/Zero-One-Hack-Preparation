# Tech Stack — Ajánlott eszközök és verziók

A hackathonhoz olyan stack kell, ami **gyors, ismert és megbízható**. Hackathon alatt az eszköz akkor jó, ha gyorsít, nem akkor, ha imponál.

---

## Core

| Tool | Verzió | Miért |
|---|---|---|
| Python | 3.11 | Stabil, gyors, minden library támogatja. Ne 3.12+ — egyes library-k még nem kompatibilisek. |
| Jupyter / notebooks | latest | Exploration és demo fallback. |
| pandas | 2.x | Tabular adat standard. |
| polars | >=0.20 | Nagy adathalmazokra, ha pandas lassú. Opcionális. |
| numpy | 1.26+ | Kötelező. |
| scikit-learn | 1.4+ | Minden baseline, preprocessing, evaluation. |

---

## Modeling

| Tool | Mikor |
|---|---|
| **XGBoost** | Tabular classification/regression default. Robust, gyors, jó defaultokkal. |
| **LightGBM** | Alternatíva XGBoost-hoz. Gyorsabb nagy adaton, kezeli a kategorikusokat. |
| **CatBoost** | Ha sok kategorikus oszlop van. |
| **Prophet** | Time series forecast, ha gyorsan kell valami működő. |
| **statsmodels** | ARIMA, klasszikus TS modellek. |
| **PyTorch** | Csak ha tényleg szükséges (kép, hang, speciális NLP). Huggingface transformers API-ján keresztül. |
| **Huggingface transformers** | Pretrained NLP/vision modellek. Ne fine-tune-olj, csak inference/feature extraction hackathon alatt. |
| **sentence-transformers** | Text embedding. `all-MiniLM-L6-v2` a go-to gyors modell. |

---

## API / Demo

| Tool | Mikor |
|---|---|
| **FastAPI** | REST endpointnak. 10 perc alatt áll egy `/predict`. |
| **Streamlit** | Gyors UI. Egy fájl, működik. **Default választás demóhoz.** |
| **Gradio** | Alternatíva Streamlit-hez, különösen ML modellekhez. |
| **React + Vite** | Csak akkor, ha valaki nagyon rutinos benne. Hackathonon időbomba. |

---

## Visualization

| Tool | Mikor |
|---|---|
| **matplotlib** | Notebookban gyors plotolás. |
| **seaborn** | Statisztikai plotok (heatmap, pairplot). |
| **plotly** | Interaktív plotok a demóban. |
| **altair** | Ha deklaratív API jobban megy. |

---

## Collaboration

- **GitHub** — code + issues + project board
- **GitHub Projects** vagy **Notion** egyszerű kanban task boardnak
- **Discord / WhatsApp / Slack** a gyors kommunikációhoz
- **Google Drive** / **OneDrive** — pitch deck, közös doksik

---

## Optional

Ezeket csak akkor húzd be, ha **nem lassítanak**.

| Tool | Mikor NE |
|---|---|
| Docker | Ha nem szoktál vele dolgozni. Hackathon alatt nem a legjobb tanulni. |
| MLflow | Ha még sosem használtad. Overkill 36 órára. |
| Weights & Biases | Ugyanaz — ha nincs rutin, skip. |
| Kubernetes | NE. |
| Airflow / Prefect | NE. |

---

## LLM használat

Ha a feladat megengedi (és gyakran igen):

- **OpenAI API** (`gpt-4o-mini` gyors, olcsó; `gpt-4o` komolyabb feladatra)
- **Anthropic API** (`claude-haiku-4-5` gyors, `claude-sonnet-4-6` minőség)
- **Ollama** lokális modellekhez, ha offline kell
- **Huggingface inference endpoints** — ingyenes tier van

**Fontos:** az LLM hívást **cache-eld** (még egy dict is jó), mert különben percekbe telik, és a demóban is lassú.

---

## Requirements.txt sablon

```txt
# Core
python>=3.11
pandas>=2.0
numpy>=1.26
polars>=0.20

# ML
scikit-learn>=1.4
xgboost>=2.0
lightgbm>=4.0
catboost>=1.2

# Time series
prophet>=1.1
statsmodels>=0.14

# NLP (opcionális)
sentence-transformers>=2.2
transformers>=4.35

# API / Demo
fastapi>=0.104
uvicorn>=0.24
streamlit>=1.28

# Viz
matplotlib>=3.8
seaborn>=0.13
plotly>=5.18

# Utils
python-dotenv>=1.0
tqdm>=4.66
jupyter>=1.0
```

---

## Environment setup parancsok

### conda / mamba (ajánlott)

```bash
mamba create -n zeroone python=3.11 -y
mamba activate zeroone
pip install -r requirements.txt
```

### venv

```bash
python -m venv .venv
source .venv/bin/activate    # Linux/Mac
.venv\Scripts\activate       # Windows
pip install -r requirements.txt
```

### Environment check script

Tegyél be egy `scripts/check_env.py`-t, ami importálja mind a kulcs library-kat és kiír egy OK/FAIL-t. Mindenki futtassa **legalább 3 nappal a hackathon előtt**.

---

## Hardver / compute

- **saját laptop**: legyen töltő + hosszabbító
- **GPU** ha kell: Colab Pro, Kaggle notebooks, Huggingface Spaces
- **tartalék internet**: mobil hotspot ha bedöglik a helyszíni wifi
- **nagy adathalmaz**: pendrive vagy SSD-n vidd magaddal, ne nagy letöltéssel kezdj a helyszínen

---

## Mit NE húzz be az utolsó pillanatban

- új library, amivel még sosem dolgoztál
- új framework, amit a Twitteren láttál
- AutoML cuccot, ami "mindent megold"
- saját custom neural net architektúrát scratchből

**Szabály:** hackathon hétvégéjén csak olyan eszközt használunk, amit Phase 2 alatt legalább egyszer használtunk sikerrel.
