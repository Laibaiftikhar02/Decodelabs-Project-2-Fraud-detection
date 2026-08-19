# Project 2 Results Summary

## Dataset
- Transactions: 1,200
- Proxy fraud cases: 99
- Proxy fraud rate: 8.25%

## Baseline comparison

|                     |   Precision |   Recall |   ROC-AUC |   PR-AUC |
|:--------------------|------------:|---------:|----------:|---------:|
| Logistic Regression |      0.6071 |     0.85 |    0.9736 |   0.8254 |
| Random Forest       |      0.8    |     0.6  |    0.977  |   0.823  |

## Tuned Random Forest

- Precision: 0.7778
- Recall: 0.7000
- ROC-AUC: 0.9759
- PR-AUC: 0.8309

Best hyperparameters:
```text
{
  "model__max_depth": 8,
  "model__min_samples_leaf": 1,
  "model__n_estimators": 200
}
```

## Important limitation
The original Excel file contains no ground-truth fraud label. The `FraudFlag` used here is a transparent proxy target created from transaction-risk rules for educational/demo purposes. A real fraud dataset with verified labels should replace this proxy target before presenting the work as actual fraud detection.
