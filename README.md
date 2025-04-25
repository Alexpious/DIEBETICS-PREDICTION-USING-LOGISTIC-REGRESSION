# 🩺 Diabetes Prediction Using Logistic Regression

This project applies data science and machine learning techniques to predict whether an individual is likely to develop diabetes, based on health-related features. It uses the Pima Indian Diabetes dataset and trains a logistic regression model to classify patients as diabetic or not.

---

## 📌 Project Overview
Diabetes is a chronic disease that affects millions worldwide. Early diagnosis through data analysis can help mitigate severe complications. This project follows these steps:

- Data cleaning & preprocessing
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model training & evaluation
- Insights generation from odds ratio

---

## 🧰 Tools & Technologies
- Python
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## 🧾 Dataset Features Description

| Column Name       | Description |
|-------------------|-------------|
| `num_preg`        | Number of pregnancies the individual has had. |
| `glucose_conc`    | Plasma glucose concentration (a key indicator of diabetes). |
| `diastolic_bp`    | Diastolic blood pressure (mm Hg). |
| `thickness`       | Triceps skinfold thickness (mm). |
| `insulin`         | 2-Hour serum insulin (mu U/ml). |
| `bmi`             | Body Mass Index (kg/m²). |
| `diab_pred`       | Diabetes pedigree function — genetic/family history risk. |
| `age`             | Age of the individual (in years). |
| `skin`            | Duplicate of `thickness` (removed due to multicollinearity). |
| `diabetes`        | Target variable — `True` if diabetic, `False` otherwise. |

---

## 🔍 Project Steps

### 1. Data Cleaning & Wrangling
- Converted `diabetes` column from Boolean to binary integers (0, 1).
- Dropped the `skin` column due to multicollinearity with `thickness`.
- Replaced 0s in the `insulin` column with the mean of valid entries.
- Removed age outliers based on the 5th and 95th percentiles.

### 2. Exploratory Data Analysis (EDA)
- Used `sns.heatmap()` to visualize correlation between features.
- Plotted class distribution of diabetes outcomes.
- Used `boxplot()` to compare `bmi` and `age` across diabetes status.

### 3. Performance Evaluation
- **Baseline accuracy**: 0.648
- **Training accuracy**: 0.768
- **Testing accuracy**: 0.816

The model performs significantly better than the baseline, indicating a good fit without overfitting.

#### 🧠 Odds Ratio Interpretation:
| Odds Ratio | Meaning |
|------------|---------|
| 0.0        | Extremely negative effect on outcome |
| 0.2        | Decreases odds by 80% |
| 0.4        | Decreases odds by 60% |
| 0.6        | Decreases odds by 40% |
| 1.0        | No effect |
| 1.4        | Increases odds by 40% |
| 1.6        | Increases odds by 60% |

Features with an odds ratio > 1 make diabetes **more likely**. Features with values < 1 make diabetes **less likely**.

---

## 🚀 Getting Started (Local)

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/diabetes-logistic-model.git
cd diabetes-logistic-model
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Notebook
Open `diabetes_model.ipynb` in Jupyter and run all cells.

---

## 🤝 Acknowledgments
- Dataset source: Pima Indian Diabetes Dataset (UCI/Kaggle)
- Logistic Regression theory: scikit-learn documentation

