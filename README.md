# Hypertension Risk Prediction — Hybrid Epidemiology–ML Framework

## Overview
This repository contains the full analysis for the manuscript:

**"Beyond Traditional Risk Scores: A Hybrid Epidemiology–Machine Learning 
Approach to Hypertension Prediction Using a Public Dataset"**

Authors: O.K., O.A.

## Key Finding
Near-ceiling accuracy (~97%) observed in prior analyses was attributable 
to data leakage from clinically proximal features (BP_History, Medication). 
After correction using lifestyle and demographic variables only, LightGBM 
achieved ROC-AUC = 0.857 — a more generalisable and clinically meaningful result.

## Repository Structure
hypertension-ml-prediction/
├── hypertension_analysis.ipynb   ← Full analysis notebook
├── data/
│   └── hypertention.csv          ← Dataset (UCI ML Repository)
├── figures/                      ← All manuscript figures (fig1–fig14)
├── models/
│   ├── hypertension_lgbm_corrected.pkl
│   └── hypertension_preprocessor.pkl
├── results/
│   ├── results_corrected_featureset.csv
│   ├── results_full_featureset.csv
│   ├── results_crossvalidation.csv
│   └── shap_importance_table3.csv
├── README.md
└── requirements.txt

## Model Performance — Corrected Feature Set (10-fold CV)
| Model | CV Accuracy | CV ROC-AUC |
|---|---|---|
| LightGBM | 0.7688 ± 0.030 | 0.8484 ± 0.027 |
| XGBoost | 0.7602 ± 0.030 | 0.8417 ± 0.026 |
| Random Forest | 0.7532 ± 0.025 | 0.8377 ± 0.025 |
| Logistic Regression | 0.7174 ± 0.022 | 0.8070 ± 0.021 |

## Top Predictors (SHAP — LightGBM)
1. Age (1.1360)
2. Family History (0.9917)
3. Smoking Status (0.8662)
4. Stress Score (0.8564)
5. BMI (0.7073)

## Requirements
pip install pandas numpy scikit-learn xgboost lightgbm shap matplotlib seaborn joblib

## How to Run
1. Clone this repository
2. Open hypertension_analysis.ipynb in Google Colab or Jupyter
3. Update DATA_PATH to point to data/hypertention.csv
4. Run all cells in order

## Data Source
UCI Machine Learning Repository — Hypertension Dataset

## License
MIT License

## Citation
Manuscript in preparation — citation to be added upon publication.
