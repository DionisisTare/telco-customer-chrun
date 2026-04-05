 End-to-end machine learning pipeline for predicting customer churn in a telecom dataset
 Objective
Predict which telecom customers are likely to cancel their subscription (churn)
using data from 7,043 customers and 5 different analytical methods.

Business Problem
Telecom companies lose 15–25% of customers annually to churn. Acquiring a new customer costs 5–7x more than retaining an existing one. This project builds a system to identify at-risk customers before they leave, enabling targeted retention campaigns.

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

Why Recall matters here: Missing a churner (false negative) is more costly than a false alarm. Threshold optimization was applied to maximize recall while controlling precision.


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

 What I Learned

XGBoost and Logistic Regression had nearly identical AUC (0.847 vs 0.845) — tree-based methods don't always win. In this case, the simpler model is nearly as powerful and far more interpretable for business stakeholders.
SHAP revealed that tenure dominates all other features — a single variable (how long the customer has been subscribed) explains more of the churn risk than pricing, service type, or contract length combined.
Threshold optimization matters: the default 0.5 threshold gave poor recall on the minority class. Lowering it to ~0.35 significantly improved churn detection without unacceptable precision loss.
Statistical testing (Mann-Whitney U, Chi-Square) before modeling confirmed which features were genuinely informative — a step often skipped in portfolio projects.

Author

**DionisisTare** — Telecom Churn Analysis Project, 2026
