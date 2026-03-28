<div align="center">

<!-- Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,12,24&height=200&section=header&text=🏦%20CreditWise%20Loan%20Predictor&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=3%20ML%20Models%20|%20End-to-End%20Loan%20Approval%20Prediction&descAlignY=60&descAlign=50" width="100%"/>

<!-- Badges -->
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.4-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)](LICENSE)

</div>

---

## 📌 Project Overview

**CreditWise** is an end-to-end Machine Learning pipeline that predicts whether a loan application should be **approved or denied**, based on 20 financial and demographic features.

Three classification algorithms were trained and benchmarked using a **banking-first evaluation strategy** — prioritizing **Precision** over all other metrics, since a wrong approval in finance costs far more than a missed one.

---

## 📂 Dataset

| Property | Value |
|---|---|
| File | `loan_approval_data.csv` |
| Features | 20 (numerical + categorical) |
| Target | `Loan_Approved` (Yes / No) |
| Missing Values | Handled via SimpleImputer |
| Split | 80% train / 20% test |

**Key Features:**
`Applicant_Income` · `Coapplicant_Income` · `Credit_Score` · `DTI_Ratio` · `Savings` · `Collateral_Value` · `Loan_Amount` · `Loan_Term` · `Employment_Status` · `Marital_Status` · `Education_Level` · `Gender` · `Loan_Purpose` · `Property_Area` · `Employer_Category`

---

## 🔄 Pipeline Workflow

```
Raw Data → Missing Value Imputation → EDA → Feature Encoding → StandardScaler → Model Training → Evaluation
```

### 1️⃣ Data Preprocessing
- Separated **Numerical** and **Categorical** columns
- Handled missing values using **SimpleImputer**
  - `strategy="mean"` → Numerical columns
  - `strategy="most_frequent"` → Categorical columns

### 2️⃣ Exploratory Data Analysis (EDA)
- **Loan Approval Distribution** — Pie chart (Yes vs No)
- **Gender & Education** — Bar chart breakdowns
- **Income Analysis** — Histplots for Applicant & Co-applicant income
- **Multi-factor Boxplots** — Loan Amount, Credit Score, Savings, DTI Ratio vs Approval
- **Correlation Heatmap** — Reveals strongest predictors

### 3️⃣ Feature Encoding
```
Label Encoding   → Education_Level, Loan_Approved
One-Hot Encoding → Employment_Status, Marital_Status, Loan_Purpose,
                   Property_Area, Gender, Employer_Category
```

### 4️⃣ Feature Scaling
```
StandardScaler → Applied on X_train (fit_transform) and X_test (transform only)
```

### 5️⃣ Model Training & Evaluation

---

## 🤖 Models

### 1️⃣ Logistic Regression
```
StandardScaler → LogisticRegression()
```
- Linear decision boundaries with L2 regularization
- Strong baseline for binary classification
- Interpretable coefficients

### 2️⃣ K-Nearest Neighbors
```
StandardScaler → KNeighborsClassifier(n_neighbors=13)
```
- Distance-based: scaling is **essential**
- Optimal `k=13` found through experimentation
- Non-parametric — adapts to feature space shape

### 3️⃣ Gaussian Naive Bayes ⭐ Best Model
```
StandardScaler → GaussianNB()
```
- Probabilistic model assuming Gaussian feature distribution
- **Highest Precision, Recall, F1, and Accuracy** on this dataset
- Fast, scalable, and surprisingly powerful on financial data

---

## 📊 Results

| Model | Precision | Recall | F1 Score | Accuracy |
|:---|:---:|:---:|:---:|:---:|
| Logistic Regression | ✅ | ✅ | ✅ | ✅ |
| KNN (k=13) | ✅ | ✅ | ✅ | ✅ |
| 🏆 **Naive Bayes** | **Best** | **Best** | **Best** | **Best** |

> **Banking Evaluation Priority:** `Precision > Recall > F1 Score > Accuracy`
> In financial applications, minimizing false approvals is critical.

---

## 🔍 Key Insights

- 📈 **Credit Score** has a **+0.45 positive correlation** with loan approval
- 📉 **DTI Ratio** has a **-0.44 negative correlation** with loan approval
- These two features are the **strongest predictors** in the dataset
- **Naive Bayes** outperformed both tuned models — simpler beats complex on structured financial data

---

## 🗂️ Repository Structure

```
📦 creditwise-loan-predictor
 ┣ 📓 credit_wise_loan.ipynb      # Full notebook — preprocessing, EDA, models, evaluation
 ┣ 📄 loan_approval_data.csv      # Dataset (20 features, binary target)
 ┗ 📄 README.md                   # This file
```

---

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/ronakrajput8882/Creadit-Wise-Loan-Predictor.git
cd Creadit-Wise-Loan-Predictor

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Launch notebook
jupyter notebook credit_wise_loan.ipynb
```

---

## 🧠 Key Learnings

- **SimpleImputer** is a clean, pipeline-friendly approach to missing value handling
- **Label Encoding vs One-Hot Encoding** — choosing the right one avoids ordinal bias
- **StandardScaler** must be fit only on training data to prevent data leakage
- **Precision-first evaluation** is the correct strategy for banking/financial ML
- On structured datasets, **Naive Bayes** can beat more complex models

---

## 🛠️ Tech Stack

| Tool | Use |
|---|---|
| `pandas` | Data loading & manipulation |
| `numpy` | Numerical operations |
| `matplotlib` & `seaborn` | EDA visualizations & heatmaps |
| `scikit-learn` | Models, preprocessing, evaluation metrics |
| `Jupyter Notebook` | Interactive analysis & presentation |

---

<div align="center">

### Connect with me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ronakrajput8882)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/techwithronak)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ronakrajput8882)

*If you found this useful, please ⭐ the repo!*

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,12,24&height=100&section=footer" width="100%"/>

</div>
