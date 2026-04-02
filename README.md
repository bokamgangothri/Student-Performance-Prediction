# Student-Performance-Prediction
A Python-based project that predicts student performance using data preprocessing, feature engineering, and basic machine learning models.

# 🎓 Student Performance Prediction
### Machine Learning Project | Python · Scikit-learn · Matplotlib · Seaborn

---

## 📌 Project Overview

This project builds a complete end-to-end machine learning pipeline to **predict a student's final exam score** based on academic and lifestyle features such as study time, attendance, previous scores, sleep hours, and parental education level.

The entire project is contained in a **single Jupyter Notebook** — no separate scripts needed.

---

## 🎯 Objective

> Given a student's profile data, predict their final exam score (0–100) and grade.

---

## 📁 Project Structure

```
Student_Performance_Prediction/
│
├── Student_Performance_Prediction.ipynb   ← Main notebook (complete pipeline)
├── README.md                              ← This file
└── Documentation.docx                    ← Full project documentation
```

---

## 🔄 Pipeline

```
Dataset Generation
      ↓
Exploratory Data Analysis (EDA)
      ↓
Data Preprocessing
  ├── Missing Value Imputation (Median)
  ├── Feature Engineering
  ├── Train/Test Split (80-20)
  ├── Feature Selection (SelectKBest)
  └── Normalization (MinMaxScaler)
      ↓
Model Training (6 models)
      ↓
Evaluation (RMSE, MAE, R², Accuracy, 5-Fold CV)
      ↓
Visualizations
      ↓
Prediction on New Students
```

---

## 📊 Dataset

| Feature | Description | Type |
|---|---|---|
| `study_time_hrs` | Daily study hours (1–10) | Continuous |
| `attendance_pct` | Class attendance percentage | Continuous |
| `prev_score` | Previous exam score (30–100) | Continuous |
| `sleep_hours` | Average nightly sleep hours | Continuous |
| `assignments_pct` | Assignment completion % | Continuous |
| `parental_edu` | Education level (0=None to 3=PG) | Ordinal |
| `extra_classes` | Extra coaching (0=No, 1=Yes) | Binary |
| `internet_access` | Internet at home (0=No, 1=Yes) | Binary |
| `final_score` | **TARGET** — Final exam score | Continuous |

**Engineered Features:**
- `study_attend_ratio` = study_time / (attendance / 100)
- `overall_index` = (prev_score + assignments_pct) / 2

---

## 🤖 Models Trained

| Model | Type |
|---|---|
| Linear Regression | Baseline linear model |
| Ridge Regression | L2 regularized linear |
| Lasso Regression | L1 regularized linear |
| Decision Tree | Non-linear, interpretable |
| Random Forest | Ensemble (bagging) |
| Gradient Boosting | Ensemble (boosting) |

All models evaluated with **5-fold cross-validation**.

---

## 📈 Results

| Model | RMSE | MAE | R² | Accuracy | CV-RMSE |
|---|---|---|---|---|---|
| **Ridge Regression** 🏆 | 5.67 | 4.42 | **0.8836** | **94.33%** | 6.23 |
| Linear Regression | 5.68 | 4.44 | 0.8833 | 94.32% | 6.22 |
| Lasso Regression | 5.71 | 4.47 | 0.8820 | 94.29% | 6.26 |
| Random Forest | ~6.2 | ~4.8 | ~0.85 | ~93.8% | ~6.7 |
| Gradient Boosting | ~6.4 | ~5.0 | ~0.84 | ~93.6% | ~6.9 |
| Decision Tree | ~7.5 | ~5.9 | ~0.77 | ~92.5% | ~7.5 |

---

## 🔮 Sample Predictions

| Student Profile | Predicted Score | Grade |
|---|---|---|
| High Performer (study=8h, attend=95%, prev=88) | 88.61 / 100 | **A** |
| Average Student (study=5h, attend=75%, prev=62) | 55.90 / 100 | **C** |
| At-Risk Student (study=2h, attend=50%, prev=38) | ~28 / 100 | **F** |

---

## 🏆 Key Findings

1. **`prev_score`** is the strongest predictor (F-score: ~900+)
2. **`study_time_hrs`** and **`overall_index`** are the next most important
3. **Ridge Regression** performs best — R² = 0.88, Accuracy = 94.33%
4. Linear models outperform ensemble methods on this dataset due to the strong linear relationships in the features

---

## 🛠️ Tech Stack

| Library | Usage |
|---|---|
| `numpy` | Numerical operations |
| `pandas` | Data manipulation |
| `scikit-learn` | ML models, preprocessing, evaluation |
| `matplotlib` | Plotting |
| `seaborn` | Statistical visualization |

---

## 🚀 How to Run

### Prerequisites
```bash
pip install numpy pandas scikit-learn matplotlib seaborn jupyter
```

### Run the Notebook
```bash
jupyter notebook Student_Performance_Prediction.ipynb
```

Then click **Cell → Run All** or press `Shift+Enter` through each cell.

---

## 📝 Grading Scale

| Score | Grade |
|---|---|
| 80–100 | A |
| 65–79 | B |
| 50–64 | C |
| 35–49 | D |
| 0–34 | F |

---

*Project by — [Month 2025]*
