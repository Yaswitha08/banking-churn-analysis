# banking-churn-analysis

An interactive Power BI dashboard analyzing customer churn for a retail banking dataset of 10,000 customers. The report segments churned vs. retained customers across geography, demographics, account tenure, product holdings, balance, and credit score to identify which customer groups are most at risk of leaving.

## 📊 Dashboard Overview

**KPI Cards**
- Total Churned Customers
- Sum of Tenure

**Filters**
- Geography slicer
- Age Group slicer

**Visuals**
- Customer Churn by Geography
- Customer Churn by Gender
- Customer Churn by Tenure
- Customer Churn by Number of Products
- Customer Churn by Balance Range
- Customer Churn by Age Group
- Customer Churn by Credit Score Range
- Customer Churn Distribution (donut chart)

## 🗂️ Files in this Repository

| File | Description |
|------|-------------|
| `banking_report.pbix` | Power BI Desktop report file — open with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) |
| `churn.csv` | Raw customer dataset used to build the report |

## 🛠️ Tools & Techniques Used

- **Power BI Desktop** for data modeling and visualization
- **DAX (Data Analysis Expressions)** for:
  - Custom calculated columns (Age Group, Balance Range, Credit Score Range) using `SWITCH(TRUE(), ...)` logic to bucket continuous values into readable categories
  - Measures (e.g., Total Churned using `CALCULATE` + `COUNT`)
- Interactive slicers for dynamic filtering
- Clustered column and donut charts for segment comparison

## 📈 Key Insights

Overall churn rate: **20.37%** (2,037 of 10,000 customers)

| Segment | Finding |
|---|---|
| **Geography** | Germany churns at **32.4%** — nearly 2x France (16.2%) and Spain (16.7%) |
| **Gender** | Female customers churn more (**25.1%**) than male customers (16.5%) |
| **Number of Products** | Customers with 2 products churn least (**7.6%**); those with 3+ products churn at **82–100%**, a major red flag |
| **Age Group** | Ages **46–60 churn at 51.1%**, far higher than any other age band (18–35 churns at 7.5–8.5%) |
| **Active Membership** | Inactive members churn nearly 2x more (**26.9%** vs. 14.3% for active members) |
| **Balance** | Customers with zero/low balance churn least (**13.9%**); churn is fairly flat (~23–26%) above that |
| **Credit Score / Tenure** | Relatively weak predictors — churn stays in the 17–23% range across all bands |

**Highest-risk profile:** a customer in **Germany**, aged **46–60**, holding **3+ products**, and **not an active member** is statistically the most likely to churn.

## 🔍 How to Use

1. Clone or download this repository
2. Open `banking_report.pbix` in Power BI Desktop
3. Use the Geography and Age Group slicers to filter the dashboard
4. Explore churn patterns across the different breakdown charts

## 📌 Next Steps / Possible Extensions

- Build a predictive churn model (e.g., logistic regression) to score individual customer risk
- Design a targeted retention campaign for the German 46–60 segment
- Investigate why customers holding 3+ products churn at such high rates (possible product fit or service issue)
- Publish to Power BI Service and embed a live report link here
