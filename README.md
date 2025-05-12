# Loan Default Risk Analysis

This end-to-end data analytics and machine learning project analyzes and models credit default risk using the Lending Club dataset (2007–2015) with over **2.26 million loan records**. The workflow combines Python (for data cleaning and modeling) with Power BI (for interactive business-focused dashboards). This project is built to meet professional standards expected by top-tier firms in data-driven finance and consulting.

---

## Part 1: Data Cleaning & Feature Engineering (Python)

### Objective
Prepare raw loan data for predictive modeling and BI reporting by cleaning, transforming, and enriching key variables.

### Key Steps
- **Dropped columns** with more than 50% missing values.
- **Handled missing values** in `emp_length`, `annual_inc`, and other key fields.
- **Created features:**
  - `issue_year` from `issue_d`
  - `income_to_loan_ratio`
  - `log_annual_inc` (log-transformed income)
- **Exported final dataset** as `LoanData_Cleaned.csv` (13 key columns).

---

## Part 2: Power BI Dashboard (Pages 1–5)

### Page 1: Loan Portfolio Overview
**Objective:** Provide a high-level snapshot of the loan book.

**Visualizations:**
- Total Number of Loans: **2,260,668**
- Average Interest Rate: **13.1%** (with 36-month loans averaging **11.95%**)
- Average Annual Income: **€77,992**
- Default Rate: **12.5%**
- Average Term: **42.9 months**
- Loan Distribution by Status

**Insight:**
- Most loans were issued for 36 months with moderate interest rates.
- Default rates vary significantly by grade — from **3.48% (Grade A)** to **38.49% (Grade G)**.

📸 *Screenshot: Page 1 – Loan Portfolio Overview*

---

### Page 2: Risk Analysis
**Objective:** Understand key drivers and patterns in loan defaults.

**Visualizations:**
- Default Rate by Loan Purpose
- Default Rate by Grade and Subgrade
- Average Income-to-Loan Ratio by Default Status
- Average Interest Rate by Grade

**Insight:**
- “Small Business” and “Renewable Energy” loans had the highest default rates.
- Lower grades (E, F, G) showed significantly higher risk and interest rates.
- Loans with lower income-to-loan ratios were more likely to default.

📸 *Screenshot: Page 2 – Risk Analysis*

---

### Page 3: Customer Profile & Behavior
**Objective:** Analyze financial profiles and demographics of borrowers.

**Visualizations:**
- Average Loan Amount by Home Ownership Type
- Average Annual Income by Loan Purpose
- Average Annual Income by Employment Length (Years)
- Number of Loans by Income-to-Loan Group

**Insight:**
- Borrowers who rent tend to request lower loan amounts.
- Highest incomes were observed in loans issued for “Small Business” and “Home Improvement” purposes.
- Borrowers with higher income-to-loan ratios and longer, known employment history tend to default less frequently.

📸 *Screenshot: Page 3 – Customer Profile & Behavior*

---

### Page 4: Time Trend Analysis
**Objective:** Understand how loan metrics evolve over time.

**Visualizations:**
- Loan Volume over Time
- Average Interest Rate over Time
- Default Rate over Time
- Default Rate by Employment Length

**Insight:**
- Loan volume sharply increased between 2012 and 2018.
- Default rate peaked in 2015 and stabilized afterwards.
- Borrowers with **4–6 years** of employment exhibited the **lowest default rates (~12%)**, while those with **8+ years** peaked at **14%,** suggesting that longer tenure doesn't always correlate with lower risk.

📸 *Screenshot: Page 4 – Time Trend Analysis*

---

## Part 3: Machine Learning – Default Prediction (Python)

### Objective
Build a logistic regression model to estimate the probability of default.

### Highlights
- Model: Logistic Regression with `class_weight='balanced'`
- ROC AUC: **0.73**
- Recall (defaults): **68%**
- **254,000 loans (≈11.2%)** were classified as high-risk (predicted default probability > 50%) across the entire dataset.

### Features Used:
- Numeric: `loan_amnt`, `term`, `int_rate`, `emp_length`, `annual_inc`
- Engineered: `income_to_loan_ratio`, `issue_year`
- Categorical (encoded): `grade`, `purpose`, `home_ownership`

**Insight:**
- The model identifies high-risk profiles across multiple loan types.
- Grade, purpose, and employment stability are strong indicators of creditworthiness.

---

## Part 4: Risk Prediction Dashboard (Page 5)

### Objective
Visualize model output and provide actionable insight to risk teams.

**Visualizations:**
- High-Risk Loans Count (p > 0.5): **~254,000**
- Average Predicted Risk by Loan Term
- Predicted Default Risk: Grade vs. Loan Purpose (Heatmap)
- Distribution of Predicted Default Risk (Histogram)
- Average Predicted Risk by Grade

**Insight:**
- Loans with **60-month terms** show higher default probabilities overall.
- **Grades E, F, G** exhibit the highest predicted risks.
- Risk assessment improves significantly with segmentation by both `term` and `grade`.

📸 *Screenshot: Page 5 – Risk Prediction*

---

## 🛠 Tools Used
- **Python:** pandas, scikit-learn, matplotlib
- **Power BI:** DAX, Power Query, Time Intelligence
- **Jupyter Notebook**, GitHub

---

## Authorin
**Ekaterina Podolskaya**  
Aspiring Data Analyst • Business-oriented • Python & BI Enthusiast  
[LinkedIn](www.linkedin.com/in/ekaterina-podolskaya) • [GitHub](https://github.com/Ekaterina-Podolskaya)

## Download Power BI Project
[Download](https://drive.google.com/file/d/1l2QEDxex6JWsf5OMMZ6tC21hAr69Cx1U/view?usp=sharing)
