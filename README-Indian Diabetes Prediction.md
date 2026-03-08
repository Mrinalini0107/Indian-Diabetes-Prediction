# 🩺 Indian Diabetes Prediction — Statistical Analysis & Machine Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat-square&logo=jupyter)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-green?style=flat-square&logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

---

## 📌 Project Description

Diabetes is one of the most prevalent chronic diseases globally, with a particularly high burden in India. Early diagnosis is critical to preventing complications and improving patient outcomes. This project performs a comprehensive **statistical analysis and machine learning classification** on the **Indian Diabetes dataset** to predict whether a patient is diabetic or non-diabetic based on key clinical and demographic features.

The project follows a structured data science pipeline — from raw data ingestion and exploratory data analysis (EDA) to hypothesis testing, ANOVA, and multi-model classification — providing a complete end-to-end solution for binary health outcome prediction.

**Dataset:** The dataset contains **768 patient records** with **9 features** including Glucose levels, Blood Pressure, BMI, Insulin levels, Skin Thickness, Diabetes Pedigree Function, Number of Pregnancies, Age, and the target binary outcome (diabetic/non-diabetic).

---

## 🎯 Learning Objectives

By working through this project, you will be able to:

1. **Understand and preprocess real-world medical data** — handle missing values (encoded as zeros), detect duplicates, and perform data type analysis.

2. **Perform Exploratory Data Analysis (EDA)** — use histograms, box plots, violin plots, and distribution plots to uncover patterns and outliers in clinical variables.

3. **Apply Univariate and Bivariate Analysis** — analyze individual features independently and study feature relationships using correlation heatmaps, pair plots, and scatter plots.

4. **Conduct Statistical Hypothesis Testing** — use normality tests (SciPy's `normaltest`) and Pearson correlation tests to validate assumptions about the data.

5. **Perform Analysis of Variance (ANOVA)** — test whether treatment groups (clinical variables) differ significantly using F-statistics and OLS models via `statsmodels`.

6. **Handle Class Imbalance** — apply **SMOTE (Synthetic Minority Over-Sampling Technique)** to balance diabetic vs. non-diabetic training samples before model training.

7. **Build and Compare ML Classification Models** — train, evaluate, and compare:
   - Support Vector Machine (SVM)
   - Logistic Regression
   - Random Forest Classifier
   - K-Means Clustering

8. **Interpret Feature Importance** — identify which clinical variables (Glucose, BMI, Age, etc.) are most predictive of diabetes onset using logistic regression coefficients.

9. **Evaluate Model Performance** — use accuracy, precision, and recall metrics to select the best-performing classifier.

10. **Answer real-world clinical questions** using probability calculations directly from data (e.g., likelihood of diabetes above a certain age or glucose threshold).

---

## 📁 Project Structure

```
Indian-Diabetes-Prediction/
│
├── Project_-_Indian_Diabetes_Prediction.ipynb   # Main Jupyter Notebook
├── diabetes.csv                                  # Dataset (Pima Indian Diabetes Dataset)
└── README.md                                     # Project documentation
```

---

## 🔬 Dataset Features

| Feature | Description |
|---|---|
| `Pregnancies` | Number of times the patient has been pregnant |
| `Glucose` | Plasma glucose concentration (2-hour oral glucose tolerance test) |
| `BloodPressure` | Diastolic blood pressure (mm Hg) |
| `SkinThickness` | Triceps skinfold thickness (mm) |
| `Insulin` | 2-hour serum insulin (mu U/ml) |
| `BMI` | Body Mass Index (kg/m²) |
| `DiabetesPedigreeFunction` | Genetic diabetes likelihood based on family history |
| `Age` | Age of the patient (years) |
| `Outcome` | Target variable — `1` = Diabetic, `0` = Non-Diabetic |

---

## 🔄 Project Workflow

### Step 1 — Import Libraries
`pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`, `sklearn`, `imblearn`

### Step 2 — Load Dataset
Read `diabetes.csv`; dataset has 768 rows × 9 columns, no explicit null values.

### Step 3 — Data Understanding
- Examine shape, dtypes, unique values, and memory usage via `info()`, `shape`, `nunique()`

### Step 4 — Descriptive Statistics
- `describe()` to detect impossible zero values in medical fields (Glucose, BloodPressure, BMI, Insulin, SkinThickness)
- Replace zeros with column means to preserve data integrity

### Step 5 — Univariate Analysis
- Histograms and box plots for each feature using Matplotlib and Seaborn
- Skewness measurement for each variable

### Step 6 — Bivariate Analysis
- Correlation heatmap
- Pair plots
- Scatter plots between key variables

### Step 7 — Multivariate Analysis
- Combined visualizations across multiple features

### Step 8 — Outlier Detection
- IQR-based outlier identification and visualization

### Step 9 — Feature Relationships
- Covariance analysis and feature correlation with target

### Step 10 — Outcome-based Analysis
- Violin plots comparing clinical metrics (Glucose, Insulin, BMI, etc.) across diabetic vs. non-diabetic groups

### Step 11 — Hypothesis Testing
- **Test 1:** Normality test on Glucose distribution (SciPy `normaltest`)
- **Test 2:** Pearson correlation between Glucose and diabetes Outcome

### Step 12 — ANOVA
- One-way ANOVA using `stats.f_oneway` and OLS model via `statsmodels`
- ANOVA table generation; p < 0.05 confirms significant differences among clinical variable groups

### Step 13 — Train/Test Split
- 70/30 split using `train_test_split`

### Step 14 — Feature Scaling
- `StandardScaler` normalization applied to training and test sets

### Step 15 — Class Imbalance Handling
- SMOTE applied to oversample minority class (diabetic patients) in training data

### Step 16 — Model Training & Comparison
- SVM, Logistic Regression, Random Forest, and K-Means trained and evaluated
- Feature importance plotted from logistic regression coefficients

---

## 📊 Model Performance

| Model | Accuracy |
|---|---|
| **Support Vector Machine (SVM)** | **83%** ✅ (Best) |
| Random Forest Classifier | 79% |
| K-Means Clustering | 67% |

---

## 💡 Key Findings

- **Glucose** is the single most important predictor of diabetes onset.
- **BMI** and **Age** are the second and third most influential features.
- Factors like Diabetes Pedigree Function, Pregnancies, Blood Pressure, Skin Thickness, and Insulin also contribute.
- Patients above age 37 show a significantly higher probability of diabetes.
- Patients with glucose levels above 140 have a markedly elevated risk of a diabetic outcome.
- SVM outperforms other models due to its robustness to outliers (a common challenge in this dataset).

---

## ✅ Conclusion

This project demonstrates that **machine learning can meaningfully assist in early diabetes prediction** using routine clinical measurements. After comparing multiple classification algorithms:

- **SVM** emerged as the top-performing model with **83% accuracy**, attributed to its strength in handling high-dimensional data with outliers.
- **Random Forest** achieved 79% accuracy and is a strong alternative when interpretability and ensemble robustness are required.
- **K-Means** (unsupervised) achieved 67%, confirming that supervised approaches are better suited for this binary classification problem.

From a clinical perspective, **Glucose remains the primary biomarker** for diabetes diagnosis, aligning with established medical practice. The inclusion of BMI and Age as secondary predictors also reinforces that lifestyle and demographic factors are significant contributors. The use of **SMOTE** to address class imbalance ensured that the model does not disproportionately favor the majority (non-diabetic) class, leading to more reliable predictions.

Overall, this project provides a reusable, well-documented framework for health outcome prediction that can be extended to other datasets or medical classification tasks.

---

## 🛠️ Installation & Requirements

```bash
# Clone the repository
git clone https://github.com/your-username/indian-diabetes-prediction.git
cd indian-diabetes-prediction

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn scipy statsmodels imbalanced-learn
```

### Launch the Notebook

```bash
jupyter notebook Project_-_Indian_Diabetes_Prediction.ipynb
```

---

## 📦 Dependencies

| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical visualizations |
| `scipy` | Hypothesis testing |
| `statsmodels` | ANOVA and OLS modeling |
| `scikit-learn` | ML models, preprocessing, evaluation |
| `imbalanced-learn` | SMOTE for class imbalance |

---

## 🙏 Acknowledgements

- Dataset: [Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) — originally from the National Institute of Diabetes and Digestive and Kidney Diseases.
- Project developed by **Ms. Mrunalini** (Data Science Trainer) 📧 mrunalini0107@gmail.com 📍 Mumbai – 400095

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
