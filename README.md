# Real-Time Fraud Detection and Risk Scoring Platform

A reproducible synthetic-payment fraud-triage prototype with model comparison, saved evaluation evidence and a FastAPI interface.

[Setup](#local-installation--setup-guide) · [Architecture](#architecture--system-design-diagram) · [Detailed guide](PROJECT_GUIDE.md) · [Repository standard](docs/REPOSITORY_STANDARD.md)

## Visuals

![Architecture](<docs/architecture.svg>)

Existing project visual; diagrams and illustrative graphics are not evidence of a deployed application.

## Live Link / Demo

Run the local demo using the setup guide below. No public deployment URL has been verified for this documentation update.

## Key Features

- Deterministic synthetic (or bundled sample) input generation with controlled seed 42; no client, patient or banking records.
- Leakage-conscious model development and evaluation: Classification: Logistic Regression vs Random Forest, PR-AUC, recall, alert threshold.
- Baseline comparison, numerical evaluation output in `artifacts/metrics.json`, and plotted holdout evidence `docs/figures/evaluation.svg`.
- Model serialized to `artifacts/model.joblib`, accompanying SHA-256-short manifest and example FastAPI interface.
- Input validation, unit tests, Dockerfile, example GitHub Actions job, data dictionary, model card, and architecture diagram.

## Tech Stack

![Python](https://img.shields.io/badge/Python-334155?style=flat-square) ![FastAPI](https://img.shields.io/badge/FastAPI-334155?style=flat-square) ![scikit-learn](https://img.shields.io/badge/scikit--learn-334155?style=flat-square) ![NumPy](https://img.shields.io/badge/NumPy-334155?style=flat-square) ![Docker](https://img.shields.io/badge/Docker-334155?style=flat-square)

Dependency versions and optional packages are defined in the repository manifests.

## Architecture / System Design Diagram

[Architecture documentation / diagram](<docs/architecture.svg>)

## Local Installation & Setup Guide

```bash
git clone https://github.com/harshakavali81-collab/Real-Time-Fraud-Detection-and-Risk-Scoring-Platform.git
cd Real-Time-Fraud-Detection-and-Risk-Scoring-Platform
```

Requires Python and the packages in `requirements.txt`:

```bash
python -m venv .venv
# Windows PowerShell: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
python engine.py train
python -m unittest discover -s tests -v
python -m uvicorn api:app --reload
```

Open http://127.0.0.1:8000/docs for the local API. Training regenerates model artifacts; evaluation uses synthetic/sample inputs.

## Challenges & Solutions

A model score is useful only when its data and evaluation are reproducible. The project pairs a deterministic demonstration pipeline with baseline comparison, saved metrics and synthetic/sample-data limitations. See [the implementation notes](docs/implementation.md) and [model card](docs/model_card.md); these results do not establish real-world performance.

## Future Improvements

- Capture a reproducible end-to-end demo with runtime versions and sample inputs.
- Expand regression checks for invalid inputs and documented edge cases.
- Record measured results, data provenance and deployment limitations alongside each release.

## Scope and supporting evidence

> **Status:** reproducible synthetic-data, local research/portfolio demonstration. The source requirements mention advanced production services; this implementation does **not** claim real-world validation, 24/7 streaming, clinical use, live cloud hosting or third-party system integration.

## Repository Structure

| Location | Purpose |
| --- | --- |
| `tests/` | Tests |
| `docs/` | Documentation |
| `.github/` | Issue forms, PR template and automated checks |

[Complete file inventory and workflow](docs/REPOSITORY_STANDARD.md). Runtime entry points retain their existing paths.

## Workflow & Tracking

Use the [bug and feature forms](https://github.com/harshakavali81-collab/Real-Time-Fraud-Detection-and-Risk-Scoring-Platform/issues/new/choose) to define work with acceptance criteria. Keep tasks in Todo → In progress → Review → Done, and link a pull request with `Closes #<number>`. See [the maintenance workflow](docs/REPOSITORY_STANDARD.md#workflow).

## License

Original project software is available under the [MIT License](LICENSE). See [licensing scope](docs/LICENSING.md) for third-party and data exclusions.

