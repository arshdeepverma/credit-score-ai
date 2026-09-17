# 💳 CreditScore AI — Explainable Credit Risk Classifier

**An academic FinTech & AI project for understanding credit risk using Machine Learning and Explainable AI concepts.**

CreditScore AI combines an **illustrative credit scoring engine** with a **Machine Learning-based default risk classifier** to demonstrate how customer financial information can be analyzed and used for credit-risk prediction.

> ⚠️ **Disclaimer:** This project is developed strictly for academic and educational purposes. The dataset is synthetic, and the credit score formula is illustrative. This system should not be used for real-world lending, financial decisions, or credit approval.

---

## 🚀 Project Overview

Credit risk assessment involves analyzing multiple financial and personal factors to estimate the likelihood that a customer may default on a loan.

This project demonstrates an end-to-end credit risk analytics workflow:

**Customer Data → Data Understanding → EDA → Illustrative Credit Score → Data Preprocessing → Logistic Regression → Risk Prediction → Model Evaluation → Explainability**

The project focuses on understanding both the **financial scoring logic** and the **Machine Learning approach** behind credit-risk classification.

---

## 🎯 Objectives

The main objectives of this project are to:

* Understand and explore customer credit data
* Perform Exploratory Data Analysis (EDA)
* Develop an illustrative credit score calculation
* Preprocess numerical and categorical features
* Train a Logistic Regression classification model
* Predict customer default risk
* Evaluate model performance using multiple metrics
* Understand which features influence model predictions
* Demonstrate basic Explainable AI (XAI) concepts
* Predict risk for new customers

---

## 🧠 Machine Learning Model

### Logistic Regression

The project uses **Logistic Regression** as its primary Machine Learning classification algorithm.

The model predicts whether a customer belongs to:

* `0` → Lower Default Risk
* `1` → Higher Default Risk

The model uses:

* Numerical feature standardization
* One-hot encoding for categorical features
* Balanced class weights
* Probability-based risk prediction

Example model configuration:

```python
LogisticRegression(
    class_weight="balanced",
    max_iter=2000,
    random_state=42
)
```

### Why Logistic Regression?

Logistic Regression is suitable for this project because it is designed for binary classification and provides interpretable coefficients and probability estimates.

Its coefficients can also be analyzed to understand how different features contribute to the predicted risk.

---

## 📊 Illustrative Credit Score

In addition to the Machine Learning model, the project contains an **illustrative credit score engine**.

The score considers factors such as:

* Late payments
* Debt-to-income ratio
* Credit utilization
* Credit history
* Number of credit accounts
* Loan-to-income relationship

The resulting score is mapped into illustrative risk categories such as:

| Score Range | Category                |
| ----------- | ----------------------- |
| 750+        | Excellent / Lower Risk  |
| 700–749     | Good / Lower Risk       |
| 650–699     | Fair / Moderate Risk    |
| 600–649     | Poor / Higher Risk      |
| Below 600   | Very Poor / Higher Risk |

**Important:** These ranges and calculations are created for demonstration purposes and do not represent an official credit bureau scoring system.

---

## 📈 Exploratory Data Analysis

The project performs EDA to understand patterns and relationships within the dataset.

Visualizations include:

* Default risk distribution
* Debt-to-income vs. credit utilization
* Late payments across risk categories
* Distribution and descriptive statistics of financial variables

EDA helps identify patterns in customer financial behavior before building the Machine Learning model.

---

## 🛠️ Data Preprocessing

The Machine Learning pipeline includes:

### Numerical Features

Numerical variables are standardized using:

```python
StandardScaler()
```

### Categorical Features

Categorical variables are converted using:

```python
OneHotEncoder(handle_unknown="ignore")
```

### Feature Engineering

A derived feature is also created:

```text
Loan-to-Income Ratio
```

This represents the relationship between the customer's loan amount and annual income.

---

## 📋 Dataset

The project uses a **synthetic dataset** containing 1,200 customer records.

### Features

| Feature                | Description               |
| ---------------------- | ------------------------- |
| `age`                  | Customer age              |
| `annual_income`        | Annual income             |
| `employment_years`     | Years of employment       |
| `loan_amount`          | Requested loan amount     |
| `loan_term`            | Loan repayment term       |
| `credit_history_years` | Length of credit history  |
| `credit_accounts`      | Number of credit accounts |
| `late_payments`        | Number of late payments   |
| `debt_to_income`       | Debt-to-income ratio      |
| `credit_utilization`   | Credit utilization ratio  |
| `savings_balance`      | Customer savings balance  |
| `existing_loans`       | Number of existing loans  |
| `education_level`      | Education category        |
| `employment_type`      | Employment category       |
| `home_ownership`       | Home ownership status     |
| `default_risk`         | Target variable           |

### Target Variable

```text
0 = Lower Default Risk
1 = Higher Default Risk
```

---

## 🔍 Model Evaluation

The Logistic Regression model is evaluated using:

* Classification Report
* Precision
* Recall
* F1-Score
* Confusion Matrix
* ROC-AUC Score
* ROC Curve

These metrics provide different perspectives on how well the classifier distinguishes between lower- and higher-risk customers.

---

## 💡 Explainable AI (XAI)

A basic XAI approach is included using the **Logistic Regression coefficients**.

The coefficients help identify which features have stronger positive or negative relationships with the model's predicted default-risk class.

This makes the model more interpretable than treating the prediction as a completely unexplained output.

> Note: A coefficient represents the model's learned association within this synthetic dataset and should not be interpreted as a causal relationship.

---

## 👤 New Customer Risk Prediction

The notebook also demonstrates how the trained model can be used to analyze a new customer's information.

The system generates:

* Predicted risk class
* Probability of higher default risk

Example concept:

```text
Customer → Preprocessing → Logistic Regression
                         ↓
                Risk Probability
                         ↓
              Lower / Higher Risk
```

---

## 🧰 Tech Stack

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Google Colab**
* **Jupyter Notebook**

---

## 📁 Project Structure

```text
credit-score-ai/
│
├── CreditScore_AI_Colab.ipynb
├── README.md
│
└── data/
    └── credit_data.csv
```

---

## ▶️ How to Run the Project

### 1. Clone or download the repository

```bash
git clone <your-repository-url>
```

### 2. Open the notebook

Open:

```text
CreditScore_AI_Colab.ipynb
```

using **Google Colab**.

### 3. Add the dataset

Upload:

```text
data/credit_data.csv
```

to the Colab environment.

### 4. Run the notebook

Run all cells from top to bottom.

The notebook will:

1. Load the dataset
2. Explore the data
3. Perform EDA
4. Calculate illustrative credit scores
5. Preprocess the data
6. Train the Logistic Regression model
7. Evaluate the model
8. Explain model coefficients
9. Predict risk for new customers

---

## 📚 Key Learning Outcomes

Through this project, the following concepts are demonstrated:

* Data cleaning and exploration
* Exploratory Data Analysis
* Feature engineering
* Numerical feature scaling
* Categorical encoding
* Binary classification
* Logistic Regression
* Class imbalance handling
* Model evaluation
* ROC-AUC analysis
* Confusion matrices
* Probability-based predictions
* Basic Explainable AI

---

## 🔮 Future Improvements

The project can be extended by adding:

* Random Forest and XGBoost comparisons
* SHAP-based explainability
* Hyperparameter tuning
* Cross-validation
* Advanced feature selection
* Model calibration
* Interactive dashboards
* Streamlit deployment
* Real-world anonymized datasets
* More advanced credit-risk modeling techniques

---

## ⚠️ Disclaimer

This project is intended **only for academic and educational purposes**.

The dataset is synthetic and does not represent real customers. The illustrative credit score calculation is not based on any official credit bureau methodology.

The predictions generated by this project should **not** be used for loan approval, credit scoring, financial decisions, or any other high-impact decision involving real individuals.

---

## 👨‍💻 Author

**Arshdeep Verma**

Academic Project — FinTech & Artificial Intelligence

---

⭐ If you found this project useful, consider giving the repository a star!
