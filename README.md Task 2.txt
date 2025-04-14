# 📘 Sentiment Analysis on IMDB Movie Reviews

## 📌 Task Overview

**Task 2: Text Sentiment Analysis**  
This project focuses on building a sentiment analysis model using a dataset such as IMDB Reviews. The goal is to classify each movie review as **positive** or **negative** based on its content.

---

## 🧠 Steps Performed

### 1. 🧹 Text Preprocessing

We cleaned the text using several NLP steps:
- **Tokenization**: Splitting text into individual words.
- **Stopword Removal**: Removing common English stopwords using `nltk`.
- **Lemmatization**: Reducing words to their base/root form.
- **Reconstruction**: Joining the processed words back into full sentences.

Libraries used:  
```python
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer
```

### 2. ⚙️ Feature Engineering

We converted the processed text into numerical format using **TF-IDF (Term Frequency–Inverse Document Frequency)**:
```python
from sklearn.feature_extraction.text import TfidfVectorizer

vectorizer = TfidfVectorizer()
X_tfidf = vectorizer.fit_transform(df['processed_text'])
```

This resulted in a matrix where each row represents a review and each column a term weighted by its importance.

---

### 3. 🤖 Model Training

We trained two classifiers:
- **Logistic Regression**
- **Multinomial Naive Bayes**

```python
from sklearn.linear_model import LogisticRegression
from sklearn.naive_bayes import MultinomialNB

model_lr = LogisticRegression()
model_nb = MultinomialNB()
```

Data was split into training and testing sets using `train_test_split`.

---

### 4. 📊 Model Evaluation

We evaluated both models using:
- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**

#### ✅ Logistic Regression
- Accuracy: `89.64%`
- F1-score: `0.90` (Weighted Avg)

#### ✅ Naive Bayes
- Accuracy: `86.65%`
- F1-score: `0.87` (Weighted Avg)

Logistic Regression slightly outperformed Naive Bayes.

---

## ✅ Outcome

The final script:
- Preprocesses and cleans raw text
- Converts it into numerical format using TF-IDF
- Trains two classifiers to predict sentiment
- Outputs evaluation metrics including precision, recall, and F1-score

---

## 💪 Requirements

- Python 3.x
- pandas
- scikit-learn
- nltk

Install required libraries:
```bash
pip install pandas scikit-learn nltk
```

Download NLTK data (one-time):
```python
import nltk
nltk.download('stopwords')
nltk.download('wordnet')
nltk.download('omw-1.4')
```

---

## 📂 Example Directory Structure

```
.
├── sentiment_analysis.py
├── imdb_reviews.csv
├── README.md
```

