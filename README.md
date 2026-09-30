# ❤️ Heart Disease Prediction using Machine Learning

A machine learning classification project that predicts whether a patient has **Heart Disease** using Logistic Regression trained on the UCI Cleveland Heart Disease dataset (13 clinical parameters).

> 🎓 **Internship Project** — Machine Learning (Healthcare)

---

## 📖 Project Overview

Cardiovascular disease is the **#1 cause of death globally** (~18 million deaths/year, WHO). Early risk detection enables timely intervention, but full clinical workups (ECG, angiography, stress tests) are expensive and time-consuming.

**Goal:** Build an ML model that predicts heart disease status from 13 routine clinical parameters — an interpretable decision-support tool for screening.

---

## 📊 Dataset

**UCI Cleveland Heart Disease Dataset** (included: `data.csv`)

| Property | Value |
|---|---|
| Total Records | 303 patients |
| Features | 13 clinical parameters |
| Disease Present (1) | 165 (54.5%) |
| No Disease (0) | 138 (45.5%) |
| Missing Values | 0 |

**Features:** age, sex, chest pain type (cp), resting blood pressure (trestbps), cholesterol (chol), fasting blood sugar (fbs), resting ECG (restecg), max heart rate (thalach), exercise-induced angina (exang), oldpeak, slope, major vessels (ca), thalassemia (thal)

---

## 🔬 Methodology

1. **Data Loading** — CSV → pandas DataFrame (303 × 14)
2. **Inspection** — shape, `info()`, missing values check (0 found)
3. **Statistical Analysis** — `describe()` summary
4. **Target Analysis** — distribution: 165 vs 138 (fairly balanced)
5. **Feature/Label Split** — X = 13 features, Y = target
6. **Train-Test Split** — `test_size=0.2, stratify=Y` → 242 train / 61 test
7. **Model Training** — Logistic Regression
8. **Evaluation** — accuracy on train & test sets
9. **Predictive System** — end-to-end inference on new patient data

---

## 🤖 Model

**Logistic Regression** (scikit-learn)

- Models disease probability via the logistic (sigmoid) function
- Probability output → 0.5 threshold → binary decision
- **Why it suits medical data:**
  - Highly interpretable — doctors can trace feature influence
  - Strong baseline for small clinical datasets
  - Industry standard for binary diagnosis tasks

---

## 📈 Results & Key Findings

| Metric | Value |
|---|---|
| **Test Accuracy** | **81.97%** |
| Training Accuracy | 85.12% |
| Overfitting Gap | ~3.1% (healthy) |

**Key findings:**
- ✅ 81.97% on unseen data with a simple interpretable model
- ✅ Predictive system verified: new patient data → `[0]` → "The Person does not have a Heart Disease"
- 📌 Published studies on UCI heart data report 80–85% for LR — this result is competitive

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
jupyter notebook Heart_Disease_Prediction.ipynb
# Kernel → Restart & Run All
```

Sample prediction (last cell of notebook):
```python
input_data = (62, 0, 0, 140, 268, 0, 0, 160, 0, 3.6, 0, 2, 2)
# Output: [0] → "The Person does not have a Heart Disease"
```

---

## 🛠 Tech Stack

Python 3.10 • Scikit-learn • Pandas • NumPy • Jupyter

---

## ⚠️ Limitations & Future Scope

- Small dataset (303 patients, single region)
- No cross-validation / hyperparameter tuning yet
- Binary outcome only — no severity grading
- **Future:** K-Fold CV, Random Forest/SVM/KNN benchmarks, ROC-AUC analysis, feature importance for clinicians, Streamlit decision-support app

---

## 📁 Files

| File | Description |
|---|---|
| `Heart_Disease_Prediction.ipynb` | Main executed notebook |
| `Heart_Disease_Prediction_Presentation.pptx` | 10-slide presentation |
| `data.csv` | Dataset |
| `README.md` | This documentation |
| `requirements.txt` | Dependencies |

---

