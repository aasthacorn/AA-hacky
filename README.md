# 🏥 AI for Healthcare Efficiency: Predicting Patient Length of Stay

## 📌 Overview
Efficient hospital resource management is critical for delivering quality patient care. A major challenge is **predicting patient Length of Stay (LOS)**.  
Unexpectedly long stays cause bed shortages, overworked staff, and increased costs. Traditionally, LOS is estimated by doctors’ experience — but **AI/ML can predict LOS more accurately** using historical data.  

This project builds an AI-powered solution that predicts LOS at admission time, estimates patient cost, and checks for fairness across age groups and illness severity.

---

The approach and methology for the analysis begins with exploratory data analysis, data cleaning, removal of outliers for numeric features, and transformations for categorical features. Dummy variables were created for categorical features and label encoding used for target variable. Target variable was transformed from 9 categories to 5, encoded as as 0-10 days: 0, 11-20 days: 1, 21-30 days: 2, 31-40 days: 3, and 41+ days: 4. Data is split into training, testing, and validation at 70-20-10 split and normalized using min-max normalization. Baseline models were built for classification with strongest models being optimized using hyperparameter tuning. 

---

### 1. Exploratory Data Analysis (EDA)
- Checked missing values, class imbalance, and feature correlations  
- Distribution analysis of Stay_Days across age groups and severity  

### 2. Model Development
- Preprocessing: Label encoding, scaling, and train-test split  
- Models trained:
  - ✅ Random Forest  
  - ✅ AdaBoost  
  - ✅ Gradient Boosting  

### 3. Explainability
- Used **feature importance** and **SHAP values** to interpret predictions  
- Explainable AI ensures clinicians understand why a patient was predicted to stay longer  

---

## 📌 Tech Stack
- **Language:** Python  
- **Libraries:** scikit-learn, XGBoost, Pandas, NumPy, Matplotlib, Seaborn, SHAP  
- **Tools:** Jupyter Notebook 
---

## 🧠 Solution for 1: LOS Prediction Model

We framed the task as a multi-class classification problem with Stay_Days as the target.

Approach: Preprocessed patient + hospital features → trained ML models (Random Forest / XGBoost).

Why Multi-class: LOS is categorical (e.g., 0–10, 11–20, … days).

Evaluation: Accuracy, F1-score, confusion matrix.

Explainability: SHAP + feature importance to show which factors (age, severity, department, etc.) matter most.

✅ Outcome: Predicts LOS at admission, enabling proactive resource allocation.



## 💰 Solution for 2: Cost Estimation

We converted LOS predictions into estimated treatment costs using a cost-per-day schedule (INR).

Assumptions: Daily rates vary by department (ICU > General Ward) and severity (Mild < Severe).

Formula:

Estimated Cost = Predicted LOS (days) × Daily_Rate(dept, severity)


Example: ICU + Severe case → 15 days × ₹10,000/day = ₹1,50,000.

✅ Outcome: Early cost transparency for patients + better hospital financial planning.



## 🔎 Solution for 3: Error Analysis (Over/Under Prediction)

Our model sometimes under-predicts LOS for elderly (65+) & severe cases, and over-predicts for moderate ones.

Risk of Under-Prediction → Bed shortages, staff overload, patient care issues.

Risk of Over-Prediction → Wasted resources, blocked admissions.

🛠️ Mitigation

Add buffer days for elderly & high-severity patients.

Use cost-sensitive training (penalize under-prediction more).

Build dashboards to monitor subgroup errors.

Keep a human-in-the-loop for critical patients.

✅ Takeaway: Reduces bias & ensures safer, more efficient hospital operations.
---

✨ *This project demonstrates how AI can make healthcare more efficient, transparent, and fair.*  
