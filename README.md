
# 💼 Financial Modeling using SQL on Banking Data (BigQuery)

This project demonstrates intermediate-level financial modeling with **Google BigQuery** and **SQL** on real-world banking datasets. It focuses on estimating valuation, forecasting growth, analyzing credit risk, and optimizing loan portfolios.

---

## 📊 Project Overview

- **Tech Stack**: SQL + BigQuery + Excel/CSV
- **Dataset**: U.S. Bank Financials (Q1 2025)
- **Level**: Intermediate (Ideal for Analyst Portfolios & CVs)
- **Target Users**: Aspiring Financial Analysts, Data Analysts, SQL Learners

---

## 📁 Files Included

| Filename                                 | Type   | Description                                |
|------------------------------------------|--------|--------------------------------------------|
| `results- Financial modelling.xlsx`      | Excel  | Master file with all result sheets         |
| `Bank financial metrics.csv`             | CSV    | Clean table of key balance sheet metrics   |
| `Loan Portfolio Breakdown.csv`           | CSV    | Loan composition by category               |
| `Credit Risk Exposure Breakdown.csv`     | CSV    | Loan risk data for risk analysis           |
| `YOY Growth forecasting.csv`             | CSV    | Year-over-year forecasted growth           |
| `Portfolio Optimisation.csv`             | CSV    | Loan portfolio balancing                   |
| `README.md`                              | Markdown | Project documentation and SQL breakdown  |

---

## 📌 Key SQL Queries

### 1. 📈 Valuation Estimation (Book Value Approach)
```sql
SELECT
  Value AS Equity,
  Value * 1.2 AS Esimated_valuation_pb
FROM `my-project-2-463200.financial_modeling.bank_financials_q1_2025`
WHERE name = 'Total Equity Capital';
```

### 2. 📊 YOY Growth Forecasting
```sql
SELECT
  name,
  value,
  `Year Ago from Period` AS year_ago,
  (value - `Year Ago from Period`) / `Year Ago from Period` * 100 AS yoy_growth_pct
FROM `my-project-2-463200.financial_modeling.bank_financials_q1_2025`
WHERE name IN (
  'Total Assets',
  'Total Equity Capital',
  'Total Loans and Leases'
);
```

### 3. 🧱 Loan Portfolio Breakdown
```sql
SELECT
  name AS loan_category,
  value / 1000 AS value_in_billions
FROM `my-project-2-463200.financial_modeling.bank_financials_q1_2025`
WHERE name IN (
  '1-4 Family Residential Mortgages',
  'Commercial and Industrial Loans',
  'Auto Loans',
  'Multifamily Residential Real Estate',
  'Nonfarm Nonresidential',
  'Construction and Development',
  'Credit Cards'
);
```

### 4. 🧠 Credit Risk Exposure
```sql
SELECT
  name AS risk_type,
  value / 1000 AS value_in_billions
FROM `my-project-2-463200.financial_modeling.bank_financials_q1_2025`
WHERE name IN (
  'Loans and Leases 90 Days or More Past Due',
  'Loans and Leases in Nonaccrual Status',
  'Restructured and Current Loans and Leases'
);
```

---

## 📊 Visuals and Insights

- **Valuation (PB)** → simple multiplier on equity capital
- **YOY Growth** → bar chart or line chart by metric
- **Loan Portfolio** → pie or stacked bar chart
- **Credit Risk** → grouped bar chart of high-risk exposure

---

## 🚀 Use Case

- 📌 Demonstrates financial insight using SQL
- 📌 Ideal for Data Analytics, Finance, and FinTech roles
- 📌 Easily imported into Tableau/Power BI for dashboards

---

## 🔓 License

This project is licensed under the **MIT License**.  
You are free to use, modify, and share with attribution.

> Developed for educational and professional CV use.
