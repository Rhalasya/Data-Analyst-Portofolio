# Customer Churn Analysis Using MySQL

## Project Overview

This project analyzes customer churn using subscription data and customer transaction activity. The objective is to identify churned customers, calculate churn rate, analyze churn by subscription plan and province, segment churned customers by customer value, and identify active customers who are at risk of churn.

## Business Problem

A subscription-based business needs to understand which customers have stopped subscribing and which active customers are starting to show churn risk. This analysis helps the company prepare retention and win-back strategies.

## Churn Definition

In this project, customer churn is identified using the `status` column from the `subscriptions` table. In addition, customer inactivity is monitored using `last_transaction_date`.

The reference analysis date used in this project is:

```sql
'2024-01-31'
```

Active customers are considered **at risk** when they have not made transactions for a long period:

* `High Risk`: inactive for 90 days or more
* `Medium Risk`: inactive for 60–89 days
* `Low Risk`: inactive for 30–59 days

## Dataset

This project uses dummy customer subscription data.

| File                           | Description                                                     |
| ------------------------------ | --------------------------------------------------------------- |
| `data/mysql_customers.csv`     | Customer profile data                                           |
| `data/mysql_subscriptions.csv` | Subscription, transaction activity, and spending data           |
| `sql/project2_mysql_churn.sql` | MySQL script containing schema, insert data, queries, and views |

## Dataset Size

| Table         | Rows |
| ------------- | ---: |
| customers     |  200 |
| subscriptions |  200 |

## Database Tables

### customers

| Column              | Description                |
| ------------------- | -------------------------- |
| `customer_id`       | Unique customer ID         |
| `name`              | Customer name              |
| `email`             | Customer email             |
| `phone`             | Customer phone number      |
| `city`              | Customer city              |
| `province`          | Customer province          |
| `registration_date` | Customer registration date |
| `gender`            | Customer gender            |
| `age`               | Customer age               |

### subscriptions

| Column                  | Description              |
| ----------------------- | ------------------------ |
| `subscription_id`       | Unique subscription ID   |
| `customer_id`           | Customer ID              |
| `plan`                  | Subscription plan        |
| `monthly_fee`           | Monthly subscription fee |
| `start_date`            | Subscription start date  |
| `end_date`              | Subscription end date    |
| `status`                | Active or Churned        |
| `last_transaction_date` | Last transaction date    |
| `total_spent`           | Total customer spending  |

## Tools

* MySQL
* SQL
* GitHub

## Skills Demonstrated

* `CASE WHEN`
* Date functions: `DATEDIFF`, `DATE_FORMAT`
* CTE / `WITH` clause
* Subquery
* Self JOIN
* Aggregate functions
* SQL View
* Customer segmentation
* Churn rate analysis

## Analysis Performed

1. Customer churn labeling
2. Overall churn rate calculation
3. Churn rate by subscription plan
4. Churn rate by province
5. Monthly churn trend
6. Churned customer segmentation by value
7. At-risk active customer analysis
8. High-value churned customer identification
9. Spending comparison between active and churned customers
10. Reusable SQL views for churn monitoring


## Key Results

| Metric            |  Value |
| ----------------- | -----: |
| Total Customers   |    200 |
| Active Customers  |    136 |
| Churned Customers |     64 |
| Churn Rate        | 32.00% |


## Business Insight

Full business insight is available here:

[Business Insight Summary](insight/business_insight.md)

## Business Recommendations

* Prioritize high-value churned customers for win-back campaigns.
* Monitor active customers with more than 60 days of inactivity.
* Evaluate subscription plans with the highest churn rate.
* Track monthly churn trends to identify periods with high customer loss.
* Use SQL views to simplify recurring churn monitoring.

## Conclusion

This project demonstrates how SQL can be used to analyze customer churn from subscription and transaction activity data. The analysis helps businesses understand customer retention issues, identify high-risk customers, and develop data-driven retention strategies.

Through this project, SQL is used not only to retrieve data, but also to generate business insights related to customer behavior, churn risk, customer value, and retention priority.
