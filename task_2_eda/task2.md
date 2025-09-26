# 🔎 Task 2 – Exploratory Data Analysis & Data Cleaning

---

## 📌 Objective
The aim of this stage was to **explore churn patterns and clean the dataset** for PowerCo.  
By analyzing key variables and addressing data quality issues, we identified which features are most relevant to predicting churn.

---

## ✅ Key Facts
- **Dataset**: Customer attributes, consumption data, contract information, pricing data.  
- **Churn Rate**: ~10% of customers churned.  
- **Focus**: Sales channels, consumption behavior, and temporal trends.  

---

## 📊 Exploratory Highlights

### Overall Churn
Churn rate is approximately **10%** across all customers, providing a baseline for predictive modeling.


---

### Sales Channels
- Churn varies significantly by sales channel.  
- Certain channels show systematically higher churn.  
- The **MISSING** category (created during cleaning) has ~7.6% churn → may carry predictive power.  


---

### Consumption Features
- **cons_12m** and **cons_gas_12m** differ significantly between churned vs. retained customers (p < 0.05).  
- **cons_last_month** not significant.  
- Consumption variables are **highly skewed with strong outliers** → log/winsorization needed.  

---

### Temporal Trends
- Churn heavily concentrated in **2016** (contract end dates).  
- Seasonal/monthly effects may also be present.  


---

### Additional Churn Split (Contract Type)
- Some contract types show higher churn → useful for retention strategy.  
- Other splits (products, tenure, origin) also contain signal, but contract type best illustrates the point without redundancy.  


---

## 🧹 Data Cleaning Actions
- Converted date fields to `datetime` and derived year/month features.  
- Preserved **MISSING** category in `channel_sales`.  
- Identified skewed features → plan for log transformation.  
- Checked ranges, duplicates, and missing values.  

---

## 🎯 Key Takeaways
- Churn ≈10% overall, but varies strongly by **sales channel** and **contract type**.  
- **Consumption features** are predictive but require transformation.  
- **Temporal clustering in 2016** highlights market-driven churn.  
- Cleaned dataset is now ready for feature engineering and modeling.  

---

## 📎 Deliverables
- [EDA Notebook](notebooks/task_2_EDA.ipynb)
- [Data](data/) 

---

✨ *This stage transformed messy raw data into a clean, structured dataset with clear churn patterns, setting the foundation for robust feature engineering and modeling.*

