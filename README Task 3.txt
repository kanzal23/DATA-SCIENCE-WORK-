# 🛡️ Credit Card Fraud Detection System

This project develops a **fraud detection system** using the [Credit Card Fraud Detection dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud). It utilizes machine learning to accurately detect fraudulent transactions based on transaction patterns.

---

## 📌 Project Overview

- **Goal**: Identify fraudulent credit card transactions using supervised machine learning.
- **Techniques Used**:
  - Data preprocessing and resampling (SMOTE)
  - Random Forest classifier
  - Evaluation metrics (Precision, Recall, F1-score)
  - Command-line prediction interface

---

## 🔍 Dataset

- The dataset contains transactions made by European cardholders in September 2013.
- Features are numerical, obtained using PCA (e.g., `V1`, `V2`, ..., `V28`) + `Time` and `Amount`.
- It is **highly imbalanced**: Only 0.17% of transactions are frauds.

---

## 🧪 Steps Performed

### 1. **Data Preprocessing**
- Split data into features (`X`) and target (`y`).
- Standardized `Amount` and `Time` values.
- Addressed class imbalance using **SMOTE (Synthetic Minority Oversampling Technique)**.

### 2. **Model Training**
- Trained a **Random Forest classifier** on the balanced dataset.
- Achieved perfect performance on the test data (Precision, Recall, F1-score ≈ 1.00).

### 3. **Model Evaluation**
- Evaluated model performance using:
  - **Precision**: How many predicted frauds were actual frauds.
  - **Recall**: How many actual frauds were detected.
  - **F1-score**: Harmonic mean of precision and recall.

#### ✅ Sample Output:
