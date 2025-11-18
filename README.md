# Megaline Telecom Plan Recommendation

## Project Overview
Megaline, a mobile carrier, wants to recommend suitable new plans (Smart or Ultra) to subscribers still using legacy plans. The goal of this project is to build a **classification model** that predicts the most appropriate plan for each subscriber based on behavioral data, achieving an accuracy of at least **75%**. This helps Megaline optimize customer retention and target the right subscribers with the right plans.

---

## Table of Contents
- [Business Problem](#business-problem)  
- [Data](#data)  
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
- [Modeling Approach](#modeling-approach)  
- [Evaluation](#evaluation)  
- [Conclusion](#conclusion)  
- [Repository Structure](#repository-structure)  
- [How to Run](#how-to-run)  

---

## Business Problem
Megaline wants to move subscribers from legacy plans to either the Smart or Ultra plans. Correctly classifying subscribers can improve plan adoption, increase revenue, and enhance customer satisfaction. The challenge is to analyze historical subscriber behavior to predict the optimal plan recommendation.

---

## Data
The dataset includes the following fields for each subscriber:

| Feature       | Description                         |
|---------------|-------------------------------------|
| calls         | Number of calls made                 |
| minutes       | Total call duration (minutes)        |
| messages      | Number of messages sent              |
| mb_used       | Mobile data used (MB)                |
| is_ultra      | Target variable (1 = Ultra, 0 = Smart) |

**Note:** The data has already been preprocessed for this project.

---

## Exploratory Data Analysis (EDA)
- Inspected distributions of `calls`, `minutes`, `messages`, and `mb_used`.
- Checked correlations between features and the target variable `is_ultra`.
- Identified potential patterns in subscriber behavior for Smart vs Ultra plans.

---

## Modeling Approach
We tested multiple classification models to predict the best plan:

1. **Decision Tree Classifier**
   - Tested different `max_depth` values (1–10)
   - Observed accuracy and precision to avoid overfitting

2. **Random Forest Classifier**
   - Tested `n_estimators` from 1–10
   - Achieved the best validation accuracy with `n_estimators = 10`

3. **Logistic Regression**
   - Served as a baseline model
   - Accuracy was lower than tree-based models

**Libraries used:** `pandas`, `scikit-learn` (DecisionTreeClassifier, RandomForestClassifier, LogisticRegression, DummyClassifier), `train_test_split`

---

## Evaluation
- **Random Forest Classifier** (n_estimators = 10) achieved:
  - Validation Accuracy: ~82%
  - Test Set Accuracy: ~78%
- Accuracy exceeds the project goal of 75%
- Sanity check with a dummy classifier confirms the model is significantly better than random chance

**Observation:** Logistic Regression performed worst, and Decision Tree models with higher depth showed signs of potential overfitting.

---

## Conclusion
The Random Forest Classifier is the **best-performing model** for this dataset. It correctly identifies the suitable plan for a subscriber approximately **78% of the time**. This model provides a practical solution for Megaline to recommend plans to legacy subscribers with confidence.

---

## How to Run

1. **Clone the repository**  
```bash
git clone https://github.com/BTWBrown/Megaline-Telecom-Plan-Recommendation.git

cd Megaline-Telecom-Plan-Recommendation

pip install pandas scikit-learn matplotlib seaborn


---

This block is:

- **Step-by-step for users to run your project**  
- **Professional and easy to read**  
- Keeps all the instructions and contact info **together at the bottom**  

---

If you want, I can now **combine this with the full README.md** I wrote earlier so you have **one polished file ready to paste** into your repo. Do you want me to do that next?

---

