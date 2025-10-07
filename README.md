# ML Imputation of Survey Data: Oxford Internet Survey Dataset

This project explores whether individual survey responses on the prioritization of the environment versus the economy can be accurately **imputed** from other survey items using machine learning models. It evaluates multiple algorithms for imputing both binary and continuous responses, focusing on distributional preservation and bias control in survey inference.

---

## Overview

The analysis uses the **Oxford Internet Survey** dataset to test whether pro-environment or pro-economy preferences can be predicted from other observed responses.  
Data from the **2017** survey are used for training and validation, and **2019** responses serve as an out-of-sample test set — ensuring **temporal generalization**.

Three outcome formats were modeled:
1. **Binary** (environment vs economy)
2. **Multiclass** (0–3, 4–6, 7–10)
3. **Continuous** (0–10 scale)

The study evaluates **Regularized Regression**, **Random Forest**, and **LightGBM** models, applying random forest imputation (`missRanger`) for missing predictors and optimizing thresholds by **Macro F1** to balance pro-environment and pro-economy classifications.

---

## Skills Used

- Supervised machine learning (Regularized Regression, Random Forest, LightGBM)  
- Missing data handling and imputation (`missRanger`)  
- Model evaluation across outcome types (binary, multiclass, continuous)  
- Temporal validation for out-of-sample generalization  
- Feature selection and interpretability analysis  
- Statistical metrics: Macro F1, Recall, Specificity, MAE, RMSE, R²  
- Programming in **R** (`tidyverse`, `lightgbm`, `caret`, `missRanger`)  

---

## Key Results

- **Binary models performed best overall**:  
  LightGBM (Macro F1 = 0.63) and Regularized Regression (0.62) achieved the highest balance between Recall (0.96 for pro-environment) and Specificity (0.23–0.57 for pro-economy).  

- **Continuous outcome models less reliable**:  
  Best model reached MAE = 1.75 but showed low R² = 0.16 and unstable calibration across the 0–10 range.  

- **Multiclass models exhibited imbalance**:  
  LightGBM achieved Macro F1 = 0.60, but the pro-economy class underperformed (F1 = 0.12), limiting minority-class recovery.

---

## Contributions

- **Developed** an end-to-end ML imputation pipeline for survey data using R.  
- **Demonstrated** that reducing survey length to 17–25 key questions retains strong predictive performance (Macro F1 ≈ 0.63).  
- **Quantified** model bias: strong recovery of majority (pro-environment) responses but under-representation of minority (pro-economy) views.  
- **Benchmarked** multiple model classes across binary, multiclass, and continuous formulations with temporal validation.  
- **Highlighted** the trade-off between efficiency and representativeness in predictive imputation for social science surveys.

---

