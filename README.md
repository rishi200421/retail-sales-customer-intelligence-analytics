# Retail Sales, Customer Intelligence & Profitability Analytics

An end-to-end retail business analytics project combining **Python, statistical analysis, machine learning, customer segmentation, and Microsoft Power BI** to analyze sales performance, understand customer behavior, evaluate product profitability, and generate actionable business insights.

## Project Overview

This project explores a year of retail transaction data containing 10,000 transactions across different regions, cities, sales channels, customer types, and product categories.

The objective is to transform raw, inconsistent business data into a structured analytical dataset, identify meaningful business patterns, understand customer purchasing behavior, and develop predictive models for sales forecasting.

The project follows an end-to-end analytics workflow, from data preparation and exploratory analysis to predictive modeling and interactive business intelligence dashboards.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data processing and analysis |
| Pandas | Data cleaning, transformation, aggregation |
| NumPy | Numerical operations and feature engineering |
| Matplotlib / Seaborn | Exploratory data visualization |
| SciPy / Statsmodels | Statistical testing |
| Scikit-learn | Predictive modeling and evaluation |
| Power BI | Interactive business intelligence dashboards |
| DAX | Measures and analytical calculations |

## Dataset

The project uses a synthetic retail sales dataset designed to simulate real-world business data quality problems.

The original dataset contains 10,000 transactions, with additional deliberately introduced duplicate records and data inconsistencies.

The dataset includes information about:

- Transaction dates and invoice IDs
- Customer IDs, demographics, and tenure
- Product categories and unit prices
- Units sold and discount percentages
- Regions, cities, and sales channels
- Payment methods and salesperson IDs
- Shipping costs, taxes, and invoice values
- Cost of goods and gross profit
- Returns, delivery duration, and customer ratings

### Data Quality Challenges

The original dataset was intentionally made imperfect to simulate practical business analytics scenarios:

- Duplicate transaction records
- Missing values across multiple columns
- Inconsistent date formats
- Currency symbols and commas inside numerical fields
- Percentage values stored as strings
- Inconsistent categorical labels
- Numerical outliers
- Inconsistent sales values requiring validation

The data preparation process addresses these issues before analysis.

## Project Workflow

### 1. Data Cleaning and Preparation

Performed data quality checks and transformed the original dataset into a consistent analytical format.

Key operations:

- Identified and removed duplicate records.
- Standardized transaction date formats.
- Converted currency and percentage strings into numerical values.
- Corrected inconsistent categorical labels.
- Investigated missing values and applied suitable imputation strategies.
- Validated numerical ranges and business rules.
- Checked the consistency of important sales-related fields.

**Output:** Cleaned transaction dataset.

### 2. Feature Engineering

Created additional variables to support deeper business analysis.

Engineered features include:

| Feature | Purpose |
|---|---|
| Revenue Per Unit | Revenue generated per unit sold |
| Profit Per Unit | Profit generated per unit sold |
| Discount Ratio | Discount relative to gross sales |
| Cost Ratio | Cost relative to net sales |
| Shipping Ratio | Shipping cost relative to sales |
| Return Rate | Returns relative to units sold |
| Year / Month / Quarter | Time-based analysis |
| Age Group | Customer demographic segmentation |
| Tenure Group | Customer tenure segmentation |
| Profitability | Profitable versus loss-making transactions |
| High Discount | Discount-level classification |
| Delivery Category | Delivery duration classification |

Additional customer-level aggregations were created to analyze total sales, total profit, order frequency, average order value, ratings, discounts, and returns.

### 3. Exploratory Data Analysis

Conducted exploratory analysis to understand business performance and discover patterns.

Areas investigated:

- Monthly sales and profit trends
- Sales performance across regions
- Product category performance
- Sales versus profit comparisons
- Profit margins across product categories
- Discount patterns and their relationship with profitability
- Customer purchasing behavior
- Customer sales concentration and Pareto analysis
- Return patterns and operational indicators

The analysis focuses on identifying business performance differences rather than relying only on total revenue.

### 4. Statistical Analysis

Applied statistical techniques to investigate whether observed business patterns were statistically meaningful.

Methods explored:

- Correlation analysis
- Independent samples t-test
- One-way ANOVA
- Tukey HSD post-hoc comparisons
- Chi-square test of independence

Example analytical questions:

- Is average profit margin different between high-discount and normal-discount transactions?
- Does sales performance differ across product categories?
- Which category pairs show statistically significant differences?
- Is there an association between discount classification and transaction profitability?

Statistical significance is interpreted alongside practical business relevance. Correlation is not treated as proof of causation.

### 5. Customer Intelligence and RFM Segmentation

Developed a customer-level analytical dataset using RFM analysis.

RFM stands for:

- **Recency:** How recently a customer purchased.
- **Frequency:** How often a customer purchased.
- **Monetary:** How much revenue a customer generated.

Customers were assigned RFM scores and grouped into business segments.

Segments include:

- High Value
- At Risk
- New/Potential
- Regular

The resulting customer-level dataset supports customer segmentation, spending analysis, and customer intelligence dashboards.

### 6. Predictive Modeling

Developed regression models to predict transaction sales (`End_Sales`).

The selected input features include:

- Units Sold
- Unit Price
- Discount
- Region
- City
- Sales Channel
- Customer Type
- Product Category
- Customer Age
- Customer Tenure
- Orders in the Last 90 Days

A preprocessing pipeline was developed using numerical imputation, categorical imputation, one-hot encoding, and regression models.

#### Model Comparison

A chronological train-test split was used to evaluate performance on later transactions.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 2,655.33 | 5,669.50 | 0.706 |
| Random Forest Regressor | 651.61 | 1,799.15 | 0.970 |

**Best-performing model:** Random Forest Regressor.

The Random Forest model achieved a lower prediction error and higher R² on the chronological test set.

These results are specific to the synthetic dataset and its generated patterns. They should not be interpreted as guaranteed performance on real retail data.

### 7. Power BI Dashboard

Developed an interactive multi-page Power BI report to present business performance and analytical findings.

#### Page 1 — Executive Overview

Provides a high-level view of business performance.

Key KPIs:
- Total Sales
- Total Profit
- Profit Margin
- Average Order Value

Visual analysis:
- Monthly sales versus profit
- Sales by region
- Sales by product category

Interactive filters support time, region, and sales channel analysis.

#### Page 2 — Customer Intelligence

Focuses on customer value and purchasing behavior.

Key analysis:
- Total customers
- High-value customers
- At-risk customers
- Average customer spending
- Customer distribution by segment
- Revenue contribution by customer segment
- Top 10 customers by spending
- Customer frequency versus monetary value

Uses the RFM customer segmentation dataset.

#### Page 3 — Product & Profitability

Evaluates product performance beyond revenue.

Key analysis:
- Total units sold
- Total discounts
- Total returns
- Average discount
- Sales versus profit by product category
- Profit margin by category
- Discount versus profitability
- Returns by product category

#### Page 4 — Operations & Geography

Focuses on operational performance and geographical analysis.

The geographical map visual is the remaining dashboard component to be completed.



## Key Business Questions

This project aims to answer questions such as:

1. Which regions and product categories generate the most sales?
2. Which categories generate the highest profit margins?
3. Are higher discounts associated with lower profitability?
4. Which customers contribute the most revenue?
5. Which customers may be at risk of becoming inactive?
6. How is revenue distributed across customer segments?
7. How do sales and profits change over time?
8. Which factors help predict transaction sales?
9. Which product categories experience the most returns?

## How to Run

### Python Analysis

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/retail-sales-customer-intelligence-analytics.git
   ```

2. Navigate into the project directory:

   ```bash
   cd retail-sales-customer-intelligence-analytics
   ```

3. Install the required packages:

   ```bash
   pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn jupyter
   ```

4. Open the notebooks:

   ```bash
   jupyter notebook
   ```

5. Run the notebooks in workflow order, starting with data cleaning.

### Power BI

1. Open the `.pbix` file inside the `powerbi/` directory using Power BI Desktop.
2. If necessary, update the data source paths to point to the CSV files in the repository.
3. Refresh the data.
4. Explore the report pages and interactive filters.

## Skills Demonstrated

- Data Cleaning and Preprocessing
- Exploratory Data Analysis
- Feature Engineering
- Business Analytics
- Statistical Hypothesis Testing
- Customer Segmentation
- RFM Analysis
- Regression Modeling
- Model Evaluation
- Power BI Dashboard Development
- DAX Measures
- Business Intelligence and Data Storytelling

## Project Status

- [x] Data cleaning
- [x] Feature engineering
- [x] Exploratory data analysis
- [x] Statistical analysis
- [x] Customer RFM segmentation
- [x] Predictive modeling
- [x] Executive Overview dashboard
- [x] Customer Intelligence dashboard
- [x] Product & Profitability dashboard
- [ ] Geographical map visual

## Disclaimer

This project uses synthetic data created for educational and portfolio purposes. It does not represent actual company transactions, customers, or financial records.

---

**Developed as an end-to-end Business Analytics and Machine Learning portfolio project.**
