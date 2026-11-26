# Customer Shopping Behavior Analysis

An end-to-end data analytics project that uses Python, PostgreSQL and Power BI to understand how customers shop and what drives spending, subscriptions and loyalty for a retail company.


## Business Problem

A retail company wants to understand its customers' shopping behavior in order to improve sales, customer satisfaction and long-term loyalty. Management has noticed shifts in buying patterns across customer groups, product categories and sales channels, and wants to know which factors, such as discounts, reviews, seasons or payment preferences, drive purchases and repeat business.

**Key question:** How can the company use shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?

## Dataset

- **Rows:** 3,900 purchase records
- **Columns:** 18
- **Customer details:** age, gender, location, subscription status
- **Purchase details:** item purchased, category, purchase amount, season, size, color
- **Shopping behavior:** discount applied, promo code used, previous purchases, frequency of purchases, review rating, shipping type
- **Data quality:** 37 missing values in the Review Rating column

## Tools Used

- **Python:** Pandas, SQLAlchemy, Jupyter Notebook
- **Database:** PostgreSQL, pgAdmin
- **Visualization:** Power BI
- **Other:** Excel, GitHub

## Project Workflow

### 1. Data Preparation (Python)
- Loaded the dataset with Pandas and checked its structure with `df.info()` and `df.describe()`
- Filled the 37 missing review ratings using the **median rating of each product category**, so ratings from one category do not affect another
- Renamed all columns to snake_case for consistent use in Python and SQL
- Created two new features: `age_group` (binned customer ages) and `purchase_frequency_days` (days between purchases)
- Confirmed that `discount_applied` and `promo_code_used` held the same information, then dropped `promo_code_used`
- Loaded the cleaned data into PostgreSQL using SQLAlchemy

### 2. Data Analysis (SQL)
Ten business questions were answered with PostgreSQL queries using aggregations, subqueries, CTEs and window functions:

1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average review rating
4. Average purchase amount by shipping type (Standard vs Express)
5. Spend and revenue of subscribers vs non-subscribers
6. Top 5 products by discount rate
7. Customer segmentation: New, Returning and Loyal
8. Top 3 products in each category
9. Repeat buyers (more than 5 previous purchases) and subscriptions
10. Revenue by age group

### 3. Dashboard (Power BI)
An interactive dashboard with:
- 3 KPI cards: number of customers, average purchase amount, average review rating
- 5 charts: subscription split, revenue and sales by category, revenue and sales by age group
- 4 slicers: subscription status, gender, category, shipping type

## Key Findings

- **Revenue by gender:** Male customers generated $157,890 and female customers $75,191. Men are about 68% of the records, so revenue largely follows the customer mix.
- **Discounts:** 839 customers used a discount and still spent above the average purchase. About 43% of all purchases carried a discount. Hat (50.0%), Sneakers (49.7%), Coat (49.1%), Sweater (48.2%) and Pants (47.4%) rely on discounts the most.
- **Product ratings:** Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80) and Skirt (3.78) are the top-rated items. The overall average rating is 3.75.
- **Shipping:** Express shipping customers spent $60.48 on average compared with $58.46 for Standard, a difference of about 3.5%.
- **Subscriptions:** Only 27% of customers (1,053) are subscribers. Subscribers and non-subscribers spend about the same on average ($59.49 vs $59.87), and non-subscribers generate about 73% of revenue.
- **Customer segments:** 3,116 customers are Loyal, 701 are Returning and 83 are New.
- **Repeat buyers:** Of customers with more than 5 previous purchases, 958 are subscribed and 2,518 are not. About 28% subscribe, close to the 27% overall rate.
- **Age groups:** Young Adults contribute the most revenue ($62,143), followed by Middle-aged ($59,197), Adult ($55,978) and Senior ($55,763).

## Business Recommendations

1. **Boost subscriptions:** Subscribers do not spend more, so add clear member benefits to make subscribing worthwhile.
2. **Run a loyalty program:** Reward repeat buyers and help Returning customers become Loyal.
3. **Review the discount policy:** Several products are discounted about half the time, so balance sales gains against margin.
4. **Highlight top-rated and best-selling products** in marketing campaigns.
5. **Target marketing** at the highest-revenue age groups and at express shipping users.

## Repository Structure

```
customer-shopping-behavior-analysis/
├── data/
│   └── customer_shopping_behavior.csv
├── notebooks/
│   └── data_preparation.ipynb
├── sql/
│   └── business_queries.sql
├── dashboard/
│   └── customer_behavior_dashboard.pbix
├── reports/
│   ├── project_report.pdf
│   └── presentation.pptx
├── images/
│   └── dashboard.png
└── README.md
```

## Author

**Mateti Greeshma**
Hyderabad, Telangana
GitHub: [github.com/Greeshma-27](https://github.com/Greeshma-27)
