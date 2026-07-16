# Customer Shopping Behavior Analysis

**An end-to-end data analytics case study** — Python (data cleaning) → SQL (hypothesis testing) → Power BI (visualization)

Prepared by Tahseenah Hamza | Dataset: 3,900 customer transaction records

---

## 🎯 Situation

A retail company was seeing shifts in purchasing patterns across demographics, product categories, and sales channels, but lacked a clear, data-backed understanding of what was actually driving customer decisions and repeat purchases. Management needed to know whether discounts, reviews, subscriptions, or demographics were the real levers behind revenue and loyalty — but the raw transaction data (3,900 records, 18 columns) had never been cleaned, queried, or visualized to answer that.

---

## 📋 Task

Build an end-to-end analytics pipeline that could:
1. Clean and prepare the raw dataset for reliable analysis
2. Test 10 specific business hypotheses about what drives spend, discounts, and loyalty
3. Communicate the findings through an interactive dashboard a non-technical stakeholder could use to explore the data themselves

**Guiding question:** *How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?*

---

## ⚙️ Action

| Stage | Tool | What I did |
|---|---|---|
| Data Cleaning | Python (pandas, Jupyter) | Inspected data types and nulls before touching anything; imputed missing review ratings using category-level medians (not a global fill) to preserve category-specific rating patterns; standardized all column names to snake_case; engineered an `age_group` feature using quartile binning for balanced demographic segments; converted purchase frequency text labels into a numeric `purchase_frequency_days` field; verified and dropped a fully redundant column (`promo_code_used`) only after confirming it matched `discount_applied` on all 3,900 rows |
| Data Analysis | SQL (PostgreSQL) | Loaded the cleaned dataset into PostgreSQL via SQLAlchemy; wrote 10 targeted SQL queries — including window functions (`ROW_NUMBER() OVER PARTITION BY`) for per-category product ranking and CASE-based logic for loyalty segmentation — each framed as a real question a retail stakeholder would ask, not a generic aggregate |
| Visualization | Power BI | Selected chart types based on statistical variance (coefficient of variation) across categories, cutting low-signal visuals (e.g. age-group revenue, ~5% spread) in favor of higher-signal ones (e.g. revenue by category, ~66% spread); built a single-page interactive dashboard with KPIs, revenue drivers, and a loyalty/strategy diagnostic layer, with filters for subscription status, gender, category, and size |

---

## 📈 Result

- **Uncovered the strongest actionable finding in the project:** 72% of repeat buyers (5+ previous purchases) are *not* enrolled in the subscription program — meaning the company's most loyal customers are falling outside its own retention program.
- **Found subscription status does not predict higher spend** ($59.49 subscribers vs. $59.87 non-subscribers) — a counter-intuitive result that reframed how the subscription program's value should be evaluated.
- **Showed discounting has mixed effectiveness:** only ~half of discount users spent above the overall average, and discount rates were fairly uniform (45–50%) across top products rather than concentrated anywhere specific.
- **Identified category, not demographics, as the stronger revenue differentiator** (Clothing vs. Outerwear showed a 5.6x spread vs. only ~10% across age groups) — directly shaping which charts made the final dashboard.
- **Delivered a concrete, lower-risk marketing recommendation:** target the ~2,500 non-subscribed, high-repeat customers with a subscription incentive campaign rather than spending acquisition budget on new subscribers.

---

## 📁 Repo Contents

- `customer_shopping_behavior.csv` — raw dataset
- `data_cleaning.ipynb` — Python/pandas cleaning & feature engineering notebook
- `analysis_queries.sql` — 10 SQL business-question queries
- `Customer_Shopping_Behavior_Presentation.pdf` — for a slide-deck summary of this project
- `dashboard_screenshot.png` — Power BI dashboard export


## 📊 Dashboard Preview

![Dashboard Screenshot](https://github.com/Tahseenahhamza/Customer-Shopping-Behavior-Analysis/blob/main/Customer%20Shopping%20Behavior%20Analysis%20Dashboard.jpg)

---

*Note: Findings are descriptive comparisons of averages and have not been tested for statistical significance. They should be treated as directional signals rather than confirmed causal effects.*
