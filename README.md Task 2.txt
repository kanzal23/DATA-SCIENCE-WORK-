# 📘 Sentiment Analysis on IMDB Movie Reviews

## 📌 Task Overview

**Task 2: Text Sentiment Analysis**  
This project focuses on building a sentiment analysis model using the IMDB Reviews dataset. The goal is to classify each movie review as **positive** or **negative** based on its content.

---

## 🧠 Steps Performed

### 1. 🧹 Text Preprocessing

We cleaned the text using several NLP steps:

- **Tokenization**: Splitting text into individual words.
- **Stopword Removal**: Removing common English stopwords using `nltk`.
- **Lemmatization**: Reducing words to their base/root form.
- **Reconstruction**: Joining the processed words back into full sentences.

**Libraries Used**:
```python
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer
2. ⚙️ Feature Engineering
We converted the processed text into numerical format using TF-IDF (Term Frequency–Inverse Document Frequency).

python
Copy
Edit
from sklearn.feature_extraction.text import TfidfVectorizer

vectorizer = TfidfVectorizer()
X_tfidf = vectorizer.fit_transform(df['processed_text'])
Each row represents a review, and each column represents a term weighted by its importance across the dataset.

3. 🤖 Model Training
We trained two classifiers:

Logistic Regression

Multinomial Naive Bayes

python
Copy
Edit
from sklearn.linear_model import LogisticRegression
from sklearn.naive_bayes import MultinomialNB

model_lr = LogisticRegression()
model_nb = MultinomialNB()
Data was split into training and testing sets using train_test_split.

4. 📊 Model Evaluation
Models were evaluated using:

Accuracy

Precision

Recall

F1-score

✅ Logistic Regression
Accuracy: 89.64%

F1-score: 0.90 (Weighted Avg)

✅ Naive Bayes
Accuracy: 86.65%

F1-score: 0.87 (Weighted Avg)

Logistic Regression slightly outperformed Naive Bayes.

🔍 Findings, Challenges & Solutions
🔎 Key Insights
TF-IDF vectorization effectively captured sentiment-related features.

Logistic Regression proved to be more robust than Naive Bayes for this dataset.

Preprocessing played a crucial role in improving performance.

⚠️ Problems & Resolutions
CHALLENGE                                   
Noisy and Inconsistent text              
Slow lemmatization 
Stopwords diluting features 
Overfitting risk 
High dimension in TF-IDF 

DESCRIPTION 
Reviews had HTML tags, special characters, and inconsistent casing
Lemmatizing all words slowed preprocessing 
Common words reduced accuracy 
Naive Bayes occasionally overfitted 
Resulted in a sparse, memory- heavy matrix 

SOLUTION
Cleaned using regex and standardized text 
Filtered non-informative tokens before lemmatization.
Removed stopwords using NLTK.
Used train_test_split with stratification and cross validation 
Applied Max_features parameter or dimensionality reduction as needed.

	                                                                                  ✅ Outcome
The final script:

Preprocesses and cleans raw text.

Converts it into numerical format using TF-IDF.

Trains two classifiers to predict sentiment.

Outputs performance metrics including accuracy, precision, recall, and F1-score.