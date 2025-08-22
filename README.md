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
  - ✅ K-Nearest Neighbor  

**Metrics:** Accuracy, Balanced Accuracy, Weighted F1-score

### 3. Explainability
- Used **feature importance** and **SHAP values** to interpret predictions  
- Explainable AI ensures clinicians understand why a patient was predicted to stay longer  

---

## 💰 Cost Estimation
Predicted LOS is translated into **estimated patient cost** using a **cost-per-day schedule**:  
- Different **daily rates per department**  
- Adjusted by **severity level**  
- Provides transparency in billing  

---

## 📈 Fairness Check
Analyzed whether LOS predictions are **over- or under-predicted** across:  
- Age groups  
- Illness severity categories  

👉 In case of bias, models can be retrained with **re-sampling, re-weighting, or fairness constraints**.  

---

## 📌 Tech Stack
- **Language:** Python  
- **Libraries:** scikit-learn, XGBoost, Pandas, NumPy, Matplotlib, Seaborn, SHAP  
- **Tools:** Jupyter Notebook 
---

✨ *This project demonstrates how AI can make healthcare more efficient, transparent, and fair.*  
