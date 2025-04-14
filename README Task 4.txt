# 🔍 Regression Models from Scratch

## 📌 Project Overview

This project focuses on implementing three machine learning regression models **from scratch** using Python and NumPy. The models include:

- **Linear Regression**
- **Random Forest Regressor**
- **XGBoost Regressor (simplified version)**

The goal is to understand model construction, evaluate performance, and interpret feature importance.

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `RegressionModels.ipynb` | Main notebook containing all steps: preprocessing, model implementation, evaluation |
| `dataset.csv` | Dataset used for training and evaluation |
| `feature_importance.png` | Visualization showing feature importance (from tree-based models) |
| `.gitignore` | Lists files/folders to exclude from version control |
| `README.md` | This file – documentation for the project |

---

## 🧪 Project Steps

1. **Data Preprocessing**
   - Normalization of numerical features
   - Encoding of categorical features (if any)

2. **Model Implementation**
   - Manual implementation (without sklearn) of:
     - Linear Regression (using Normal Equation)
     - Decision Trees (for Random Forest)
     - Ensemble logic for Random Forest
     - Boosting logic for XGBoost

3. **Model Evaluation**
   - Metrics used: **RMSE** and **R² Score**
   - Comparison of all three models

4. **Feature Importance**
   - Visualized importance for tree-based models

---

## ⚙️ How to Run This Project

### Option 1: Run on Google Colab (Recommended)
1. Open the notebook `RegressionModels.ipynb` in Google Colab
2. Run each cell step-by-step
3. Make sure your dataset (e.g., `dataset.csv`) is uploaded to the Colab environment

### Option 2: Run Locally
1. Clone the repository:
```bash
git clone https://github.com/yourusername/tasks.git
