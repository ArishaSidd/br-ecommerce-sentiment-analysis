# 🛒 Brazilian E-Commerce Review Sentiment Analysis

## Backstory & Scope
This project aims to analyze customer reviews from Brazil’s largest e-commerce platform and classify them into sentiment as **Positive**, **Neutral**, or **Negative** using **Natural Language Processing (NLP)** and **Machine Learning (ML)** techniques. It helps businesses understand customer satisfaction, trends, and pain points from real feedback.
---

## 📁 Dataset

- **Source**: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Files Used**:
  - `orders.csv`
  - `order_items.csv`
  - `order_reviews.csv`
  - `order_payments.csv`
  - `customers.csv`
  - `products.csv`
- **Join Key**: `order_id`

---

## 🔧 Tools & Libraries

- **Languages:** **Python**
- **NLP**: **NLTK**, **scikit-learn**, **wordcloud**
- **Models**: **Random Forest, Logistic Regression, SVM, XGBoostn**
- **Visualization: Seaborn, Matplotlib, Plotly**

---

## 🔄 Project Workflow

### 📥 Data Loading & Wrangling

- Loaded all relational CSV files using `pandas`.
- Merged datasets using `order_id` to form a single, unified dataframe.
- Filtered and retained relevant features like:
  - `review_comment_message`
  - `review_score`
  - `order_purchase_timestamp`
- Removed:
  - Duplicates
  - Missing review texts
  - Null values from review columns
  - Format timestamps

---

### 📊 Exploratory Data Analysis (EDA)

Explored the dataset using summary statistics and visualizations:
- **Review Score Distribution** – Majority of reviews are positive (4 & 5 stars).
- **Review Count Over Time** – Monthly trend showing volume of customer feedback.
- **Sentiment Distribution** – Balanced view of Positive, Neutral, and Negative reviews after labeling.
- **Word Clouds** – Visualized common keywords in Positive vs. Negative reviews.
- **Review Length** – Distribution of text length in characters and words.

---

### 🏷️ Sentiment Labeling Strategy

To convert numerical scores (1–5) into categorical sentiment:

| Review Score | Sentiment |
|--------------|-----------|
| 1 or 2       | Negative  |
| 3            | Neutral   |
| 4 or 5       | Positive  |

- Created a new column `sentiment_label` based on this mapping.
- Dropped rows with empty or `NaN` review messages.
- This labeled data became the target variable for NLP modeling.

---

### 3. NLP Preprocessing
- Lowercasing, removing punctuation
- Tokenization and stopword removal
- Lemmatization
- TF-IDF Vectorization

### 4. Model Building
- Logistic Regression
- Random Forest
- LinearSVC
- XGBoost

### 5. Evaluation Metrics
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrix
- Cross-validation
- Model Comparison

---



## ✅ Results

| Model                | Accuracy  |
|---------------------|-----------|
| Random Forest        | **0.8611** |
| Logistic Regression  | 0.8598    |
| LinearSVC            | 0.8581    |
| XGBoost              | 0.8556    |

🎯 **Best Model**: `Random Forest` with **86.11%** accuracy.

---



