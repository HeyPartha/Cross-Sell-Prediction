# **Cross-Sell Prediction Case Study**

## **Project Overview**
This project predicts the likelihood of cross-sell success for a leading NBFC using machine learning models.  
The solution leverages Python and popular ML libraries to address the business objective.

---
## **Case Study Solution**

### **Background**
XYZ Finance is a leading NBFC in India that specializes in **vehicle financing**. The company has a large customer base for its vehicle loans. It also offers various other products like:
- **Insurance**
- **Personal Loans**
- **Asset Management Services**

---

### **Problem Statement**
- The company's current cross-sell rate is **12%**, which is lower than the industry average.
- The company aims to increase the cross-sell rate to **25%** to:
  - Boost **revenue**.
  - Improve **customer loyalty**.

---

#### **Created By**  
**Partha Chowdhury**  
[LinkedIn Profile](www.linkedin.com/in/parthach)




---

## **Summary of Steps Performed**

### **1. Data Understanding and Cleaning**
- **Explored the dataset** to understand the available features and target variable (`cross_sell_flag`).
- **Data Cleaning**:
  - Removed or transformed non-numeric and irrelevant columns.
  - Handled missing values through imputation or removal.
  - Ensured correct data types for all features.
- **Synthetic Feature Engineering**:
  - Generated new features such as `interaction_intensity` and behavioral flags using the **Faker library** and custom logic.
  - Applied transformations to skewed features (e.g., `log1p` for `ltv` and `disbursed_amount`).

---

### **2. Exploratory Data Analysis (EDA)**
- Visualized **distributions of key features** (e.g., age, loan amount, email click rate).
- Investigated **patterns in cross-sell success**:
  - Correlations between features (e.g., `ltv` vs. `asset_cost`).
  - Cross-sell rates by demographic segments (e.g., age, employment type).
- Highlighted **important behavioral metrics**:
  - Higher engagement through email and calls correlates with higher cross-sell rates.

---

### **3. Feature Engineering**
- Created meaningful derived features:
  - **Loan-to-value ratio (LTV)** for financial capacity.
  - **Income proxies** using `disbursed_amount` and synthetic data.
  - **Interaction metrics**: email clicks, SMS counts, and call log counts.
- Performed **feature scaling and transformation**:
  - Transformed skewed numerical features.
  - Binned features like `PERFORM_CNS_SCORE` into equal-width bins.

---

### **4. Model Development**
- Built and evaluated three machine learning models:
  1. **Logistic Regression** (with SMOTE for class imbalance handling).
  2. **Random Forest** (with `class_weight='balanced'` for imbalance handling).
  3. **XGBoost** (with `scale_pos_weight` to manage class imbalance).
- **Model Comparison**:
  - Evaluated models using metrics:
    - **Accuracy**
    - **F1 Score**
    - **Balanced Accuracy**
    - **AUC-ROC**

---

### **5. Feature Importance Analysis**
- Calculated **feature importance scores** for Random Forest and XGBoost.
- Identified the **top 10 predictive features**:
  - `age`, `asset_cost`, `ltv`, `disbursed_amount`, etc.
- Used these features to test if models perform better with a reduced feature set.

---

### **6. Insights and Recommendations**
- Identified key predictors for cross-sell success:
  - Customer demographics (e.g., `age`).
  - Engagement metrics (e.g., `email_click_rate`, `call_logs_count`).
  - Financial stability indicators (e.g., `ltv`, `CREDIT_HISTORY_LENGTH_MONTHS`).
- Suggested actionable strategies:
  - Personalized marketing for high-engagement customers.
  - Bundled offerings for customers with higher loan-to-value ratios.
  - Regional targeting based on branch-level performance.

---

### **7. Model Saving and Deployment**
- Saved the trained models (**Logistic Regression**, **Random Forest**, **XGBoost**) and dependencies (e.g., SMOTE scaler).
- Prepared functions to load models and predict on unseen data for deployment.

---

### **What Could Have Been Done Better**
- **Under-sampling** could be explored as an alternative to SMOTE.
- Use of **real-world data** for cross-sell behavior instead of synthetic data.
- Incorporate external data sources (e.g., credit bureau data) for richer insights.
- Perform advanced feature engineering and hyperparameter tuning to improve model performance.

---

### **Notebook Objective**
This repository provides a complete solution for identifying customers likely to cross-sell and offers actionable insights for improving cross-sell strategies.

---
