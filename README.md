# Project 2 — Supervised Learning: Fraud Detection Pipeline

## Overview
A supervised-learning pipeline for identifying potentially fraudulent transactions in an imbalanced transaction dataset.

### Techniques
- Data audit and exploratory analysis
- Feature engineering from date fields
- One-hot encoding and scaling
- SMOTE for class imbalance
- Logistic Regression baseline
- Random Forest classifier
- GridSearchCV hyperparameter tuning
- Precision, Recall, ROC-AUC and PR-AUC evaluation
- Model persistence with Joblib

## Important Dataset Limitation
The supplied Excel workbook contains **1,200 transactions but no real fraud/legitimate target label**.

To make the assignment executable, this repository uses a **proxy `FraudFlag`** generated from transparent transaction-risk rules. The proxy label is for educational/demo purposes only and must not be described as verified fraud ground truth.

If a genuine fraud label is later provided, replace the proxy-target creation step and rerun the same modeling pipeline.

## Repository Structure
```text
Project_2_Fraud_Detection/
├── data/
│   └── fraud_detection_dataset_proxy.csv
├── models/
│   └── fraud_detection_random_forest_smote.joblib   # created after notebook run
├── outputs/
├── fraud_detection_pipeline.ipynb
├── requirements.txt
└── README.md
```

## How to Run
```bash
pip install -r requirements.txt
jupyter notebook fraud_detection_pipeline.ipynb
```

Run all cells from top to bottom.

## Expected Workflow
1. Load and audit data.
2. Inspect class imbalance.
3. Build/verify proxy target.
4. Split data using stratification.
5. Preprocess numerical and categorical variables.
6. Apply SMOTE only within the training pipeline.
7. Train Logistic Regression and Random Forest.
8. Tune Random Forest with 5-fold ROC-AUC.
9. Evaluate Precision, Recall, ROC-AUC and PR-AUC.
10. Save the final pipeline with Joblib.
