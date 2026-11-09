# Jeevah — Tri-Dhat Tongue Image Research

Jeevah is a local research prototype that classifies a tongue image into three Traditional Thai Medicine (TTM) Tri-Dhat categories: **Pitta, Vata, and Kapha**. It uses a React web interface, a FastAPI service, and a TensorFlow/Keras DenseNet121 model. The page shows all three model scores and an educational food guide matched to the highest score.

## Run locally on Windows

Use PowerShell from the project folder:

```powershell
.\scripts\setup.ps1
.\.venv\Scripts\python.exe -m scripts.serve --experimental
```

Keep the terminal open and visit **http://127.0.0.1:5173/**. In Git Bash, the start command is:

```bash
./.venv/Scripts/python.exe -m scripts.serve --experimental
```

The experimental model files (`best.keras`, `metadata.json`, and `test.json`) are stored locally under `artifacts/retrain-head-20261108/` and are excluded from Git. Prediction mode will not start if those files are missing. The dataset and local Python/Node runtimes are also not included in the repository.

## Research limitations

This is **not a disease detector or medical device**. Scores are uncalibrated model outputs, not disease probabilities or a person's measured body proportions. Food-guide text is general educational content, not personal diet advice.

On the saved 74-image test split, the model reached **59.5% accuracy**, below the **63.5% majority-class baseline**, and classified **0 of 5 Vata images** correctly. The model and split have not passed independent review or clinical validation; do not use the output to make health decisions.

## Data and reference

- Dataset: [Tongue image dataset for Tri-Dhat classification](https://doi.org/10.5281/zenodo.12525502) (download and review its terms before use).
- Reference implementation and research paper: [Tonge-Image-Classification](https://github.com/kasikrit/Tonge-Image-Classification).

The reference repository is licensed under GPL-3.0. Preserve its license and notices for any code reused from it; this project does not declare a separate license.
