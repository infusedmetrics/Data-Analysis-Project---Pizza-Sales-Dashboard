# DataAnalytics-Projects / PIZZA SALES EXCEL VISUAL DASHBOARD 

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Results](#results)
- [Recommendations](#recommendations)

   

## Project Overview 

 Pizamo, a pizza franchise with a chain of 13 stores in the United Kingdom. I'm partnering up with the head of operations to extract insights and deliver recommendations to improve their performance in the sales, product and marketing team for one of their many stores across the country. Inisghts are delivered to operations and the product Manager.

 ## Executive Summary 
Key Findings:

Peak Sales Periods - The busiest days are Fridays and Saturdays, with the highest order volumes occurring during evening hours (4 PM – 8 PM) and lunchtime (12 PM – 1 PM).
Product Popularity - Large pizzas dominate sales, comprising 46% of total orders. Among the pizza categories, Classic Deluxe and BBQ Chicken generate the highest sales revenue.
Consumer Preferences - Weekend evenings attract the most customers, suggesting a strong trend in family and social dining occasions.
Pizamo can beneift from appling strategic marketing by enhancing marketing efforts during peak hours and days, especially Friday and Saturday evenings, to capitalize on high customer demand. Working on the product focus by expanding and promote popular items such as the Classic Deluxe and BBQ Chicken Pizza to drive sales further. Operational improvements to adjust staffing and inventory to align with peak sales periods.
By implementing these strategies, Pizamo can not only maximize revenue but also strengthen its competitive position in the market.

![image](https://github.com/user-attachments/assets/274d0663-ea93-4df2-81df-954c5fb2cd0d)





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


  
