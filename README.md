# Mortgage Affordability Prediction Analysis

## Overview
This project evaluates whether machine learning models can predict if mortgage affordability will increase or decrease one year into the future. The analysis specifically targets predicting the direction of change for Q4 2017 using historical data trends.

---

## Project Goal
The main technical question addressed:

> Is a Decision Tree better than Logistic Regression for predicting mortgage affordability trends?

---

## Methodology

### 1. Data Source
- Dataset: `Affordability_Wide_2017Q4_Public.csv`
- Provider: Zillow
- Granularity: County-level data across the United States

---

### 2. Feature Engineering & Preprocessing

| Step                     | Description |
|--------------------------|------------|
| Standardization          | Affordability values normalized per region to ensure consistency |
| Quarterly Differences    | Features created using affordability differences from 2014 to 2016 |
| Outcome Variable         | Binary classification: **Up** or **Down** (Q4 2017 vs Q4 2016) |

---

### 3. Experimental Setup

| Component               | Details |
|-------------------------|--------|
| Models Compared         | Logistic Regression (`liblinear`, `lbfgs`), Decision Tree Classifier |
| Hyperparameter Tuning   | GridSearchCV |
| Logistic Regression     | Regularization parameter `C` |
| Decision Tree           | `max_depth`, `min_samples_leaf` |
| Validation Strategy     | 10-fold Stratified Cross-Validation grouped by `RegionID` |

---

## Key Findings

### Statistical Results

| Metric           | Value   | Interpretation |
|------------------|--------|---------------|
| Logistic Regression Coefficient | +0.1342 | Logistic Regression scored approximately 13% higher on average |
| P-Value          | 0.184  | Not statistically significant (p > 0.05) |
| R-squared        | 0.096  | Model type explains only 9.6% of variance |

---

### Visual Analysis

| Visualization Type | Insight |
|-------------------|--------|
| ROC Curves        | Logistic Regression consistently outperforms Decision Tree |
| AUC Comparison    | Logistic Regression shows higher average performance but high variance |

---

## Conclusion

- Logistic Regression achieved a higher mean performance:
  - AUC ≈ 0.70
- Decision Tree performance:
  - AUC ≈ 0.57

However:
- The difference is **not statistically significant**
- Cannot conclusively declare one model superior

### Interpretation
- The relationship in the data may be largely linear
- Decision Trees may require better feature engineering to compete effectively

---

## How to Run

### 1. Dataset
Ensure the dataset is in your project directory:
