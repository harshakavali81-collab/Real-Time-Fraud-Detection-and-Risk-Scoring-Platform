# Project structure — Real Time Fraud Detection and Risk Scoring Platform

```text
Real-Time-Fraud-Detection-and-Risk-Scoring-Platform/
├── README.md                      # Overview, scope and run instructions
├── engine.py                      # Data generation, training, evaluation and inference
├── api.py                         # FastAPI health, inference, search/recommend endpoints
├── requirements.txt               # Reproducible Python dependencies
├── Dockerfile                     # Local container build and API command
├── run_checks.sh                  # Local test command
├── tests/
│   └── test_project.py            # Synthetic pipeline and inference smoke tests
├── artifacts/
│   ├── README.md                   # Artifact generation guidance
│   └── metrics.json               # Recorded demo evaluation statistics
├── docs/
│   ├── architecture.svg           # Visual flow diagram
│   ├── figures/
│   │   └── evaluation.svg         # Synthetic/sample evaluation visualization
│   ├── data_dictionary.md         # Feature reference
│   ├── implementation.md          # Method and evaluation description
│   ├── model_card.md              # Model limitations and intended use
│   ├── PROJECT_STRUCTURE.md       # This file
│   └── WORKFLOW.md                # End-to-end process diagram
└── .github/workflows/ci.yml       # Automated tests on GitHub
```

## Key commands
```bash
pip install -r requirements.txt
python engine.py train
python -m unittest discover -s tests -v
uvicorn api:app --reload
```

Generated binary models and PNG evaluation plots are produced locally by training and may be excluded from source control. SVG figures are tracked for lightweight GitHub previews. No personal, financial or medical source records are included.
