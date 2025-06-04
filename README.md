# Fire Incident Analysis - DI 501 Term Project

## Overview

This project investigates two critical questions in the domain of fire management using the 2023 "Yılı Yangın Müdahale İstatistiği" dataset:

1. **Do fire department arrival times differ significantly across seasons, regions, and fire causes?**
2. **Can fire outcomes and required water resources be predicted based on fire characteristics such as cause, location, and response time?**

## Dataset

- **Source:** 2023 İzmir Fire Incident Dataset
- **Size:** 12,986 fire incident records
- **Features:** 23 categorical and numerical attributes related to fire events

## Research Questions

### Q1: Arrival Time Variability

- **Statistical Methods:** Shapiro-Wilk Test (normality), Kruskal-Wallis H Test (group difference)
- **Findings:** Arrival times vary significantly across seasons, address regions, and fire causes.

### Q2: Predictive Modeling of Fire Outcomes and Resource Needs

- **Tasks:**
  - Classification: Predict fire severity ("low", "moderate", "high")
  - Regression: Predict water resource usage 

## Data Preparation

- **Missing Data Handling:**
  - Median imputation (arrival time)
  - KNN imputation (water used)
- **Outlier Removal:** IQR method
- **Feature Engineering:** season, month, day_of_week, ordinal encoding of fire outcome
- **Transformations:** Log-scaling of skewed numerical features
- **Encoding:** Label Encoding, Ordinal Encoding
- **Normalization:** StandardScaler

## Modeling

### Classification Models

- Random Forest
- Logistic Regression
- Naive Bayes
- XGBoost
- k-NN
- ANN
- Dummy Classifier (baseline)

### Regression Models

- XGBoost
- Gradient Boosting
- Random Forest
- SVR
- ANN
- k-NN
- Linear Regression
- Dummy Regressor (baseline)

## Performance Summary

### Classification (F1 Macro Score)

- **Best Model:** Random Forest (F1 = 0.3973)
- **Baseline:** Dummy Classifier (F1 = 0.3185)

### Regression (R² Score)

- **Best Model:** Gradient Boosting (R² = 0.1815)
- **Baseline:** Dummy Regressor (R² = 0.000)

## Hyperparameter Tuning

- **Regression:** GridSearchCV
- **Classification:** RandomizedSearchCV
- **Validation:** 3-fold cross-validation

## Interpretability

- **Techniques Used:** Feature Importance, Permutation Importance
- **Key Features:**
  - **Classification:** Fire cause, district, arrival time
  - **Regression:** Address region, fire cause

## Baseline Comparison

- Random Forest and XGBoost significantly outperform dummy models in F1 macro and R² scores.
- Statistical tests (e.g., Mann-Whitney U Test) support the superiority of tuned models in non-normal and imbalanced data contexts.

## Applications

- **Fire Prevention:** Identifying high-risk seasons/regions
- **Risk Assessment:** Prioritizing severe incidents
- **Resource Planning:** Forecasting resource needs using ML predictions

## References

Detailed citations are available in the full report.