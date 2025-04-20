# Parameter Optimization for SVM on Liver Disorder Dataset

This repository demonstrates how to optimize hyperparameters for a Support Vector Machine (SVM) regression model using the Liver Disorders Dataset from the BUPA Medical Research Ltd. database. The dataset contains results from blood tests that may indicate liver issues, often linked to excessive alcohol consumption.

---

##  Dataset Overview

- **Source:** BUPA Medical Research Ltd.
- **Instances:** 345
- **Features:** 5 (categorical, integer, and real-valued)
- **Target Variable:** Daily alcohol consumption (`drinks`)
- **Task Type:** Regression
- **Domain:** Health & Medicine

---

## 🎯 Objective

The project focuses on predicting daily alcohol intake using SVM regression, with an emphasis on optimizing hyperparameters to improve model performance.

---

## 🧪 Methodology

1. **Data Loading:**  
   Dataset is loaded using `ucimlrepo` and split into features (`X`) and target (`y`).

2. **Train-Test Splitting:**  
   For each of 10 random seeds, the data is split into 70% training and 30% testing sets.

3. **Simulating Low-Resource Training:**  
   From each training set, only 50 samples are selected to simulate scenarios with limited data.

4. **Random Search Optimization:**  
   - **Parameter Space:**
     - `kernel`: `'linear'`, `'poly'`, `'rbf'`, `'sigmoid'`
     - `C`: [0.1, 10.0]
     - `gamma`: [0.001, 1.0]
   - For each sample, 100 random combinations are tested.
   - Accuracy is computed on the test set for each configuration.
   - The best-performing configuration is logged.

5. **Visualization:**  
   The best sample across all runs is visualized using a convergence plot to show accuracy improvement over iterations.

---

## 📈 Convergence Plot

**File:** `convergence_plot.png`

- **X-axis:** Iteration number (logged every 10 iterations)
- **Y-axis:** Best accuracy achieved up to that point

This plot illustrates how the optimization process identifies better parameter sets over time, converging towards an optimal configuration.

---

## ✅ Conclusion

The convergence curve demonstrates successful hyperparameter tuning for SVM regression. The model achieves its best performance within a specific parameter range, effectively avoiding both underfitting and overfitting. Beyond this range, performance stabilizes, indicating convergence.

---
