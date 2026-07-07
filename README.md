# DevelopersHub Data Science & Analytics Internship

## Tasks Completed

### Task 1 - Exploring and Visualizing the Iris Dataset
- **Dataset:** Iris Dataset (150 rows, 5 columns, 3 species)
- **Approach:** Loaded dataset, explored structure, created visualizations
- **Visualizations:** Scatter Plot, Histogram, Box Plot
- **Key Insight:** Setosa species is clearly distinct based on petal measurements

### Task 2 - Credit Risk Prediction
- **Dataset:** Loan Prediction Dataset (614 rows, 13 columns)
- **Approach:** Data cleaning, EDA, Logistic Regression
- **Accuracy:** 78.86%
- **Key Insight:** Credit history and education are strongest predictors

### Task 3 - Customer Churn Prediction
- **Dataset:** Churn Modelling Dataset (10,000 rows, 14 columns)
- **Approach:** Label Encoding, EDA, Logistic Regression
- **Accuracy:** 79.90%
- **Key Insight:** Tenure and IsActiveMember are strongest churn predictors

- ## Task 4 - Predicting Insurance Claim Amounts
- **Dataset:** Medical Cost Personal Dataset (1338 rows, 7 columns)
- **Model:** Linear Regression
- **Key Findings:**
  - Smoking is the strongest factor (correlation: 0.79)
  - Age and BMI also impact charges
- **Results:**
  - MAE: $4,186.51
  - RMSE: $5,799.59
  - R² Score: 0.7833

## Tools Used
- Python, Jupyter Notebook
- pandas, numpy, matplotlib, seaborn, scikit-learn

# Task 5: Personal Loan Acceptance Prediction
## DevelopersHub Corporation - Data Science & Analytics Internship

## 📌 Task Objective
Predict which customers are likely to accept a personal loan offer using the Bank Marketing Dataset (UCI Machine Learning Repository).

---

## 🔍 Approach

### 1. Data Exploration
- Analyzed key features: age, job, marital status, education, balance
- Checked for missing values and duplicates
- Visualized target variable distribution

### 2. Data Preprocessing
- Applied Label Encoding on categorical columns (job, marital, education, etc.)
- Split dataset: 80% training, 20% testing

### 3. Models Used
- **Logistic Regression**
- **Decision Tree Classifier** (max_depth=5)

---

## 📊 Results & Insights

| Model | Accuracy |
|-------|----------|
| Logistic Regression | 88.40% |
| Decision Tree | 87.62% |

### Key Findings:
- **Call duration** is the most important feature
- **Retired and student** customers have higher acceptance rates
- **Single customers** accept loans more than married ones
- Customers **without existing loans** are more likely to accept

---

## 🛠️ Libraries Used
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

---

## Task 6 - Term Deposit Prediction

- **Dataset:** Bank Marketing Dataset (term deposit subscription data)
- **Approach:** Data cleaning, EDA, classification model (Logistic Regression)
- **Accuracy:** XX%
- **Key Insight:** [yahan apna key finding likho]
