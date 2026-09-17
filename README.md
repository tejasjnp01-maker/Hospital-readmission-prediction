# 🏥 Hospital Readmission Prediction

## 📌 Project Overview

This project focuses on predicting whether a patient will be **readmitted to the hospital within 30 days** using Machine Learning.

The project uses **Logistic Regression with L2 Regularization** to perform binary classification on patient records. The model is evaluated using **ROC-AUC** and the clinical impact of **False Negatives and False Positives** is discussed.

---

## 🎯 Objective

The main objective is to:

* Predict 30-day hospital readmission risk.
* Apply Logistic Regression for binary classification.
* Use **L2 Regularization** to reduce overfitting.
* Handle missing values in patient records.
* Evaluate the model using **ROC-AUC**.
* Understand the clinical cost of False Negatives and False Positives.

---

## 📊 Dataset

The dataset used in this case study is:

`hospital_readmission.csv`

### Dataset Size

* **Rows:** 32,300
* **Columns:** 10

### Features

| Feature               | Description                      |
| --------------------- | -------------------------------- |
| `age`                 | Patient age                      |
| `length_of_stay_days` | Number of days spent in hospital |
| `num_diagnoses`       | Number of diagnoses              |
| `num_medications`     | Number of medications            |
| `prev_admissions`     | Previous hospital admissions     |
| `glucose_level`       | Patient glucose level            |
| `bmi`                 | Body Mass Index                  |
| `has_diabetes`        | Whether the patient has diabetes |
| `discharge_type`      | Type of discharge                |
| `readmitted_30days`   | Target variable                  |

### Target Variable

`readmitted_30days`

* `0` → Patient was **not readmitted** within 30 days
* `1` → Patient was **readmitted** within 30 days

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

### 1. Missing Value Handling

Numerical missing values were handled using the **median**.

Categorical missing values were handled using the **mode**.

### 2. Feature Scaling

`StandardScaler` was used to standardize numerical features.

Scaling is particularly useful when using regularization because features should be on comparable scales.

---

## 🤖 Machine Learning Model

### Logistic Regression

Logistic Regression is used because the target variable has two possible outcomes:

```text
0 → Not Readmitted
1 → Readmitted
```

The model estimates the probability of readmission using the sigmoid function:

$$
P(y=1|X)=\frac{1}{1+e^{-z}}
$$

where:

$$
z=\beta_0+\beta_1X_1+\beta_2X_2+...+\beta_nX_n
$$

---

## 🔒 L2 Regularization

L2 Regularization was applied to reduce overfitting.

The objective function can be represented as:

$$
Loss = LogLoss + \lambda\sum\beta_j^2
$$

The regularization term penalizes large model coefficients.

### Benefits

* Reduces overfitting.
* Controls large coefficients.
* Improves model generalization.
* Works well when multiple features contribute to prediction.

---

## 📈 Model Evaluation

The model is evaluated using **ROC-AUC**.

### ROC Curve

The ROC curve represents the relationship between:

* **True Positive Rate (TPR)**
* **False Positive Rate (FPR)**

### AUC

AUC represents how well the model distinguishes between patients who are readmitted and those who are not.

Generally:

```text
AUC = 1.0  → Perfect discrimination
AUC = 0.5  → Random-level discrimination
```

---

## ⚕️ Clinical Impact

In hospital readmission prediction, both types of errors are important.

### ❌ False Negative

A False Negative occurs when:

```text
Actual → Readmitted
Predicted → Not Readmitted
```

This can be clinically important because a high-risk patient may not receive additional monitoring or follow-up.

### ⚠️ False Positive

A False Positive occurs when:

```text
Actual → Not Readmitted
Predicted → Readmitted
```

This can result in unnecessary monitoring, follow-up, or use of healthcare resources.

Therefore, the classification threshold should be considered carefully rather than relying only on accuracy.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Logistic Regression
* L2 Regularization
* StandardScaler
* ROC-AUC
* Confusion Matrix

---

## 📁 Project Structure

```text
Hospital-Readmission-Prediction/
│
├── hospital_readmission.csv
├── Hospital_Readmission_Prediction.ipynb
├── README.md
└── images/
    └── roc_curve.png
```

---

## 🔄 Machine Learning Workflow

```text
Patient Dataset
       ↓
Data Cleaning
       ↓
Missing Value Handling
       ↓
Feature Selection
       ↓
Feature Scaling
       ↓
Train-Test Split
       ↓
Logistic Regression
       ↓
L2 Regularization
       ↓
Prediction
       ↓
ROC-AUC Evaluation
       ↓
Clinical Error Analysis
```

---

## 💡 Key Learning Outcomes

Through this case study, I learned:

* How to prepare healthcare-related tabular data.
* How Logistic Regression works for binary classification.
* How L2 Regularization helps control overfitting.
* Why feature scaling is important.
* How to evaluate a classification model using ROC-AUC.
* The difference between False Positives and False Negatives.
* Why model evaluation in healthcare should consider the cost of different errors.

---

## 👨‍💻 Author

**Tejas Mishra**

B.Tech Student
Interested in Machine Learning, AI and Technology.

---

## ⭐ Conclusion

This project demonstrates how **Logistic Regression with L2 Regularization** can be used to predict 30-day hospital readmission risk. The case study also highlights that in healthcare applications, model performance should be evaluated not only through numerical metrics but also by considering the potential clinical consequences of prediction errors.

