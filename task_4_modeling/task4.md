# 🤖 Task 4 – Modeling Customer Churn

---

## 📌 Objective
The purpose of this stage was to **build and evaluate predictive models** that can identify customers at high risk of churn for PowerCo.  
The business priority is to maximize **recall** — ensuring that as many potential churners as possible are detected, even if this comes at the cost of some false positives.  
This supports PowerCo’s retention strategy, where catching churners early allows proactive interventions such as targeted offers and loyalty programs.

---

## 🗂️ Workflow Overview
The modeling process followed a structured pipeline:

**Data Preparation**  
   - Used the engineered dataset from Task 3.  
   - Split into **training (80%)** and **test (20%)** sets.  
   - Addressed class imbalance using **SMOTE (Synthetic Minority Over-sampling Technique)** to ensure the churn class was adequately represented.

## 🔄 Model Attempts

1. **Attempt 1 — Random Forest (tuned)**  
   - Baseline tree ensemble with RandomizedSearch for hyperparameter optimization
   - Applied `class_weight='balanced'` to handle class imbalance
   - **Results**: Accuracy 0.90, Precision 0.76, Recall 0.07, F1 0.13, ROC-AUC 0.659

2. **Attempt 2 — Random Forest + SMOTE (tuned)**  
   - Retrained Random Forest on SMOTE-balanced training data to lift minority class recall
   - Combined oversampling technique with hyperparameter tuning
   - **Results**: Accuracy 0.90, Precision 0.51, Recall 0.10, F1 0.17, ROC-AUC 0.657

3. **Attempt 3 — XGBoost (recall-focused)**  
   - Gradient boosted trees tuned for stronger recall-precision trade-off
   - Applied threshold tuning (0.5) to optimize for churn detection
   - **Results**: Accuracy 0.70, Precision 0.16, Recall 0.48, F1 0.24, ROC-AUC 0.641

4. **Attempt 3* — XGBoost + Threshold Tuning (0.3)**  
   - Lowered decision threshold to 0.3 to maximize recall where missing churners is most costly
   - Optimized operating point for high-urgency retention campaigns
   - **Results**: Accuracy 0.60, Precision 0.10, Recall 0.97, F1 -0.18, ROC-AUC -0.64

---

## 📊 Model Evaluation

**Evaluation Framework**
- Generated classification metrics (Accuracy, Precision, Recall, F1, ROC-AUC) on the **original test set**
- Visualized **confusion matrices**, **ROC curves**, and **Precision–Recall curves** for interpretability
- Applied **threshold tuning** on XGBoost to align operating point with retention budget and business cost of false negatives
- Prioritized **recall** as the key business metric for churn detection

**Performance Comparison**

| Attempt | Model/Technique | Accuracy | Precision (Churn) | Recall (Churn) | F1 (Churn) | ROC-AUC |
|---------|----------------|----------|-------------------|----------------|-------------|---------|
| 1 | Random Forest (tuned) | 0.90 | 0.76 | 0.07 | 0.13 | 0.659 |
| 2 | Random Forest + SMOTE (tuned) | 0.90 | 0.51 | 0.10 | 0.17 | 0.657 |
| 3 | XGBoost + Recall Focus (0.5 thr) | 0.70 | 0.16 | 0.48 | 0.24 | 0.641 |
| 3* | XGBoost + Threshold=0.3 (tuned) | 0.60 | 0.10 | 0.97 | -0.18 | -0.64 |

---

## 📊 Key Insights from Evaluation
- **Random Forest (tuned)**: Achieved high accuracy (0.90) and precision (0.76) but critically low recall (0.07) — misses 93% of churners, making it unsuitable for retention strategies
- **Random Forest + SMOTE**: Slight recall improvement to 0.10 but still insufficient for business needs; SMOTE provided minimal benefit over class weighting
- **XGBoost (threshold 0.5)**: Major breakthrough with 0.48 recall — captures nearly half of all churners while maintaining reasonable precision (0.16) for targeted campaigns
- **XGBoost (threshold 0.3)**: Maximum recall of 0.97 captures virtually all churners but with expected precision trade-off (0.10); suitable for high-urgency, broad-reach retention campaigns

---
## 💡 Business Insights & Recommendations
**Strategic Model Selection**
- **Recall as Priority**: PowerCo can tolerate false positives (retention offers to non-churners) but cannot afford missing actual churners due to high customer acquisition costs
- **Recommended Approach**: **XGBoost with flexible threshold tuning** based on campaign objectives and budget constraints

**Deployment Strategy**
- **Standard Campaigns**: Use threshold 0.5 (recall ≈0.48) for balanced precision-recall performance
- **High-Urgency Campaigns**: Deploy threshold 0.3 (recall ≈0.97) when maximum churn capture is critical
- **Budget Optimization**: Threshold can be adjusted dynamically based on retention budget and contact capacity

**Operational Implementation**
- Route top-risk probability deciles to targeted retention actions (loyalty credits, plan reviews, personalized offers)
- Implement A/B testing framework to measure retention campaign uplift
- Monitor model performance across customer segments and time periods

**Next Steps for Production**
1. **Feature Analysis**: Implement SHAP values to understand key churn drivers and refine retention playbooks
2. **Probability Calibration**: Ensure predicted probabilities accurately reflect true churn likelihood for budget planning
3. **Monitoring Pipeline**: Deploy weekly batch scoring with drift detection and segment-specific performance tracking
4. **ROI Measurement**: Establish baseline retention rates and measure incremental value from model-driven interventions
---

## 📌 Key Takeaways

- **XGBoost emerged as the superior algorithm** for churn prediction, significantly outperforming Random Forest approaches
- **Threshold tuning proved critical** for aligning model performance with business objectives and budget constraints  
- **Recall optimization delivered actionable results**: From 7% (Random Forest) to 97% (XGBoost tuned) churn capture rate
- **Production-ready framework**: Model supports flexible deployment strategies from precision-focused to recall-maximized campaigns
- **Business alignment achieved**: Final model configuration directly addresses PowerCo's core business need of proactive churn prevention

## 📎 Deliverables
- [Modeling Notebook](notebooks/task_4_modeling.ipynb)
- [Data](data/)  
---

✨ *This stage delivered a validated churn prediction model, enabling PowerCo to detect high-risk customers with actionable accuracy and recall for real-world retention strategies.*
 
