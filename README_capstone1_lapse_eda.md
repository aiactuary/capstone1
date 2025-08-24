# Capstone — Policyholder Lapse Prediction (Churn Proxy)

## Main Research Question of my Capstone Project
I work as an actuary in life insurance company, pricing lapse-supported life insurance products. Main research question of my project is: "Can machine learning classification models (logistic regression, decision trees, random forest, gradient boosting, and SVM) predict which policyholders are likely to lapse their life insurance policy within the next 12 months?"

**Module 20.1 — Initial Report & Exploratory Data Analysis (EDA)**  
This report summarizes the results of exploratory data analysis (EDA) and a serach of a baseline model for predicting policyholder lapse (using churn as a proxy). I will continue with exploring other models in second part of my capstone project.

**Summary of Findings (Initial EDA & Baseline)**

Dataset: 7,043 customers from the Telco Customer Churn dataset (Kaggle), including demographic, contract, billing, and service usage features.
Target distribution: About 26% of customers churned (lapsed), showing moderate class imbalance.
EDA insights:
 Customers with month-to-month contracts lapse far more often than those with longer contracts.
 Electronic check payments and paperless billing are associated with higher lapse risk.
 Shorter tenure is strongly linked to higher lapse likelihood.
 Higher monthly charges are modestly associated with lapses, though long-tenure/high-charge customers tend to persist.
 Add-on services (e.g., Online Security, Tech Support) reduce lapse risk when subscribed.
 Baseline model (Logistic Regression):
 ROC-AUC ≈ 0.81 → good discrimination ability.
 Accuracy ≈ 0.73; Precision ≈ 0.62; Recall ≈ 0.58.
 Top predictors matched EDA findings: tenure, contract type, payment method, and monthly charges.
 Implication: Predictive models can meaningfully identify at-risk policyholders. Early detection enables targeted retention campaigns, which can  improve persistency and profitability.
