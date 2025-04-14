# Titanic Dataset - Exploratory Data Analysis (EDA)

This project performs a detailed exploratory data analysis (EDA) on the Titanic dataset. The goal is to uncover insights, clean and prepare the data for potential predictive modeling, and visualize important patterns.

## 📁 Dataset

- **File Name:** `tested.csv`  
- **Source:** Titanic dataset (commonly used for classification tasks)  
- **Target Variable (Optional):** `Survived` (0 = No, 1 = Yes)  

## 📊 Key Steps in EDA

### ✅ 1. Data Loading
- Read the dataset using `pandas`.

### 🔍 2. Initial Exploration
- View dataset shape and column types.
- Display first few rows using `.head()`.
- Use `.info()` and `.describe()` for structure and summary stats.

### ❗ 3. Missing Value Handling
- Identify missing values with `df.isnull().sum()`.
- Fill missing numeric values with median.
- Fill missing categorical values with mode.

### 🧹 4. Duplicate Detection
- Check for duplicates using `df.duplicated().sum()`.

### 🚨 5. Outlier Detection and Handling
- Use the Interquartile Range (IQR) method to detect outliers.
- Visualize with boxplots.
- Cap or remove outliers depending on context.

### 📈 6. Data Visualization
- **Bar Charts** for categorical variables (e.g., `Sex`, `Embarked`).
- **Histograms** for numeric variables (e.g., `Age`, `Fare`).
- **Boxplots** to identify outliers.
- **Correlation Heatmap** to understand relationships between numeric features.

## 📦 Dependencies

- `pandas`  
- `matplotlib`  
- `seaborn`  

Install using pip if necessary:

```bash
pip install pandas matplotlib seaborn
```

## 💡 Insights to Explore (Examples)

- Which group had higher survival rates? (e.g., gender, passenger class)
- How does age or fare affect survival?
- Are there correlations between numerical features?

## 📁 Output

- Cleaned dataset with missing values handled
- Outliers managed
- Visualizations to support data understanding
- Heatmap showing correlation between numerical variables

## 📝 Findings and Insights

- 🚺 **Females had a significantly higher survival rate** than males.
- 🎟️ **Passengers in 1st class survived at a higher rate** compared to 2nd and 3rd class.
- 👶 **Children and young adults had better survival rates**, suggesting priority during evacuation.
- 💵 **Fare is positively correlated with survival**, likely due to socio-economic status.
- 🧳 **Embarked location (C, Q, S)** showed slight variation in survival but not strongly predictive.
- 🔢 **Age and Fare have outliers**, which were managed using IQR-based capping.
- 🧼 The dataset had missing values in columns like `Age` and `Embarked`, which were handled through imputation.

## 🛠️ Optional Next Steps

- Feature engineering (e.g., FamilySize, Title extraction)
- Encoding categorical features
- Training ML models (e.g., Logistic Regression, Random Forest)
