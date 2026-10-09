# Predicting Core-Collapse Supernova Explodability with Machine Learning

![Python](https://img.shields.io/badge/python-3.9%2B-blue) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange) ![scikit-learn](https://img.shields.io/badge/scikit--learn-models-f7931e) ![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-ff6f00)

Undergraduate research project (2023–2024) applying machine learning to a grid of **~1,500 simulated core-collapse supernovae (CCSN)**. Using progenitor properties — zero-age main-sequence mass (`zams`), compactness parameters (`xi_1.5` … `xi_3.0`), and silicon/iron core masses and radii — the models predict whether a star **explodes** and estimate related explosion properties.

## Highlights

- Tree-based classifiers predict explosion outcome with **97.9% (Decision Tree)** and **98.6% (Random Forest)** accuracy.
- Diagnosed multicollinearity among compactness features (VIF) before interpreting feature importance.
- Neural-network regressors (TensorFlow/Keras) with grid-searched weights, plus model interpretation via SHAP and permutation importance (eli5).
- Exploratory analysis of the 1,500-model dataset with correlation heat maps and distribution plots.

## Contents

- [`notebooks/01_dataset_exploration.ipynb`](notebooks/01_dataset_exploration.ipynb) — EDA of the 1,500-progenitor dataset
- [`notebooks/02_linear_classification.ipynb`](notebooks/02_linear_classification.ipynb) — linear baselines and collinearity diagnostics
- [`notebooks/03_tree_classifiers.ipynb`](notebooks/03_tree_classifiers.ipynb) — Decision Tree / Random Forest explosion classifiers and feature importance
- [`notebooks/04_neural_networks.ipynb`](notebooks/04_neural_networks.ipynb) — neural-network models with SHAP interpretation
- [`notebooks/05_neural_network_experiments.ipynb`](notebooks/05_neural_network_experiments.ipynb) — extended experiments (main research notebook)
- [`notebooks/06_tf_model_unnormalized.ipynb`](notebooks/06_tf_model_unnormalized.ipynb) — TensorFlow model trained on unnormalized progenitor data
- [`notebooks/07_tf_model_normalized_analysis.ipynb`](notebooks/07_tf_model_normalized_analysis.ipynb) — analysis of the normalized-data model (line, bar and violin plots)

## Repository Structure

```text
ccsn-explodability-ml/
├── notebooks/
│   ├── 01_dataset_exploration.ipynb
│   ├── 02_linear_classification.ipynb
│   ├── 03_tree_classifiers.ipynb
│   ├── 04_neural_networks.ipynb
│   ├── 05_neural_network_experiments.ipynb
│   ├── 06_tf_model_unnormalized.ipynb
│   └── 07_tf_model_normalized_analysis.ipynb
├── README.md
└── requirements.txt
```

## Tech Stack

Python, scikit-learn, TensorFlow/Keras, statsmodels, SHAP, eli5, pandas, seaborn

## Getting Started

```bash
git clone https://github.com/siddakmarwaha/ccsn-explodability-ml.git
cd ccsn-explodability-ml
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

## Data

The simulation results (`results_s16.csv`, `results_s18.csv`, progenitor tables) come from the research group and are **not included**. Place them next to the notebooks (paths are referenced at the top of each notebook). Outputs are preserved so results can be reviewed without re-running.

## Author

**Siddak Marwaha**

## License

All rights reserved. This is undergraduate research work shared for portfolio review; please contact the author before reusing code or results.
