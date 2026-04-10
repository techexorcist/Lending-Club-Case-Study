# 🏦 Lending Club Risk Analytics: Exploratory Data Analysis (EDA)

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.5.3-150458.svg)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.23.5-013243.svg)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7.0-red.svg)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.12.2-blueviolet.svg)](https://seaborn.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626.svg)](https://jupyter.org/)

> **Author:** Vinodh Nagarajaiah  
> **Programme:** AI/ML Executive Programme (UpGrad & IIIT-B)

## ⏱️ Executive Summary (TL;DR)

* **The Goal:** Identify high-risk loan applicants to minimise credit loss for Lending Club.
* **The Data:** Analysed ~40,000 historical loan records across 111 initial attributes.
* **The Process:** Performed rigorous data cleaning (reduced 111 columns to 57), outlier capping (95th percentile), feature engineering, and Univariate/Bivariate Exploratory Data Analysis.
* **The Result:** Developed a clear, data-driven profile of "High-Risk" vs. "Low-Risk" borrowers, providing actionable underwriting recommendations to reduce future charge-offs.

---

## 📖 Table of Contents

1. [Problem Statement & Objective](#-problem-statement--objective)
2. [Skills & Competencies Demonstrated](#-skills--competencies-demonstrated)
3. [Methodology: The Data Science Lifecycle](#-methodology-the-data-science-lifecycle)
4. [Key Insights: The Borrower Risk Matrix](#-key-insights-the-borrower-risk-matrix)
5. [Strategic Business Recommendations](#-strategic-business-recommendations)
6. [Future Scope & Improvements](#-future-scope--improvements)
7. [Acknowledgments & Contact](#-acknowledgments--contact)

---

## 💼 Problem Statement & Objective

**LENDING CLUB** is a consumer finance company which specialises in lending various types of loans to urban customers. When the company receives a loan application, it has to make a critical decision for loan approval based on the applicant’s profile.

Two types of risks are associated with the bank’s decision:

1. **Opportunity Cost:** If the applicant is *likely to repay* the loan, then not approving the loan results in a **loss of business** to the company.
2. **Financial Loss:** If the applicant is *not likely to repay* the loan (i.e. he/she is likely to default), then approving the loan may lead to a **severe credit loss** for the company.

**The Core Objective:** To leverage Exploratory Data Analysis (EDA) to understand the **driving factors (or driver variables)** behind loan defaults. By identifying the variables which are strong indicators of a "Charged-Off" status, the company can proactively optimise its portfolio and risk assessment frameworks.

---

## 🛠️ Skills & Competencies Demonstrated

* **Data Wrangling:** Handling missing values, standardising data types, and structural dimensionality reduction.
* **Statistical Treatment:** Identifying and treating extreme outliers using percentile capping.
* **Feature Engineering:** Creating derived categorical bins ("slabs") from continuous financial variables to enable clear comparative analysis.
* **Exploratory Data Analysis:** Conducting Univariate, Segmented Univariate, and Bivariate analysis.
* **Data Visualisation:** Translating complex matrices into readable visual insights using Seaborn and Matplotlib.
* **Business Storytelling:** Bridging the gap between raw statistical data and actionable corporate strategy.

---

## 🧠 Methodology: The Data Science Lifecycle

To extract actionable insights from the raw dataset, a robust, structured data pipeline was implemented:

### 1. Data Ingestion & Cleaning

* **Dimensionality Reduction:** Identified that 54 out of 111 columns contained 100% missing (NULL) values. Dropped these to reduce computational noise, streamlining the dataset to 57 highly relevant features.
* **Data Standardisation:** Cleaned formatting issues by stripping non-numeric characters (e.g., removing `%` from `int_rate` and extracting integers from `emp_length`).
* **Outlier Treatment:** Analysed the `annual_inc` (Annual Income) distribution and capped extreme outliers at the **95th percentile**, ensuring the analysis focused on the core consumer demographic rather than extreme anomalies.

### 2. Feature Engineering

* **Variable Transformation:** Transformed continuous numerical variables into categorical segments (e.g., `loan_amnt_slabs`, `int_rate_slabs`, `dti_slabs`). This slabbing was crucial for enabling clear Bivariate plotting against the categorical target variable (`loan_status`).

### 3. Exploratory Data Analysis (EDA)

* **Univariate Analysis:** Mapped the standalone distribution of loan amounts, interest rates, employment lengths, and loan purposes.
* **Bivariate Analysis:** Correlated various borrower attributes directly against the "Charged Off" vs. "Fully Paid" status using cross-tabulations, boxplots, and countplots to isolate the primary risk drivers.

---

## 📊 Key Insights: The Borrower Risk Matrix

Through statistical visualisation, borrower profiles were segmented into distinct risk categories:

### 🟢 Low-Risk Profile (High Repayment Probability)

These are the ideal borrower traits. Applications meeting these criteria should be prioritised.

* **Loan Amount:** Moderate amounts ranging from **$5,000 to $14,000**.
* **Income:** Annual income exceeding **$90,000**.
* **Debt-to-Income (DTI):** Score is comfortably low at **≤ 10**.
* **Loan Purpose:** Primarily for weddings, car purchases, and credit card consolidation.
* **Credit Grade:** Highly rated loans in **Grade 'A' or 'B'**.
* **Public Records:** **Zero** previous public bankruptcy records.

### 🔴 High-Risk Profile (High Default Probability)

These factors strongly indicate a likelihood of default.

* **Loan Amount:** Large requests exceeding **$21,000**. (Defaults spike to ~25.79% for amounts > $28k).
* **Income:** Annual income below **$45,000**.
* **Debt-to-Income (DTI):** High score **> 20**.
* **Loan Purpose:** High failure rates observed in small business, renewable energy, and educational loans.
* **Credit Grade:** Subprime loans in **Grades 'D' through 'G'**.
* **Public Records:** **1 or more** past public bankruptcy records. (Default rates leap from 22.58% with 1 record, up to a massive 40.00% with 2 records).

---

## 💡 Strategic Business Recommendations

1. **Automate Tiered Approvals:** Applicants meeting all "Low-Risk" criteria should be fast-tracked for approval to improve customer experience and capture low-risk revenue.
2. **Implement Strict Underwriting for High-Risk Combinations:** Applications exhibiting 3 or more "High-Risk" flags should automatically trigger manual underwriting review, require higher collateral, or face outright rejection.
3. **Adjust Risk Premiums:** Re-evaluate the interest rates and tenure options for historically high-risk loan purposes (e.g., small businesses) to offset the statistical probability of credit loss.
4. **Monitor Long-Term Loans:** 60-month loan terms show a disproportionate rate of charge-offs combined with higher interest rates compared to 36-month terms. Tighten the baseline approval criteria for longer-term lending.

---

## 🚀 Future Scope & Improvements

While this project focuses on robust Exploratory Data Analysis, the foundation laid here can be expanded into a full-scale predictive system:

1. **Machine Learning Pipeline:** Implement binary classification models (Logistic Regression, Random Forest, XGBoost) to transition from descriptive analytics to predictive risk scoring.
2. **Handling Class Imbalance:** Apply SMOTE (Synthetic Minority Over-sampling Technique) to balance the "Charged Off" vs "Fully Paid" classes for more accurate predictive modelling.
3. **Natural Language Processing (NLP):** Extract sentiment and intent from the loan description text fields (`desc` / `title`) to uncover hidden behavioural predictors of default.
4. **Interactive Dashboarding:** Export the cleaned dataset into Tableau, Power BI, or a Python Streamlit app to create an interactive tool for loan officers to evaluate risk in real-time.

---

## 🎓 Acknowledgements & Contact
This project is an assessment exercise designed and integrated into the AI/ML Programme at **UpGrad**, in collaboration with **IIIT-B**.

**Created by:** Vinodh Nagarajaiah  

* 💼 **LinkedIn:** [vinodh-nagarajaiah](https://www.linkedin.com/in/vinodh-nagarajaiah/)
* 🐙 **GitHub:** [@techexorcist](https://github.com/techexorcist)
* ✉️ **Email:** [vinodh.nagarajaiah@gmail.com](mailto:vinodh.nagarajaiah@gmail.com)

<br>

> **Disclaimer:** *The dataset used in this project is for educational purposes only. All personally identifiable information (PII) has been removed or anonymised.*

---

## 📜 Licence
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the LICENSE file for details.
