# SQL-DataAnalytics-Projects / PIZZA SALES 

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Results](#results)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
   

## Project Overview 

The Pizza Sales Data Analyst project focuses on analyzing sales data and performance of a pizza business over the past year. By analysing various apects the data, we can leverage these findings to make data driven recommendations and gain a deeper understanding of the company's performance.

![Screenshot 2024-12-07 180823](https://github.com/user-attachments/assets/fd716e3d-b1b2-4878-859c-6a17b9442bd9)




## Data Sources

Pizza Sales Data: The primary Dataset used for this anyalsis is the 'Pizza_Sales.csv' containing detailed information on each sale made by the business for the year.

## Tools

- Excel - Data Cleaning
- SQL Server - Data Analysis
- Excel - Visual Dashboard


### Data Cleaning/Preparation

In the initial Data preparation phase, we performed the following tasks:
1. Data Loading and Inspection
2. Handling Missing Values
3. Data cleaning and formatting


### Exploratory Data Analysis

EDA involved exploring Pizza Sales Data to answer Key questions, such as:
- what is the overall sales trend?
- what pizza size/category are the top sellers?
- what pizza size/category are the worst sellers?
-  when are the peak sales period? Hourly/Daily/Quarterly

### Data Analysis 

These are some examples of the code I've written to query the data to get some insights.

Query for the Hourly trend of orders made.

```sql
SELECT DATEPART(HOUR, order_time) as order_hours, COUNT(DISTINCT order_id) as total_orders
from pizza_sales
group by DATEPART(HOUR, order_time)
order by DATEPART(HOUR, order_time)
```

Query for percentage of Sales by Pizza size

```sql 
SELECT pizza_size, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
FROM pizza_sales
GROUP BY pizza_size
ORDER BY pizza_size
```


### Results   

The analaysis results are summarised as follows:
1. Daily trend shows that the highest number of orders made on a given week is on a Friday.
2. Hourly Trend indentified and shows the most pizza's sold on a given day is around 12pm-1pm & 4pm-8pm.
3. Pizza Product Category: Classic Deluxe and BBQ Chicken pizza's contribute to maximum sales and orders with the highest percentage.
4. Pizza Product Category: The Brie Carre Pizza's have contributed the least amount of orders and revenue.
5. Pizza Size: Large Pizza is the highest contributer to mamimum sales.

### Recommendations 

Based on the analysis, we recommend the following actions:
- Invest in marketing and promotions during peak hours and days to maximise revenue.
- Focus on expanding and promoting products like Classic Deluxe and BBQ Chicken Pizza.
- Implement a customer segmentation strategy to target High-LIV customers effectively.


  
