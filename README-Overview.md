# 🩺 Indian Diabetes Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat-square&logo=jupyter)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-green?style=flat-square&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

---

## 📌 1. Introduction

The **Indian Diabetes Prediction Project** is a Python-based machine learning application designed to predict the likelihood of an individual developing diabetes. By analyzing a set of key health parameters, the project builds a reliable classification model that can assist in early diagnosis and preventive healthcare — particularly within the Indian population, where diabetes prevalence continues to rise at an alarming rate.

---

## 📊 2. Dataset & Input Features

The project utilizes a structured medical dataset containing patient health records with the following key attributes:

| Feature | Description |
|---|---|
| `Age` | Age of the patient in years |
| `BMI` | Body Mass Index — indicator of body fat based on height and weight |
| `BloodPressure` | Diastolic blood pressure measured in mm Hg |
| `Glucose` | Plasma glucose concentration — primary diabetes indicator |
| `Insulin` | 2-hour serum insulin level |
| `SkinThickness` | Triceps skinfold thickness in mm |
| `Pregnancies` | Number of times the patient has been pregnant |
| `DiabetesPedigreeFunction` | Family history-based genetic risk score |
| `Outcome` | Target variable — `1` = Diabetic, `0` = Non-Diabetic |

---

## 🛠️ 3. Libraries & Tools Used

The project is built entirely in Python and leverages the following industry-standard libraries:

| Library | Role |
|---|---|
| `NumPy` | Numerical computations and array operations |
| `Pandas` | Data loading, cleaning, and manipulation |
| `Matplotlib` | Plotting charts and visual distributions |
| `Seaborn` | Statistical visualizations and heatmaps |
| `Scikit-learn` | Model building, feature scaling, and evaluation |
| `SciPy` | Statistical hypothesis testing |
| `Statsmodels` | ANOVA and regression analysis |
| `Imbalanced-learn` | SMOTE for handling class imbalance |

---

## 🔧 4. Data Preprocessing

Before feeding data into any machine learning model, a thorough preprocessing pipeline is applied to ensure data quality:

- **Missing Value Treatment:** Zero values in clinical columns (Glucose, BMI, Blood Pressure, Insulin, Skin Thickness) are biologically implausible and are replaced with the respective column mean to avoid data loss.
- **Duplicate Detection:** Unique value counts are inspected across all features to detect and handle redundant entries.
- **Feature Scaling:** `StandardScaler` is applied to normalize all input features, ensuring that no single variable dominates due to differences in measurement scale — critical for distance-based models like SVM.
- **Class Imbalance Handling:** The dataset contains more non-diabetic records than diabetic ones. **SMOTE (Synthetic Minority Over-Sampling Technique)** is applied to synthetically generate additional diabetic samples in the training set, preventing the model from being biased toward the majority class.

---

## 🔍 5. Exploratory Data Analysis (EDA)

A comprehensive EDA phase is conducted before model training to understand patterns, distributions, and relationships within the data:

- **Univariate Analysis:** Histograms and box plots are generated for each feature to examine distribution shape, skewness, and outlier presence.
- **Bivariate Analysis:** Correlation heatmaps, scatter plots, and pair plots reveal the relationships and dependencies between individual features and the target outcome.
- **Outcome-Based Comparison:** Violin plots compare Glucose, BMI, Age, Insulin, and Blood Pressure distributions between diabetic and non-diabetic patient groups to visually identify the most differentiating features.

---

## 📐 6. Statistical Analysis

Beyond visualization, the project applies formal statistical methods to validate data assumptions and feature significance:

- **Normality Test:** SciPy's `normaltest` is used to assess whether the Glucose variable follows a normal distribution.
- **Pearson Correlation Test:** Quantifies and statistically validates the linear relationship between Glucose and the diabetic outcome.
- **One-Way ANOVA:** Performed using `stats.f_oneway` and an OLS model via `statsmodels` to confirm that statistically significant differences exist across clinical variable groups at a **5% significance level (p < 0.05)**.

---

## 🤖 7. Machine Learning Models

The project trains and compares multiple classification algorithms to identify the best-performing model:

| Model | Accuracy |
|---|---|
| ✅ **Support Vector Machine (SVM)** | **83%** |
| Random Forest Classifier | 79% |
| Logistic Regression | Used for feature importance |
| K-Means Clustering | 67% |

- The dataset is split **70% training / 30% testing** using `train_test_split`.
- **SVM** achieves the highest accuracy of 83%, owing to its strength in handling high-dimensional data and its resilience against outliers.
- **Feature importance** is extracted from Logistic Regression coefficients and visualized as a horizontal bar chart to identify which health parameters most strongly influence predictions.

---

## 💡 8. Key Findings & Clinical Insights

- 🔴 **Glucose** is the most significant predictor of diabetes onset — the higher the glucose level, the greater the risk.
- 🟠 **BMI** and **Age** are the second and third most influential features respectively.
- 📌 Patients **above 37 years of age** show a significantly higher probability of developing diabetes.
- 📌 Patients with **Glucose levels exceeding 140 mg/dL** carry a substantially elevated diabetes risk.
- 🧬 The **Diabetes Pedigree Function** confirms that family history and genetic predisposition contribute measurably to diabetes risk.
- ⚖️ Elevated **BMI** is consistently associated with diabetic outcomes, reinforcing the well-established link between obesity and Type II Diabetes.

---

## 🎯 9. Goals & Impact

This project aims to contribute meaningfully to **early diabetes detection and prevention** in the Indian population by providing a transparent, well-documented, and reproducible machine learning pipeline. Specific goals include:

- Supporting **proactive healthcare interventions** by identifying at-risk individuals before clinical symptoms appear.
- Providing a **modular codebase** that can be extended with new features, algorithms, or datasets with minimal effort.
- Offering **clear documentation** at every step to ensure accessibility for both clinical professionals and data science practitioners.
- Establishing a **reusable framework** for binary health outcome classification that can be adapted to other medical prediction problems.

---

## ✅ 10. Conclusion

The Indian Diabetes Prediction Project successfully demonstrates that machine learning, when combined with rigorous statistical analysis and careful data preprocessing, can serve as a powerful tool for early medical diagnosis. **SVM emerged as the optimal model at 83% accuracy**, benefiting from normalized features and SMOTE-balanced training data. The findings confirm that **Glucose, BMI, and Age** are the three most critical factors in determining diabetes risk — insights that align with established clinical knowledge and reinforce the value of data-driven approaches in modern preventive healthcare.

---

## ⚙️ Installation & Setup

```bash
# 1. Clone the repository
git clone https://github.com/your-username/indian-diabetes-prediction.git
cd indian-diabetes-prediction

# 2. Install required libraries
pip install pandas numpy matplotlib seaborn scikit-learn scipy statsmodels imbalanced-learn

# 3. Launch the notebook
jupyter notebook Project_-_Indian_Diabetes_Prediction.ipynb
```

---

## 🙏 Acknowledgements

- **Dataset:** [Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) — originally from the National Institute of Diabetes and Digestive and Kidney Diseases (NIDDK).
- **Project Author:** Ms. Mrunalini (Data Science Trainer) | 📧 mrunalini0107@gmail.com | 📍 Mumbai – 400095

---


