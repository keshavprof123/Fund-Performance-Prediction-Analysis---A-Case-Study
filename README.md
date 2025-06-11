# Fund Performance Prediction Analysis

## 1. Introduction

This project aims to predict the performance of investment funds based on their attributes using machine learning classification models. A synthetic dataset was created to simulate realistic fund-level data, enabling testing and evaluation of various classification algorithms.

---

## 2. Dataset Overview

The dataset consists of **20 entries**, each representing a unique fund with the following features:

| Feature                   | Type        | Description                                                             |
|--------------------------|-------------|-------------------------------------------------------------------------|
| `fund_id`                | Categorical | Unique identifier for each fund                                        |
| `fund_type`              | Categorical | Type of fund: `Equity`, `Bond`, or `Hybrid`                            |
| `expense_ratio`          | Numerical   | Annual fee as a percentage of fund assets                              |
| `return_rate`            | Numerical   | The fund’s return rate                                                 |
| `asset_allocation`       | Categorical | Allocation strategy: `Domestic`, `International`, or `Both`            |
| `fund_manager_experience`| Numerical   | Years of experience of the fund manager                                |
| `target_variable`        | Categorical | Fund performance: `High`, `Medium`, or `Low` (derived from return rate)|

---

## 3. Data Generation and Preprocessing

### 🛠 Data Generation
- **Tools used**: Python, NumPy, Pandas
- **Purpose**: Simulate realistic fund characteristics for modeling

### Preprocessing Steps
- **Missing Value Check**: No missing values (`df.isnull().sum()`)
- **One-Hot Encoding**: Applied to categorical variables (`fund_type`, `asset_allocation`, and `target_variable`)
- **Feature Scaling**: Used `MinMaxScaler` on numerical features (`expense_ratio`, `return_rate`, `fund_manager_experience`)
- **Target Variable Re-definition**:
  - `High` → `return_rate > 0.1`
  - `Medium` → `0.05 < return_rate ≤ 0.1`
  - `Low` → `return_rate ≤ 0.05`

---

## 4. Model Development

The data was split into **80% training** and **20% testing** sets.

### Models Used:
-  **Random Forest (RF)**
-  **Support Vector Machine (SVM)**
-  **Gaussian Naive Bayes (NB)**
-  **Decision Tree (DT)**

---

## 5. Model Evaluation

Evaluation metrics:
- **Accuracy**
- **Precision (weighted)**
- **Recall (weighted)**
- **F1-score (weighted)**

### Performance Summary

| Model         | Accuracy | Precision | Recall | F1-score |
|---------------|:--------:|:---------:|:------:|:--------:|
| **Random Forest** | 0.7500   | 0.8333    | 0.7500 | 0.7778   |
| **SVM**           | 0.5000   | 0.4167    | 0.5000 | 0.4545   |
| **Naive Bayes**   | 0.7500   | 0.8333    | 0.7500 | 0.7778   |
| **Decision Tree** | 0.5000   | 0.4167    | 0.5000 | 0.4545   |

---

## 6. Key Findings

- **Random Forest** and **Naive Bayes** models achieved the highest accuracy and overall performance.
- **SVM** and **Decision Tree** underperformed in this synthetic setup.
- The small dataset size limits generalizability.

---

## 7. Limitations

-  **Synthetic data** may not capture real market dynamics.
-  **Limited sample size** (n=20) restricts model learning.
-  **Default model parameters** used—no hyperparameter tuning.
-  **No time-series data** included for fund performance trends.

---

## 8. Conclusion

Random Forest and Naive Bayes were the best-performing models for predicting fund performance on this dataset. However, due to the synthetic and small-scale nature of the data, caution is advised in generalizing these results.

---


