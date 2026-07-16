# Customer Shopping Behavior Analysis

**An end-to-end data analytics case study** — Python (data cleaning) → SQL (hypothesis testing) → Power BI (visualization)

Prepared by Tahseenah Hamza | Dataset: 3,900 customer transaction records

---

## 📌 Business Problem

A retail company wants to understand its customers' shopping behavior to improve sales, satisfaction, and long-term loyalty. This project answers:

> **How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?**

---

## 🛠️ Tools & Workflow

| Stage | Tool | Purpose |
|---|---|---|
| Data Cleaning | Python (pandas, Jupyter) | Handle missing values, standardize columns, engineer features |
| Data Analysis | SQL (PostgreSQL) | Test 10 specific business hypotheses |
| Visualization | Power BI | Build an interactive dashboard to communicate findings |

---

## 📊 Dashboard Preview

![Dashboard Screenshot](dashboard_screenshot.png)

*(Upload your dashboard screenshot/export to the repo and it will render here)*

---

## 🔑 Key Insights

- **Loyal customers are under-subscribed.** 72% of repeat buyers (5+ past purchases) are not enrolled in the subscription program — the strongest actionable finding in the analysis.
- **Subscription status doesn't predict higher spend.** Subscribers averaged $59.49 vs. $59.87 for non-subscribers — essentially flat.
- **Discounting shows mixed effectiveness.** Only ~half of discount users spent above the overall average; discount rates are fairly uniform (45–50%) across top products.
- **Category drives revenue more than demographics.** Clothing vs. Outerwear shows a 5.6x spread, while age groups showed only a ~10% spread and were excluded from the final dashboard.
- **79.9% of customers fall into the "Loyal" segment**, based on previous-purchase thresholds.

### Recommendation
Target the ~2,500 non-subscribed customers with 5+ previous purchases with a subscription incentive campaign — a lower-risk, higher-conversion audience than acquiring new subscribers from scratch.

---

## 📁 Repo Contents

- `customer_shopping_behavior.csv` — raw dataset
- `data_cleaning.ipynb` — Python/pandas cleaning & feature engineering notebook
- `analysis_queries.sql` — 10 SQL business-question queries
- `Customer_Shopping_Behavior_Project_Documentation.pdf` — full write-up with methodology and reasoning behind each decision
- `dashboard_screenshot.png` — Power BI dashboard export

---

## 📄 Full Documentation

See [`Customer_Shopping_Behavior_Project_Documentation.pdf`](./Customer_Shopping_Behavior_Project_Documentation.pdf) for the complete walkthrough of every cleaning decision, SQL query, and dashboard design choice — including reasoning.

---

*Note: Findings are descriptive comparisons of averages and have not been tested for statistical significance. They should be treated as directional signals rather than confirmed causal effects.*
