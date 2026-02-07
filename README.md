# Predicting Patient Readmission (Logistic Regression)

## Overview
This project uses Logistic Regression to identify which patient factors most strongly influence hospital readmission. By analyzing demographic, clinical, and lifestyle variables, the model helps determine which patients are at higher risk of returning to the hospital, supporting proactive care planning and operational decision‑making.
## Business Question
What factors most significantly influence whether a patient is readmitted to the hospital?
## Dataset
- Medical records containing demographic, clinical, and service‑related variables
- Target variable: ReAdmis (binary: 0 = not readmitted, 1 = readmitted)

### Predictor variables include:
- Children
- Gender
- Soft_drink
- HighBlood
- Stroke
- Complication_risk
- Overweight
- Arthritis
- Diabetes
- Hyperlipidemia
- BackPain
- Anxiety
- Asthma
- Services
- Initial_days

Cleaned datasets and model inputs are stored in the data/ folder.
## Data Preparation
- Checked for duplicates and missing values (none found)
- Identified and capped outliers using Z‑score thresholds
- Converted Yes/No variables to binary (1/0)
- Encoded multi‑category variables using LabelEncoder
- Created a cleaned dataset for modeling
## Modeling Approach
- Technique: Logistic Regression
- Verified no multicollinearity using Variance Inflation Factor (VIF)
- Built an initial model using all predictors
- Applied Backward Stepwise Elimination (α = 0.02) to remove non‑significant variables
- Compared initial and reduced models using:
- Bayesian Information Criterion (BIC)
- Confusion matrix
- Accuracy score
## Results
- Reduced model predictors: HighBlood, Stroke, Arthritis, Anxiety, Asthma, Initial_days
- Reduced model BIC: 935.62
- Initial model BIC: 996.55
- Accuracy score: 0.82
The reduced model provides a better fit with fewer predictors, making it more interpretable and efficient.
## Insights
- Patients with high blood pressure or a history of stroke have significantly higher odds of readmission
- Longer initial hospital stays strongly increase readmission likelihood
- Patients with arthritis, anxiety, or asthma show lower odds of readmission in this dataset
- Reduced model outperforms the initial model while remaining simpler and more actionable
- Identifying high‑risk groups supports targeted follow‑up care and resource planning
## Conclusion
The Logistic Regression model identifies key predictors of patient readmission, with stroke history, high blood pressure, and initial hospital stay length being the most influential. These insights can help hospitals develop targeted care plans, allocate resources effectively, and reduce avoidable readmissions.
