# **Credit Card Fraud Analysis – End-to-End Project**

<img src="https://raw.githubusercontent.com/priyankadatacodes/credit-card-fraud-analysis-end-to-end/main/credit_card_fraud_banner.png" width="100%">

**Tools Used:** Python, Pandas, NumPy, Matplotlib, Seaborn, SMOTE, XGBoost, Joblib  
**Dataset:** Kaggle – Credit Card Fraud Dataset  

---

## **Executive Summary**

Credit card fraud is **rare, hidden, and financially damaging**, making it difficult to detect using traditional rule-based systems.  
This project builds an **end-to-end fraud detection pipeline** that combines **data analysis, feature engineering, imbalance handling, and machine learning** to identify fraudulent transactions with high recall.

Using historical transaction data, the project uncovers **fraud behavior patterns**, optimizes detection thresholds, and produces **reporting-ready outputs** suitable for risk monitoring and compliance teams.

---

## **Why I Built This Project**

Banks and fintech companies face a critical trade-off:
- Missing fraud → **direct financial loss**
- Too many false alerts → **poor customer experience**

I built this project to:
- Understand how **fraud behaves in real transaction data**
- Learn how to work with **highly imbalanced datasets**
- Build a detection system that prioritizes **recall**, which is critical in fraud analytics
- Translate model outputs into **business-usable insights**

This mirrors real-world fraud analytics workflows used by **risk and compliance teams**.

---

## **Business Context**

Financial institutions aim to:
- Detect fraudulent transactions as early as possible  
- Reduce monetary loss  
- Minimize false positives that block genuine customers  
- Maintain audit trails for compliance and monitoring  

Fraud patterns are often **subtle and behavioral**, making machine learning essential for effective detection.

---

## **Problem Statement**

Analyze historical credit card transaction data to:
- Identify patterns associated with fraudulent activity  
- Build a machine learning model to detect fraud  
- Improve fraud detection recall while keeping false alerts manageable  
- Deliver insights and outputs suitable for risk dashboards and audits  

---

## **Business Objectives**

- Detect fraudulent transactions accurately  
- Understand fraud behavior and timing patterns  
- Improve recall to minimize missed fraud cases  
- Support fraud monitoring with KPIs and reports  
- Build an interpretable, analyst-friendly ML solution  

---

## **Dataset Overview**

- **Total Transactions:** **284,807**
- **Fraud Cases:** **0.17%** (highly imbalanced)
- **Target Variable:**  
  - `Class = 1` → Fraud  
  - `Class = 0` → Non-Fraud  

### **Key Features**
- `V1–V28`: PCA-transformed behavioral features  
- `Amount`: Transaction value  
- `Time`: Seconds since first transaction  

---

## **Feature Engineering**

To improve interpretability and model performance:

- Standardized:
  - **scaled_amount**
  - **scaled_time**
- Engineered:
  - **Hour** (extracted from Time)

These features help capture **real-world transaction behavior**, such as time-based fraud patterns.

---

## **Analysis & Methodology**

### **1. Data Cleaning**
- Verified missing values  
- Removed duplicate transactions  

### **2. Exploratory Data Analysis (EDA)**
- Fraud distribution by hour  
- Transaction amount patterns  
- Fraud vs non-fraud comparisons  
- Correlation analysis  

### **3. Handling Class Imbalance**
- Applied **SMOTE** on training data only  
- Preserved original fraud ratio in test set  

### **4. Train-Test Split**
- Stratified split to maintain fraud proportion  

### **5. Modeling**
- **XGBoost Classifier**
- Used PCA features + engineered features  

### **6. Threshold Optimization**
- Tuned classification threshold using **precision–recall trade-off**
- Prioritized recall to reduce missed fraud  

### **7. Evaluation**
- Precision  
- Recall  
- F1 Score  
- ROC-AUC  
- Confusion Matrices (default vs optimized threshold)  

---

## **Key EDA Insights**

### **Fraud by Hour**
Fraud is **not random**. It peaks around:
- **Early morning (~2 AM)**
- **Midday (11 AM–12 PM)**
- **Evening (5 PM–6 PM)**

These periods often align with **low vigilance or high transaction volume**.

---

### **Transaction Amount Patterns**
- Most transactions are small  
- Fraud transactions are more **clustered**
- Fraudsters often test with small amounts before larger attempts  

---

### **Correlation Analysis**
- PCA features are largely independent  
- Engineered features add meaningful context  
- Fraud label shows weak direct correlation → requires ML-based detection  

---

## **Modeling Strategy**

**Model Selected:** **XGBoost Classifier**

**Why XGBoost?**
- Strong performance on tabular data  
- Handles non-linear behavioral patterns  
- Works well with imbalanced datasets  
- Interpretable feature importance  

**Features Used:**
- `V1–V28` (behavioral PCA features)  
- `scaled_amount`  
- `scaled_time`  
- `Hour`  

---

## **Model Evaluation Results**

### **Default Threshold (0.5)**
- Good precision  
- **Low recall** (misses fraud cases)  

### **Optimized Threshold**
- **Significant recall improvement**
- Better fraud capture rate  
- Slight increase in false positives (acceptable for fraud teams)  

**Metrics Generated:**
- Precision  
- Recall  
- F1 Score  
- ROC-AUC  
- Confusion Matrices  

---

## **Feature Importance Insights**

Top contributing features:
- PCA components: **V10, V12, V14, V17**
- **scaled_amount**
- **Hour**

This confirms that fraud is driven by **behavioral deviations**, not simple rule-based patterns.

---

## **Business Impact**

This project enables:
- Improved fraud detection effectiveness  
- Earlier identification of suspicious transactions  
- Reduced financial loss  
- Power BI–ready datasets for monitoring  
- Audit-friendly outputs for compliance  
- Analyst-supportive fraud detection workflows  

---

## **Deliverables**

- EDA visualizations (hour trends, distributions, correlations)  
- Fraud predictions with probabilities  
- KPIs and evaluation metrics  
- Confusion matrices  
- Balanced training data  
- Trained XGBoost model and scalers  
- Power BI–ready CSV outputs  
- Jupyter Notebook documentation  

---

## **Final Takeaway**

Fraud detection requires more than rules—it requires **behavioral analysis, imbalance handling, and optimized decision thresholds**.

This project demonstrates how **data analytics and machine learning** can be combined to build a **practical, business-aligned fraud detection system**, similar to those used in **banking and fintech environments**.

---

## **Author**

**Priyanka Lakra**  
**Aspiring Data Analyst | Python | Fraud Analytics | Machine Learning**
