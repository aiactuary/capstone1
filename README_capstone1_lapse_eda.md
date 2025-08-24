# Capstone — Policyholder Lapse Prediction (Churn Proxy)

**Module 20.1 — Initial Report & EDA**  
This repo contains EDA and a baseline model for predicting policyholder lapse (using churn as a proxy).

## Research Question
Can machine learning classification models (logistic regression, decision trees, random forest, gradient boosting, and SVM) predict which policyholders are likely to lapse their life insurance policy within the next 12 months?

## Data
- Primary: Telco Customer Churn (public).  
- Primary dataset: **Telco Customer Churn (Kaggle)**. Download the CSV and place it in the repo as `Telco-Customer-Churn.csv` or `WA_Fn-UseC_-Telco-Customer-Churn.csv` (optionally in a `data/` folder).

## Techniques (from syllabus)
- Logistic Regression (baseline)
- Decision Tree, Random Forest, Gradient Boosting (to be added in Module 24)
- Support Vector Machine (to be added in Module 24)
- PCA for exploratory analysis
- Cross-validation for model selection

## EDA Highlights
- Rows: 7,043; Columns: 21
- Missing `TotalCharges` imputed from `MonthlyCharges` when blank
- Class balance (lapse/churn rate): **35.10%**
- Example key drivers (from baseline coefficients): short tenure, month-to-month contract, electronic check, higher monthly charges

## Baseline Model (Logistic Regression)
Test metrics (75/25 split, random_state=7) — generated after you run the notebook on the real Telco dataset:  
- **ROC-AUC:** 0.813  
- **Accuracy:** 0.728  
- **Precision:** 0.621  
- **Recall:** 0.576  

Confusion Matrix (rows=true, cols=pred):  
[[926 217]
 [262 356]]

> Rationale: ROC-AUC is preferred over accuracy due to class imbalance; recall is monitored to avoid missing high-risk lapsers.

## Files
- [`capstone_lapse_eda.ipynb`](./capstone_lapse_eda.ipynb) — EDA + baseline model

## How to Run
```bash
pip install -r requirements.txt  # optional
jupyter lab  # or jupyter notebook
# open capstone_lapse_eda.ipynb and run all
```

## Next Steps
- Add tree/ensemble models + SVM with cross-validation
- Add calibration and business-threshold analysis
- Convert probabilities to retention-action tiers
- Prepare executive brief visuals for Module 24


> **Note:** Run the notebook section **Export Key Results to README.md** to auto-write CV and test metrics here after training on the Telco dataset.
