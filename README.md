# Customer Purchase Trends Analysis

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-025E8C?logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)

## Project Overview

This project analyzes customer shopping behavior from a retail transaction dataset to identify buying patterns, customer segments, product preferences, and revenue drivers.

It was built to turn raw customer purchase records into decision-ready analysis using Python for preparation, SQL for business questions, and Power BI for executive-style reporting.

The project is useful for analysts, students, and business stakeholders who want to understand how customer behavior changes across gender, product category, shipping method, subscription status, and purchase history.

Expected outcomes include cleaner data, reusable SQL analysis, a dashboard-ready summary of key metrics, and practical recommendations for retention and revenue growth.

---

## Features

- Loads a customer shopping dataset into pandas for analysis.
- Reviews dataset structure with `head`, `info`, `describe`, and null checks.
- Cleans missing values in the review rating field using category-level medians.
- Standardizes column names into snake_case for easier analysis.
- Creates derived fields such as `age_group` and `purchase_frequency_days`.
- Removes the redundant `promo_code_used` field after validation against `discount_applied`.
- Demonstrates loading the cleaned dataframe into PostgreSQL, MySQL, and SQL Server.
- Runs SQL business queries for revenue, discounts, shipping, subscriptions, segmentation, and product performance.
- Provides a Power BI dashboard and presentation artifacts for business storytelling.

---

## Tech Stack

| Category | Tools |
|---|---|
| Programming Languages | Python, SQL |
| Libraries | pandas, SQLAlchemy, psycopg2-binary, pymysql, pyodbc |
| Data Analysis | Jupyter Notebook, data cleaning, feature engineering, exploratory analysis |
| Visualization | Power BI |
| Database | PostgreSQL, MySQL, SQL Server |
| Tools | Git, GitHub, Jupyter Notebook, Power BI Desktop |

---

## Repository Structure

```text
.
├── .gitignore - Standard ignore rules for notebooks, virtual environments, and local OS files.
├── .vscode/settings.json - Workspace interpreter settings for the verified Python 3.12 environment.
├── Customer_Trends_Analysis.ipynb - Main notebook for loading, cleaning, feature engineering, and database export examples.
├── LICENSE - MIT license for reuse of the project.
├── customer_trends_sql_queries.sql - SQL business-analysis queries for revenue, segmentation, shipping, and product insights.
├── customer_shopping_behavior.csv - Source dataset with 3,900 purchase records and 18 columns.
├── customer_trends_dashboard.pbix - Power BI report used for dashboard-style analysis and visualization.
├── Customer Shopping Behavior Analysis.pdf - Exported analysis document for sharing results in PDF form.
├── Customer-Shopping-Behavior-Analysis.pptx - Presentation deck summarizing the analysis and recommendations.
├── requirements.txt - Python dependencies needed to run the notebook and supporting analysis workflow.
└── README.md - Project documentation and setup guide.
```

---

## Dataset

The repository uses a customer shopping behavior dataset with 3,900 purchase records and 18 columns.

| Column | Description |
|---|---|
| Customer ID | Unique identifier for each customer record |
| Age | Customer age |
| Gender | Customer gender |
| Item Purchased | Product purchased |
| Category | Product category |
| Purchase Amount (USD) | Transaction value in USD |
| Location | Customer location |
| Size | Product size |
| Color | Product color |
| Season | Purchase season |
| Review Rating | Customer review score |
| Subscription Status | Whether the customer is subscribed |
| Shipping Type | Shipping method used |
| Discount Applied | Whether a discount was used |
| Promo Code Used | Whether a promo code was used |
| Previous Purchases | Number of prior purchases |
| Payment Method | Payment channel |
| Frequency of Purchases | Purchase cadence text value |

Purpose: to support customer behavior analysis, revenue comparison, product analysis, and customer segmentation.

---

## Methodology

```text
Data Collection
↓
Data Cleaning
↓
EDA
↓
SQL Analysis
↓
Visualization
↓
Business Insights
```

The workflow starts with the CSV dataset, cleans and reshapes it in Python, validates the transformed data with SQL, and then packages the findings into Power BI and presentation deliverables.

---

## SQL Analysis

The SQL script focuses on business questions such as:

- revenue split by gender,
- high-spending customers who used discounts,
- top-rated products,
- purchase amount comparison by shipping type,
- subscriber versus non-subscriber revenue and spend,
- discount adoption by product,
- customer segmentation by previous purchases,
- top products within each category,
- repeat buyer subscription behavior,
- revenue contribution by age group.

The queries use grouping, aggregation, subqueries, CTEs, and window functions to answer these business questions.

---

## Python Analysis

The notebook performs the following steps:

- loads the CSV into pandas,
- previews the dataset with `head`, `info`, and `describe`,
- checks missing values,
- imputes `Review Rating` with the median rating of each category,
- standardizes column names,
- creates an `age_group` feature using quantiles,
- maps frequency labels to `purchase_frequency_days`,
- validates `discount_applied` against `promo_code_used`,
- drops the redundant promo code column,
- demonstrates exporting the cleaned dataframe into PostgreSQL, MySQL, and SQL Server.

The notebook is primarily a preparation and database-loading workflow. The business-facing visualization layer is handled in Power BI and the presentation exports.

---

## Power BI Dashboard

The repository includes a Power BI report file that supports dashboard-style analysis around:

- revenue by gender,
- customers using discounts while spending above average,
- top-rated products,
- shipping preferences and average spend,
- subscription impact,
- customer segmentation,
- strategic recommendations for retention and growth.

The report is designed to be filtered by the same analysis dimensions used across the dataset, including gender, category, shipping type, subscription status, age group, season, location, and payment method.

Business value: the dashboard helps identify high-value customer segments, product opportunities, shipping behavior, and loyalty patterns that can guide marketing and retention strategy.

---

## Key Insights

- Female customers generate slightly higher total revenue than male customers.
- Customers who use discounts can still spend above the average purchase amount.
- Express shipping customers spend more per transaction than standard shipping customers.
- Subscribed customers contribute a meaningful share of revenue and show stronger loyalty behavior.
- New customers form the largest segment, making early retention important.
- Top-rated products include items such as Blouse, Dress, and Shirt.

---

## Business Recommendations

- Strengthen subscription offers for high-value customers who already show strong spend behavior.
- Build loyalty programs that move new customers into returning and loyal segments.
- Use targeted campaigns for female buyers and express-shipping shoppers where revenue signals are stronger.
- Feature top-rated products in promotions to support conversion and satisfaction.
- Treat discount-heavy high spenders as a premium audience for exclusive offers instead of generic promotions.
- Focus retention efforts on first-time buyers because they make up the largest segment.

---

## Installation

```bash
git clone <your-repository-url>
cd customer-trends-data-analysis-SQL-Python-PowerBI
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

If you plan to use Power BI, install Power BI Desktop on a Windows environment or open the PBIX file in a compatible setup.

Set the database environment variables before running the notebook cells that load data into PostgreSQL, MySQL, or SQL Server.

---

## How to Run

1. Open `Customer_Trends_Analysis.ipynb` in Jupyter Notebook or VS Code.
2. Set the database environment variables used by the notebook export cells.
3. Run the notebook top to bottom to load the dataset, clean it, and prepare the derived columns.
4. Execute the SQL queries in `customer_trends_sql_queries.sql` against the `customer` table in your database.
5. Open `customer_trends_dashboard.pbix` in Power BI Desktop and refresh the data model if needed.
6. Review the presentation files for a concise business summary of the findings.

---

## Output

The project produces:

- a cleaned analysis-ready dataframe,
- a SQL table named `customer` in the chosen database,
- query result sets for business analysis,
- a Power BI dashboard/report,
- presentation and PDF exports for sharing insights.

---

## Future Improvements

- Add automated data validation checks before loading into the database.
- Parameterize database credentials through environment variables.
- Extend the notebook with more visual EDA plots.
- Build a reproducible refresh pipeline for the Power BI dataset.
- Add predictive modeling for churn, spend, or repeat-purchase propensity.
- Expand segmentation with clustering or cohort analysis.

---

---

## License

MIT License. See [LICENSE](LICENSE).

---

## Author

Name: Madhav