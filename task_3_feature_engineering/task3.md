# ⚙️ Task 3 – Feature Engineering

---

## 📌 Objective
The purpose of this stage was to **transform raw customer data into meaningful features** that improve the predictive power of churn models for PowerCo.  
Feature engineering bridges the gap between raw data and model performance by ensuring that variables are well-structured, interpretable, and machine-learning ready.

---

## 🗂️ Overview of Available Features
The dataset contained a diverse set of variables, which we grouped into:

- **Numerical Features**  
  Energy consumption (`cons_12m`, `imp_cons`, `cons_gas_12m`),  
  financial metrics (`margin_net_pow_ele`, `net_margin`),  
  and forecasted values (`forecast_cons_12m`).  

- **Categorical Features**  
  Sales channels (`channel_sales`),  
  customer origin (`origin_up`),  
  and gas availability (`has_gas`).  

- **Date Features**  
  Activation date (`date_activ`),  
  contract end date (`date_end`),  
  renewal date (`date_renewal`).  

- **Target Variable**  
  `churn` (binary indicator of whether the customer churned).

---

## 🔧 Key Transformations

### 1. Handling Skewed Distributions
- Many consumption and variation columns were **heavily right-skewed** with extreme outliers.  
- We applied **log transformations** (e.g., `cons_12m`, `cons_gas_12m`) to stabilize variance.  
- Winsorization was considered for features with excessive zero inflation.  
- Result: More balanced distributions → models less sensitive to outliers.

---

### 2. Categorical Encoding
- **One-hot encoding** was applied to categorical features (`contract`, `channel_sales`, `origin_up`).  
- The **`MISSING` category** in `channel_sales` was preserved because exploratory analysis suggested it may carry predictive signal.  
- Encoding ensures categorical variables can be used in models like logistic regression or tree-based methods.

---

### 3. Date-Based Features
- Converted raw date fields into structured variables:
  - **Year and month** of activation, end, and renewal.  
  - **Customer tenure** calculated from activation and end dates.  
- These derived features help capture temporal patterns of churn (e.g., higher churn in 2016).

---

### 4. Removing Irrelevant / Constant Features
- Dropped columns that were constant, duplicated, or had excessive zero values.  
- Example: Certain variation price columns that added no additional information.  
- Justification for each removal was documented to maintain reproducibility.

---

### 5. Additional Feature Engineering
- Grouped customers by **tenure buckets** (new vs long-standing customers).  
- Normalized financial features (`net_margin`, `margin_net_pow_ele`) for consistency.  
- Ensured all engineered features were ready for scaling or direct use in modeling.

---

## 🧹 Data Quality Handling
- Missing values addressed:
  - Forward/backward fill for some date fields.  
  - Preserved `MISSING` category in categorical columns.  
- Ensured consistent data types (floats for numerical, categories for encoded).  
- Verified that final dataset had **no null values** in model-critical features.

---

## 🎯 Key Takeaways
- Feature engineering significantly improved data quality and modeling readiness.  
- ✅ **Log transformations** addressed skewness in consumption variables.  
- ✅ **One-hot encoding** prepared categorical variables while retaining predictive categories like `MISSING`.  
- ✅ **Date-based features** (tenure, year, month) provided important temporal signals.  
- ✅ **Irrelevant features** were dropped to reduce noise and improve efficiency.  
- ✅ The final engineered dataset is **clean, structured, and ready for model training**.

---

## 📎 Deliverables
- [Feature Engineering Notebook](notebooks/task3_feature_engineering.ipynb)
- [Data](data/)  

---

✨ *This stage completed the transition from raw exploratory data to a refined feature set, ensuring PowerCo’s churn models will be both accurate and interpretable.*
