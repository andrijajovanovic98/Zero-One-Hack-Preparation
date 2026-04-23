# Zero One Hack: Vienna's Supercompute AI Hackathon - Team Prep

Ez a repository a **Zero One Hack Vienna 2026** felkészülésére készült.

Nem az a cél, hogy "majd ott kitalálunk valamit", hanem hogy a csapat már az esemény előtt rendelkezzen közös technikai alappal, gyorsan újrahasznosítható projektstruktúrával, begyakorolt workflow-val és pitch sablonnal.

**Röviden: ez a repo egy hackathon operating system a csapat számára.**

---

## Team Motto

> Build fast. Cut scope. Keep it real. Demo what works.

---

## Hogyan használd ezt a repót

A dokumentáció témák szerint van bontva a [docs/](docs/) mappában. Ha most először olvasod, menj sorban. Ha már ismered, ugorj oda, ami épp kell.

### Strategy & mindset

1. [Overview — Célok, filozófia, sikerdefiníció](docs/00-overview.md)
2. [Focus Areas — Banking / Industry / Insurance use case-ek](docs/01-focus-areas.md)

### Felkészülés az eseményre

3. [Preparation Strategy — Phase 1 & 2](docs/02-preparation-strategy.md)
4. [Tech Stack — Ajánlott eszközök és verziók](docs/03-tech-stack.md)
5. [Team Roles — Szerepkörök és felelősségek](docs/04-team-roles.md)
6. [Practice Plan — Mini-projektek és pressure test](docs/05-practice-plan.md)

### A hackathon hétvégéjén

7. [Weekend Plan — Friday / Saturday / Sunday](docs/06-weekend-plan.md)
8. [Scope & Decisions — Mit vállalunk, mit nem](docs/07-scope-and-decisions.md)
9. [Demo & Pitch — Bemutatás és prezentáció](docs/08-demo-and-pitch.md)

### Operational

10. [Git Workflow — Branching, commitek, repo struktúra](docs/09-git-workflow.md)
11. [Communication & Risk — Kommunikáció és kockázatkezelés](docs/10-communication-and-risk.md)
12. [Checklists — What to bring, personal prep, submission](docs/11-checklists.md)

---

## Quick Start

Ha most csatlakoztál a csapathoz:

1. Olvasd el az [Overview-t](docs/00-overview.md) — 5 perc.
2. Nézd meg a [Team Roles-t](docs/04-team-roles.md) és egyeztesd a csapattal, ki mit visz.
3. Állítsd be a [Tech Stack-et](docs/03-tech-stack.md) — telepítsd a csomagokat, teszteld, hogy megy a baseline.
4. Olvasd el a [Weekend Plan-t](docs/06-weekend-plan.md), hogy tudd, mire számíts.

---

## Repo Structure (tervezett)

```text
zero-one-hack-prep/
├── README.md              # ez a fájl
├── docs/                  # minden stratégiai és operational doksi
├── requirements.txt
├── .gitignore
├── notebooks/             # exploration, experiments
├── data/                  # raw/, processed/
├── src/
│   ├── data/              # load.py, preprocess.py
│   ├── models/            # train.py, predict.py, evaluate.py
│   ├── demo/              # app.py (FastAPI/Streamlit)
│   └── utils/             # helpers.py
├── outputs/               # figures/, models/, reports/
└── pitch/                 # outline.md, assets/
```

Részletes leírás: [Git Workflow doksi](docs/09-git-workflow.md).

---

## Owner

Prepared for **Zero One Hack Vienna 2026**.
