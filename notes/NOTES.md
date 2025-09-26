# 📝 Workflow Notes – BCG X PowerCo Churn Analysis  

---

<p align="center">
  <img src="https://img.shields.io/badge/Theme-Reproducibility-blue" />
  <img src="https://img.shields.io/badge/Method-End--to--End%20Workflow-green" />
  <img src="https://img.shields.io/badge/Focus-Recall%20%7C%20Churn%20Prediction-orange" />
</p>

---

## 📂 Project Workflow
1. **Task 1 – Business Understanding**  
   - Hypothesis: churn driven by price sensitivity.  
   - Outlined required data & initial analysis approach.  

2. **Task 2 – EDA & Data Cleaning**  
   - Churn rate ≈10%.  
   - Sales channel & contract type emerged as strong churn drivers.  
   - Cleaned messy data, handled missing values, and derived useful temporal fields.  

3. **Task 3 – Feature Engineering**  
   - Log transformations for skewed features.  
   - One-hot encoding for categorical features.  
   - Derived customer tenure & contract timing features.  

4. **Task 4 – Modeling**  
   - Baseline → Logistic Regression → Decision Tree → Random Forest.  
   - Balanced with SMOTE.  
   - Random Forest delivered **~50% recall**, the most critical metric for retention.  

5. **Task 5 – Executive Summary**  
   - Synthesized all findings into a client-facing executive report with actionable recommendations.  

---

## 🔑 Reproducibility Steps
- Each **task folder** contains:
  - `data/` → raw or cleaned data inputs.  
  - `notebooks/` → Jupyter notebooks with step-by-step execution.  
  - `taskX.md` → polished markdown summary.  
- **README.md** provides navigation and quick links.  
- **NOTES.md** ensures workflow clarity for future reproduction.  

---

## 📌 Repo Design Philosophy
- **Clarity**: Each stage isolated in its own folder.  
- **Reproducibility**: Data + notebooks + markdown available for every task.  
- **Professionalism**: Repo serves as a portfolio artifact, recruiter-facing.  

---

✨ *These notes document the workflow logic, ensuring the project is transparent, reproducible, and professional.*
