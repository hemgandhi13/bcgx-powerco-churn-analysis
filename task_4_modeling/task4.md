# 🤖 Task 4 – Modeling Customer Churn

---

## 📌 Objective
The purpose of this stage was to **build and evaluate predictive models** that can identify customers at high risk of churn for PowerCo.  
The business priority is to maximize **recall** — ensuring that as many potential churners as possible are detected, even if this comes at the cost of some false positives.  
This supports PowerCo’s retention strategy, where catching churners early allows proactive interventions such as targeted offers and loyalty programs.

---

## 🗂️ Workflow Overview
The modeling process followed a structured pipeline:

1. **Data Preparation**  
   - Used the engineered dataset from Task 3.  
   - Split into **training (80%)** and **test (20%)** sets.  
   - Addressed class imbalance using **SMOTE (Synthetic Minority Over-sampling Technique)** to ensure the churn class was adequately represented.

2. **Baseline Model**  
   - Implemented a **Dummy Classifier** predicting the majority class.  
   - Established a benchmark for accuracy, precision, recall, and f1.  
   - Highlighted the importance of moving beyond trivial models.

3. **Model Training**  
   - **Logistic Regression**: fast, interpretable baseline.  
   - **Decision Tree**: simple non-linear model to capture interactions.  
   - **Random Forest**: ensemble approach, more robust against variance.  
   - All models trained on balanced data and evaluated on the test set.

4. **Model Evaluation**  
   - Generated **classification reports** (accuracy, precision, recall, f1).  
   - Visualized **confusion matrices** to interpret correct vs incorrect predictions.  
   - Plotted **ROC curves** and **Precision–Recall curves** for each model.  
   - Interpretation focused on recall as the key business metric.

5. **Model Comparison**  
   - Results summarized in a comparison table (Accuracy | Precision | Recall | F1).  
   - **Random Forest** delivered the strongest balance, achieving ~50% recall, significantly outperforming Logistic Regression and the baseline.  
   - Decision Tree provided interpretability but underperformed on recall.

---

## 📊 Key Insights from Evaluation
- **Dummy Classifier**: High accuracy due to class imbalance but **recall = 0%** → not useful for churn detection.  
- **Logistic Regression**: Achieved reasonable precision but recall remained low, missing many churners.  
- **Decision Tree**: Improved recall slightly but prone to overfitting.  
- **Random Forest**: Best overall performer — ~50% recall, capturing half of churners while maintaining balanced precision and f1.  
- **SMOTE balancing**: Helped reduce bias toward the majority (non-churn) class.  

---

## 💡 Business Insights
- **Recall as the priority**: PowerCo can tolerate false positives (targeting some non-churners with offers) but cannot afford to miss real churners.  
- **Random Forest Recommendation**: With ~50% recall, PowerCo can proactively retain ~1 in 2 potential churners identified by the model.  
- **Strategic Application**: Model outputs can be used to flag at-risk customers for retention campaigns, loyalty programs, or pricing adjustments.  
- **Next Steps**: Feature importance analysis from Random Forest could identify which customer attributes drive churn the most, guiding business strategy.

---

## 📌 Key Takeaways
- A structured modeling workflow ensured fair evaluation and reproducibility.  
- Baseline models confirmed the need for machine learning approaches.  
- Random Forest emerged as the strongest model, balancing predictive performance with recall (~50%).  
- Prioritizing recall aligns directly with PowerCo’s business need: maximizing the detection of churners to enable timely retention actions.  
- The final dataset and model are now ready for **deployment or feature importance analysis**.

---

## 📎 Deliverables
- [Modeling Notebook](notebooks/task_4_modeling.ipynb)
- [Data](data/)  
---

✨ *This stage delivered a validated churn prediction model, enabling PowerCo to detect high-risk customers with actionable accuracy and recall for real-world retention strategies.*
 
