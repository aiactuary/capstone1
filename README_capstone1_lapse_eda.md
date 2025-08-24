

# Capstone part 1 — Module 20.1 — Initial Report & Exploratory Data Analysis (EDA)
I work as an actuary in life insurance company, pricing lapse-supported life insurance products. Main research question of my project is: "Can machine learning classification models (logistic regression, decision trees, random forest, gradient boosting, and SVM) predict which policyholders are likely to lapse their life insurance policy within the next 12 months?". This report summarizes the results of exploratory data analysis (EDA) and offers a baseline model for predicting policyholder lapse (using churn as a proxy). I will continue with exploring other models in second part of my capstone project.

# Note
Although the Telco Customer Churn dataset already appears in the syllabus for basic classification exercises, this project uses it in a non-standard, domain-specific way. Instead of stopping at model accuracy, I reframed churn as an insurance lapse analogue, applied threshold tuning, calibration, and risk-decile segmentation, and translated results into actionable business implications for lapse-sensitive products. This shows how even a familiar dataset can generate new insights and practical value when aligned with real industry contexts.

## Files

- [Jupyter Notebook — `capstone_lapse_eda.ipynb`](capstone_lapse_eda.ipynb)
- [Dataset - 'WA_Fn-UseC_-Telco-Customer-Churn.csv'](WA_Fn-UseC_-Telco-Customer-Churn.csv)


## Summary of Findings (Initial EDA & Baseline)

- **Dataset**: 7,043 customers from the "https://github.com/aiactuary/capstone1/raw/main/WA_Fn-UseC_-Telco-Customer-Churn.csv", including demographic, contract, billing, and service usage features.
- **Target distribution**: About **26%** of customers churned (lapsed), showing moderate class imbalance.
- **EDA insights**:
  - Customers with **month-to-month contracts** lapse far more often than those with longer commitments.
  - **Electronic check** payments and **paperless billing** are associated with higher lapse risk.
  - Shorter **tenure** is strongly linked to higher lapse likelihood.
  - Higher **monthly charges** modestly increase lapse risk, though long-tenure/high-charge customers tend to persist.
  - Add-on services (e.g., Online Security, Tech Support) reduce lapse risk when subscribed.

### Baseline model (Logistic Regression)
- **ROC-AUC ≈ 0.86** → good ability to rank high-risk vs low-risk customers.  
- **Accuracy ≈ 0.78; Precision ≈ 0.55; Recall ≈ 0.81** → good recall for identifying most churners, but precision is modest, so predictions are best used as a risk flag for retention actions, not as an absolute yes/no.  
- Top predictors matched EDA findings: tenure, contract type, payment method, and monthly charges.  

### Interpretation and limitations
- Accuracy looks fair, but it overstates performance because most customers do not churn.
- With precision ≈ 0.55 and recall ≈ 0.81, the model catches most churners but also flags some non-churners.
- Predictions are best used as risk tiers (e.g., top 10% = “high-risk” cohort) so retention teams can focus campaigns where the likelihood of churn is highest.

### Implication
Predictive modeling can meaningfully separate higher- and lower-risk policyholders: even baseline model highlights actionable segments for targeted retention.

## Next Steps for Module 24

- Expand modeling with Decision Tree, Random Forest, Gradient Boosting, and SVM using cross-validation.
- Add calibration and business-threshold analysis (already scaffolded in the notebook).
- Convert predicted probabilities into actionable lapse-risk tiers for retention campaigns.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/aiactuary/capstone1/blob/main/capstone_lapse_eda.ipynb)




