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



> 🎯 The model achieved **perfect detection** on the test data — this may indicate effective learning or possible overfitting.

---

## 🔍 Insights & Findings

- The Random Forest classifier performed exceptionally well in distinguishing fraudulent transactions when trained on a balanced dataset.
- Resampling with **SMOTE** was key to enabling the model to recognize rare fraud cases.
- PCA-transformed features retained useful variance for fraud pattern detection, even without original transaction context.

---

## ⚠️ Challenges & Solutions

| **Problem Faced** | **Description** | **Solution Taken** |
|-------------------|------------------|---------------------|
| **Class Imbalance** | Only 0.17% of the data was fraudulent, making the model biased toward majority class. | Applied **SMOTE** to generate synthetic examples of fraud for training. |
| **Overfitting Risk** | Perfect scores on test data could indicate overfitting. | Used **cross-validation** and kept test data strictly separate. Also, feature importance was reviewed. |
| **Uninterpretable Features** | PCA-transformed features (`V1–V28`) lack semantic meaning. | Focus was kept on performance metrics rather than interpretability. Additional tools (e.g., SHAP) could help. |
| **High Execution Time** | SMOTE and Random Forest on a large dataset increased processing time. | Limited feature space and used subset experiments for tuning. |

---

## ✅ Project Outcome

- Built an end-to-end machine learning pipeline to detect fraudulent transactions.
- Balanced the dataset with SMOTE and trained a **Random Forest** classifier.
- Achieved high performance (≈ 100%) on the test set.
- Includes a **command-line interface** to test real-time predictions.

---
