 End-to-end machine learning pipeline for predicting customer churn in a telecom dataset
 Objective
Predict which telecom customers are likely to cancel their subscription (churn)
using data from 7,043 customers and 5 different analytical methods.
Methodology
1. Exploratory Data Analysis (EDA)
2. Statistical Testing (Mann-Whitney U, Chi-Square)
3. Logistic Regression + Statsmodels (p-values, OR, 95% CI)
4. Random Forest (200 trees, MDI importance)
5. XGBoost (Gradient Boosting)
6. SHAP Values (Model Explainability)
7. Threshold Optimization
   Key Results

| Model | AUC (CV) | Recall (CV) | F1 (CV) |
|-------|----------|-------------|---------|
| Logistic Regression | 0.845 ± 0.014 | **0.792 ± 0.035** | 0.626 |
| Random Forest | 0.818 ± 0.016 | 0.477 ± 0.038 | 0.541 |
| **XGBoost** | **0.847 ± 0.021** | 0.788 ± 0.021 | **0.629** |

Model | AUC (CV) | Recall (CV) | F1 (CV) |
|-------|----------|-------------|---------|
| Logistic Regression | 0.845 ± 0.014 | **0.792 ± 0.035** | 0.626 |
| Random Forest | 0.818 ± 0.016 | 0.477 ± 0.038 | 0.541 |
| **XGBoost** | **0.847 ± 0.021** | 0.788 ± 0.021 | **0.629** |

Top Churn Predictors (SHAP)
1. **tenure** — Length of subscription (mean |SHAP| = 0.110)
2. **InternetService_Fiber optic** — Type of internet service (0.062)
3. **Contract_Two year** — Contract type (0.061)
4. **MonthlyCharges** — Monthly billing amount (0.060)

Author

**DionisisTare** — Telecom Churn Analysis Project, 2026
