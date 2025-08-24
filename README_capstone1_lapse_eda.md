# Capstone part 1 — Module 20.1 — Initial Report & Exploratory Data Analysis (EDA)
I work as an actuary in life insurance company, pricing lapse-supported life insurance products. Main research question of my project is: "Can machine learning classification models (logistic regression, decision trees, random forest, gradient boosting, and SVM) predict which policyholders are likely to lapse their life insurance policy within the next 12 months?". This report summarizes the results of exploratory data analysis (EDA) and offers a baseline model for predicting policyholder lapse (using churn as a proxy). I will continue with exploring other models in second part of my capstone project.

## Files

- [Jupyter Notebook — `capstone_lapse_eda.ipynb`](capstone_lapse_eda.ipynb)


## Summary of Findings (Initial EDA & Baseline)

- **Dataset**: 7,043 customers from the [Telco Customer Churn dataset (Kaggle)](https://www.kaggle.com/blastchar/telco-customer-churn), including demographic, contract, billing, and service usage features.
- **Target distribution**: About **26%** of customers churned (lapsed), showing moderate class imbalance.
- **EDA insights**:
  - Customers with **month-to-month contracts** lapse far more often than those with longer commitments.
  - **Electronic check** payments and **paperless billing** are associated with higher lapse risk.
  - Shorter **tenure** is strongly linked to higher lapse likelihood.
  - Higher **monthly charges** modestly increase lapse risk, though long-tenure/high-charge customers tend to persist.
  - Add-on services (e.g., Online Security, Tech Support) reduce lapse risk when subscribed.

### Baseline model (Logistic Regression)
- **ROC-AUC ≈ 0.81** → good ability to rank high-risk vs low-risk customers.  
- **Accuracy ≈ 0.73; Precision ≈ 0.62; Recall ≈ 0.58** → useful, but not strong enough for a pure yes/no decision.  
- Top predictors matched EDA findings: tenure, contract type, payment method, and monthly charges.  

### Interpretation and limitations
- While accuracy looks fair, it is misleading because of class imbalance (most customers do not lapse).  
- Precision and recall show the model **misses ~42% of actual lapsers** and sometimes flags non-lapsers as high risk.  
- Instead of treating predictions as binary, I suggest using the model to assign **risk tiers** (e.g., top 10% highest scores = “high risk” cohort). This would allow customer retention teams to focus campaigns on those customers, where the likelihood of lapse is the highest.  

### Implication
Predictive modeling can meaningfully separate higher- and lower-risk policyholders: even an imperfect baseline model highlights actionable segments for targeted retention.

## Next Steps for Module 24

- Expand modeling with Decision Tree, Random Forest, Gradient Boosting, and SVM using cross-validation.
- Add calibration and business-threshold analysis (already scaffolded in the notebook).
- Convert predicted probabilities into actionable lapse-risk tiers for retention campaigns.






