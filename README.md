# Logistic Regression with Imbalanced Data

---

## Overview

This project explores predictive modeling of student enrollment decisions using **logistic regression**, with a focus on addressing **class imbalance** in the dataset. The original dataset includes demographic and behavioral information for over 18,000 student applications. The target variable `enrollment` is highly imbalanced, with significantly more students not enrolling than enrolling.

To address this, the following three strategies are implemented and compared:

- **Undersampling** the majority class  
- **SMOTE** (Synthetic Minority Oversampling Technique)  
- **Class weighting** in logistic regression

---

## Files

- `modelling_logistic_regression.qmd` – Quarto source file
- `modelling_logistic_regression.html` – Rendered HTML report (self-contained)
- `enrollment3.xlsx` – Input dataset (external Excel file)

---

## Tools & Libraries

The analysis was conducted in R using:

- `tidymodels`, `caret`, `themis`, `DMwR2`, `ROSE`
- `readxl`, `rsample`, `janitor`, `glmnet`, `ggplot2`, `here`

---

##  Methodology

1. **Data Preprocessing**
   - Cleaned and recoded variables
   - Converted target to factor
   - Stratified train-test split (70/30)

2. **Imbalance Strategies**
   - **Undersampling:** Reduced majority class to match the minority
   - **SMOTE:** Generated synthetic samples for the minority class
   - **Weighted Logistic Regression:** Applied class weights inversely proportional to class sizes

3. **Evaluation Metrics**
   - Accuracy
   - Sensitivity / Specificity
   - Precision
   - F1 Score
   - Kappa

---

## Model Performance

| Technique           | Accuracy | Balanced Accuracy | Sensitivity | Specificity | Precision | F1 Score |
|---------------------|----------|-------------------|-------------|-------------|-----------|----------|
| Undersampling       | 82.2%    | 80.7%             | 83.1%       | 78.3%       | 94.4%     | —        |
| SMOTE               | **82.7%**| **80.7%**         | **83.9%**   | 77.4%       | 94.2%     | **88.8%**|
| Weighted Regression | 82.3%    | ~80.9%            | 83.7%       | **78.0%**   | **94.3%** | ~88.2%   |

---

## Insights

- **SMOTE** delivered the best F1 score and overall model balance.
- **Class weighting** was nearly as effective, without generating synthetic data.
- **Undersampling** is easy to implement but sacrifices majority class information.

---
## Author

**Anna Ceslavska**  
Senior at Lake Forest College  
Majors: Data Science and Economics  
