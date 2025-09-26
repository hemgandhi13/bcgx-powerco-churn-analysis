# 🏆 Task 5 – Executive Summary

---

## 📌 Client Context
**PowerCo**, a major gas and electricity utility serving SMEs, faced rising **customer churn** due to competitive pricing, new energy providers, and the growth of renewable options.  
BCG X Data Science team was tasked with diagnosing the churn problem and recommending data-driven strategies for customer retention.

---

## 🔎 Task 1 – Business Understanding & Problem Framing
- Framed the problem: *Are customers leaving primarily due to price sensitivity?*  
- Outlined the **data requirements**: churn status, usage and billing history, tariff changes, demographics, satisfaction/complaints data.  
- Proposed **techniques**: regression, clustering, churn prediction models.  
- Delivered a **professional email** to the client summarizing this approach.  

✅ *Outcome*: Established a clear hypothesis and analytical plan aligned with PowerCo’s business objectives.  

---

## 📊 Task 2 – Exploratory Data Analysis & Data Cleaning
- Found **churn rate ≈ 10%** across customers.  
- Identified **sales channels** and **contract type** as strong churn drivers.  
- Consumption features (`cons_12m`, `cons_gas_12m`) showed significant differences, though highly skewed → flagged for log transformation.  
- Detected **temporal churn clustering in 2016**, suggesting market-driven effects.  
- Data cleaning: date conversions, missing-value handling, and preserving meaningful “MISSING” categories.  

✅ *Outcome*: Transformed messy raw data into a clean, structured dataset with interpretable churn patterns, enabling robust feature engineering.  

---

## ⚙️ Task 3 – Feature Engineering
- Applied **log transformations** to skewed variables to stabilize variance.  
- Used **one-hot encoding** for categorical variables (`contract`, `channel_sales`, `origin_up`) while preserving predictive “MISSING” categories.  
- Engineered **date-based features**: year, month, and customer tenure.  
- Removed irrelevant/constant columns to reduce noise.  
- Final dataset verified with no nulls in model-critical features.  

✅ *Outcome*: Delivered a **refined feature set** that improved model readiness, interpretability, and predictive potential.  

---

## 🤖 Task 4 – Modeling Customer Churn
- Established a **baseline** using Dummy Classifier (recall = 0%).  
- Trained **Logistic Regression, Decision Tree, and Random Forest** on balanced data (via SMOTE).  
- Evaluation included **classification reports, confusion matrices, ROC & PR curves**.  
- **Random Forest** achieved the best performance: ~50% recall, capturing half of churners while maintaining balanced precision.  
- Business insight: prioritizing recall ensures PowerCo identifies more churners for proactive retention campaigns.  

✅ *Outcome*: Delivered a validated churn prediction model, enabling PowerCo to detect at-risk customers and act strategically.  

---

## 💡 Business Recommendation
- **Adopt Random Forest** as the churn prediction model due to its superior recall.  
- Use model outputs to **flag high-risk customers** and target them with retention strategies (loyalty offers, pricing adjustments, improved service touchpoints).  
- Leverage **feature importance analysis** from Random Forest to understand key churn drivers and inform long-term strategy.  

---

## 📌 Key Takeaways
- **Framing**: Clearly defined business problem → price sensitivity hypothesis.  
- **EDA**: Exposed churn patterns by channel, contract type, and temporal factors.  
- **Feature Engineering**: Refined messy inputs into structured, predictive features.  
- **Modeling**: Random Forest delivered actionable recall (~50%), aligning with PowerCo’s retention goals.  
- The project illustrates a **complete data science workflow** from framing → EDA → engineering → modeling → business recommendations.  

---

✨ *This Executive Summary consolidates the entire churn analysis journey, showing how data science translates business challenges into actionable insights and strategic recommendations for PowerCo.*
