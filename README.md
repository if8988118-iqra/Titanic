<<<<<<< HEAD
# Titanic
=======
# 🚢 Titanic — Complete Machine Learning Lifecycle

A complete beginner-friendly Machine Learning project on the famous **Titanic dataset** from Kaggle. This notebook walks through every stage of the ML lifecycle — from raw data to a trained model — with clear code, observations, and explanations.

---

## 📋 Project Overview

| | |
|---|---|
| **Dataset** | Titanic — Machine Learning from Disaster |
| **Source** | [Kaggle](https://www.kaggle.com/competitions/titanic) |
| **Goal** | Predict whether a passenger survived or not |
| **Type** | Binary Classification (0 = Died, 1 = Survived) |
| **Algorithm** | Logistic Regression |
| **Language** | Python |
| **Tools** | Jupyter Notebook, Pandas, Seaborn, Scikit-learn |

---

## 🗺️ ML Lifecycle — Stages Covered

| # | Stage | Emoji | Status |
|---|---|---|---|
| 1 | Problem Definition | 🎯 | ✅ Done |
| 2 | Data Collection | 📦 | ✅ Done |
| 3 | Data Cleaning & Preprocessing | 🧹 | ✅ Done |
| 4 | Exploratory Data Analysis (EDA) | 📊 | ✅ Done |
| 5 | Feature Engineering & Selection | ⚙️ | ✅ Done |
| 6 | Model Selection & Building | 🤖 | ✅ Done |
| 7 | Model Evaluation | 📈 | ✅ Done |

---

## 📁 Project Structure

```
Titanic_Complete_Lifecycle/
│
├── Titanic_Complete_Lifecycle.ipynb   ← Main notebook
├── train.csv                          ← Titanic dataset
├── README.md                          ← This file
```

---

## 🎯 Stage 1 — Problem Definition

- **Goal:** Predict survival of Titanic passengers
- **Type:** Binary Classification
- **Target Variable:** `Survived` (0 = Died, 1 = Survived)
- **Success Metric:** Accuracy score

---

## 📦 Stage 2 — Data Collection

- Dataset loaded from **Kaggle / Seaborn**
- **891 rows** and **12 columns**
- Key columns: PassengerId, Survived, Pclass, Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked

---

## 🧹 Stage 3 — Data Cleaning & Preprocessing

### 3.1 — Data Cleaning:
| Step | Action | Result |
|---|---|---|
| Duplicates | Checked and removed | 0 duplicates found |
| Irrelevant columns | Dropped Name, Ticket, Cabin | 12 → 9 columns |
| Missing values — Embarked | Dropped 2 null rows | 891 → 889 rows |
| Missing values — Age | Filled with mean | 177 nulls → 0 |
| Datatype correction | Survived, Pclass → category | Fixed |
| Outliers | Detected using IQR + Boxplot | Handled |

### 3.2 — Preprocessing:
- Inspected data structure
- Statistical summary generated
- Outliers visualized using boxplots
- Correlation analysis performed
- Features and target variable separated

---

## 📊 Stage 4 — Exploratory Data Analysis (EDA)

### Univariate Analysis:
- Age Distribution — slightly right skewed
- Fare Distribution — heavily right skewed
- More passengers died (0) than survived (1)
- Most passengers were in 3rd class

### Bivariate Analysis:
- Females survived much more than males
- 1st class passengers survived more than 3rd class
- Higher fare = better survival rate
- Age had small effect on survival

### Multivariate Analysis:
- Correlation heatmap of all columns
- Age + Sex + Survived combined
- Pclass + Fare + Survived combined

---

## ⚙️ Stage 5 — Feature Engineering & Selection

### 🔤➡️🔢 Encoding:
| Column | Method | Result |
|---|---|---|
| Sex | Label Encoding | male=0, female=1 |
| Embarked | One Hot Encoding | Embarked_C, Embarked_Q, Embarked_S |

### ⚖️ Scaling:
| Column | Method | Result |
|---|---|---|
| Age | Min-Max Scaler | 0.0 to 1.0 |
| SibSp | Min-Max Scaler | 0.0 to 1.0 |
| Parch | Min-Max Scaler | 0.0 to 1.0 |
| Fare | Standard Scaler | mean=0, std=1 |

### 🎯 Feature Selection — Correlation Heatmap Results:
| Column | Correlation with Survived | Decision |
|---|---|---|
| Sex | 0.55 | 🔴 Strong — Keep ✅ |
| Fare | 0.27 | 🟠 Moderate — Keep ✅ |
| Embarked_C | 0.16 | 🟡 Weak — Keep ✅ |
| Pclass | -0.37 | 🔵 Strong Negative — Keep ✅ |
| Embarked_S | -0.15 | 🟡 Weak Negative — Keep ✅ |
| PassengerId | -0.02 | ⚪ No relation — Remove ❌ |
| Age | -0.03 | ⚪ No relation — Remove ❌ |
| SibSp | -0.03 | ⚪ No relation — Remove ❌ |

**Final Features Used:**
```python
X = ['Pclass', 'Sex', 'Fare', 'Parch', 'Embarked_C', 'Embarked_Q', 'Embarked_S']
y = ['Survived']
```

---

## 🤖 Stage 6 — Model Selection & Building

- **Algorithm Selected:** Logistic Regression
- **Why Logistic Regression?** Target variable is binary (0 or 1) — Logistic Regression is best for binary classification
- Train/Test Split: 80% training, 20% testing

---

## 📈 Stage 7 — Model Evaluation

- Accuracy Score
- Confusion Matrix
- Classification Report

---

## 🛠️ Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.preprocessing import MinMaxScaler, StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix
```

---

## ▶️ How to Run

1. Clone this repository
```bash
git clone https://github.com/your-username/Titanic-ML-Lifecycle.git
```

2. Install required libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Open Jupyter Notebook
```bash
jupyter notebook Titanic_Complete_Lifecycle.ipynb
```

4. Run all cells from top to bottom

---

## 👩‍💻 Author

**Iqra**
Beginner ML Student | Pakistan
Learning Machine Learning step by step 🚀

---

## 📚 References

- Kaggle Titanic Dataset: kaggle.com/competitions/titanic
- Pandas Documentation: pandas.pydata.org
- Scikit-learn Documentation: scikit-learn.org
- Seaborn Documentation: seaborn.pydata.org
- GeeksforGeeks — ML Lifecycle (2026)
>>>>>>> 7a1ef20 (ML Project)
