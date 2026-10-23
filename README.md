# Emotion Text Classifier

An exploratory Natural Language Processing project that cleans short text, learns emotion labels, evaluates a Logistic Regression pipeline, and demonstrates predictions for new sentences.

Maintained by **brajesh31**.

## Overview

This project provides a reproducible notebook workflow for:

- loading a labeled emotion dataset;
- inspecting label distribution and sample records;
- removing user handles and stop words with `neattext`;
- splitting text into training and test sets;
- converting text into bag-of-words features with `CountVectorizer`;
- training a scikit-learn Logistic Regression classifier;
- measuring test-set accuracy;
- inspecting class probabilities and predicted labels; and
- exporting the trained pipeline as a local Joblib artifact.

The primary artifact is the notebook, so the repository is intended for learning, experimentation, and transparent model inspection rather than production deployment.

## Repository Layout

```text
.
├── data/
│   └── README.md
├── models/                         # Generated model artifacts (ignored by Git)
├── NLP_Emotion_IN_Text_Classifier.ipynb
├── NLP_Emotion_IN_Text_Classifier-checkpoint.ipynb
├── LICENSE
├── README.md
├── SECURITY.md
├── CONTRIBUTING.md
├── requirements.txt
└── .gitignore
```

## Requirements

- Python 3.9 or newer
- Jupyter Notebook or VS Code with the Jupyter extension
- A labeled CSV dataset with `Emotion` and `Text` columns

Install the Python dependencies in a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate        # Windows PowerShell: .venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

## Dataset Setup

Place the dataset at:

```text
data/emotion_dataset_2.csv
```

The dataset is intentionally not bundled in this repository. Review its license, privacy requirements, and redistribution terms before using or publishing it. See [data/README.md](data/README.md) for the expected schema.

## Run the Notebook

1. Install the dependencies.
2. Add a permitted dataset at `data/emotion_dataset_2.csv`.
3. Open `NLP_Emotion_IN_Text_Classifier.ipynb`.
4. Run the cells from top to bottom.
5. The trained pipeline is written to `models/emotion_classifier_logistic_regression.joblib`.

The notebook uses repository-relative paths, so it does not depend on the original author's local computer path.

## Model Notes

The current workflow is deliberately straightforward and interpretable. It uses `CountVectorizer` followed by Logistic Regression, with a fixed random seed for the train/test split. Accuracy depends on the dataset, label quality, preprocessing choices, and class balance. Treat the displayed score as an experiment result, not a universal benchmark.

Before using predictions in a real application, add a held-out evaluation set, compare against appropriate baselines, inspect per-class metrics, test for data leakage and bias, and establish a clear human review process.

## Reproducibility

- Dependencies are listed in `requirements.txt`.
- The train/test split uses `random_state=42`.
- Local datasets and generated model files are excluded from version control.
- Notebook outputs may reflect the dataset used during a local run and should be regenerated when the data changes.

## Ownership and Usage

This repository is published under the custom terms in [LICENSE](LICENSE). The source remains the property of **brajesh31**. Public visibility does not grant permission to copy, redistribute, repackage, or commercially use the code. Dataset and third-party package rights remain with their respective owners.

## Contributing

Contribution expectations are documented in [CONTRIBUTING.md](CONTRIBUTING.md). Please do not submit private, personal, or unlicensed datasets. Security concerns should be reported according to [SECURITY.md](SECURITY.md).

## Acknowledgements

This project uses open-source Python libraries including pandas, NumPy, seaborn, neattext, scikit-learn, and Joblib. Each dependency remains subject to its own license.
Last updated: 2026-10-23 17:43 UTC
