# Insurance Risk Analytics – End-to-End ML Project (10 Academy Week 3)

This project solves a real-world insurance analytics problem for **AlphaCare Insurance Solutions (ACIS)** using structured historical data (Feb 2014–Aug 2015). It involves data cleaning, exploratory analysis, hypothesis testing, modeling, and interpretability.

---

## 📈 Business Objective

Help ACIS:
- Understand risk patterns across customers (e.g., by gender, province, zip)
- Predict claim severity for policyholders
- Identify profitable and unprofitable segments
- Optimize premium pricing using data

---

## ✅ Task Breakdown

### Task 1 – Exploratory Data Analysis (EDA)

- Loaded pipe-separated dataset using an OOP-based `DataLoader`.
- Performed univariate, bivariate, and temporal analyses via `DataProfiler`.
- Key metrics: `LossRatio`, `Margin`, `HasClaim`
- Documented outliers and trends across provinces, gender, vehicle types, etc.

###  Task 2 – Data Version Control with DVC

- Tracked raw dataset using [DVC](https://dvc.org/).
- Added `.dvc` tracking files to Git and configured a local remote (`../dvc_storage`).
- Ensured that data is reproducible via `dvc pull`.

###  Task 3 – Hypothesis Testing

- Defined and tested key business hypotheses:
    - H1: Loss ratio differs by province ✅
    - H2: Risk varies by zip code ✅
    - H3: Profit margins differ by zip ❌
    - H4: Gender influences claim behavior ✅
- Used: `ANOVA`, `Chi-squared`, `Mann–Whitney U`, all wrapped in `HypothesisTester` class.

###  Task 4 – Predictive Modeling

- Built two models using `scikit-learn` with an OOP-based `ClaimModel` class:
    1. **Claim Severity** (Regression): Predict `TotalClaims` for claimants.
    2. **Claim Probability** (Classification): Predict `HasClaim` (binary).
- Included preprocessing (numeric + categorical), model evaluation, and structure for SHAP integration.

---

## 🔁 Reproducibility Guide

### ✅ 1. Clone the Repository

```bash
git clone https://github.com/abdulkerim-adem/insurance-risk-analytics.git
cd insurance-risk-analytics
```
### ✅ 2. Create Virtual Environment
```bash
python3 -m venv env
source env/bin/activate  # Windows: env\Scripts\activate
```
### ✅ 3. Install Dependencies

```bash
pip install -r requirements.txt
```
### ✅ 4. Pull the dataset using dvc
```bash
dvc pull
```
