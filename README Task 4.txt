# 🔍 Regression Models from Scratch

This project implements three popular regression models **from scratch** using **Python** and **NumPy**, without relying on machine learning libraries like `scikit-learn`.  
It is designed to deepen your understanding of how these models work internally by manually coding them.

---

## 📌 Project Overview

🧠 **Goal**: Understand and build regression models from the ground up.

📊 **Models Implemented**:
- **Linear Regression** (Normal Equation)
- **Random Forest Regressor**
- **XGBoost Regressor** (Simplified Boosting version)

📈 **Key Concepts**:
- Model construction
- Evaluation using real data
- Feature importance interpretation (for tree-based models)

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `RegressionModels.ipynb` | Main notebook: preprocessing, implementation, evaluation |
| `dataset.csv` | Dataset used for training and testing |
| `feature_importance.png` | Feature importance plot (Random Forest & XGBoost) |
| `.gitignore` | Ignore checkpoints and system files |
| `README.md` | You’re reading it! 📄 |

---

## 🧪 Project Workflow

### 1. 🧼 Data Preprocessing
- Normalized numerical features
- Encoded categorical features (if present)
- Handled missing values manually

### 2. 🧱 Model Implementations
Implemented all models manually using only NumPy:
- **Linear Regression**: Solved using the Normal Equation  
- **Random Forest**:
  - Implemented Decision Trees using recursive splitting
  - Used bootstrapped samples and aggregated predictions
- **XGBoost (Simplified)**:
  - Boosted multiple weak decision trees using gradient descent
  - Loss: Mean Squared Error (MSE)

### 3. 📊 Evaluation Metrics
Models evaluated using:
- **Root Mean Squared Error (RMSE)**
- **R² Score** (Coefficient of Determination)

### 4. 🌲 Feature Importance
- Calculated and visualized importance based on tree splits
- Used `matplotlib` to generate bar charts

---

## 📌 Key Insights & Findings

- **Linear Regression** performed well on linearly separable data, but struggled with non-linear patterns. It was fast but lacked flexibility compared to tree-based models.
- **Random Forest** and **XGBoost** showed superior performance on complex, non-linear relationships due to their ensemble nature. They also naturally handle feature interactions.
- **XGBoost** had the best performance with **lowest RMSE** and highest **R²** score, demonstrating the power of boosting in regression tasks.
- Tree-based models also provided useful insights into feature importance, which can guide decisions in feature engineering or domain-specific analysis.

---

## ⚠️ Challenges & Solutions

### 1. **Matrix Inversion Issues in Linear Regression**
   - **Problem**: The **Normal Equation** for Linear Regression required matrix inversion, which resulted in errors due to singular or near-singular matrices (especially when features are highly correlated).
   - **Solution**: 
     - Used **pseudo-inverse** (`np.linalg.pinv()`) instead of direct matrix inversion, which is more stable for ill-conditioned matrices.

### 2. **Tree Depth Handling in Random Forest**
   - **Problem**: When implementing decision trees, deep trees caused **stack overflows** or excessive computational time.
   - **Solution**: 
     - Limited the **maximum depth** of the trees and set a **minimum number of samples per split** to prevent overfitting and reduce computational complexity.

### 3. **Boosting Complexity in XGBoost**
   - **Problem**: Implementing **gradient boosting** for XGBoost manually was tricky. The boosting loop needed to adjust predictions step-by-step, and the gradient calculation for boosting was hard to debug.
   - **Solution**: 
     - Simplified the boosting loop and added **debugging outputs** for each iteration, logging residuals and learning rate adjustments.
     - Used a smaller **learning rate** to make gradual improvements and prevent large swings in prediction errors.

### 4. **Manual Evaluation**
   - **Problem**: Without libraries like `scikit-learn`, calculating **RMSE** and **R² Score** manually seemed tedious.
   - **Solution**: 
     - Wrote custom **RMSE** and **R² functions** using **NumPy** to handle the model evaluation.

### 5. **Handling Missing Data**
   - **Problem**: The dataset had missing values in certain features.
   - **Solution**: 
     - Implemented **mean imputation** for numerical features and **mode imputation** for categorical features, ensuring no missing values before training the models.

---

## ✅ Results Snapshot

| Model | RMSE | R² Score |
|-------|------|----------|
| Linear Regression | 18.32 | 0.76 |
| Random Forest | 7.81 | 0.92 |
| XGBoost | 6.95 | 0.94 |

> 🏆 **XGBoost outperformed** the other models, with the **lowest RMSE** and highest **R² Score**, demonstrating the power of boosting in regression tasks.

---

## 📌 Visualizations

- **Feature Importance**: For Random Forest and XGBoost models, visualized which features were most influential in making predictions. This helped understand the underlying relationships and gave insights into feature engineering.

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
cd tasks
