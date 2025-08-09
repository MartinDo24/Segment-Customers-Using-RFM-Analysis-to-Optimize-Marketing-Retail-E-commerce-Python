# Segment Customers Using RFM Analysis to Optimize Marketing – Retail E-commerce | Python

<img width="1000" height="597" alt="image" src="https://github.com/user-attachments/assets/9c0a1aeb-cd41-4491-ad98-1e3b9ce99f97" />


Author: Đỗ Hoàng Minh

Date: 2025-04-25

Tools Used: Python (google colab)

##📑 Table of Contents:

1.[📌Background & Overview](#-background--overview)

2.[📂 Dataset Description & Data Structure](#-dataset-description--data-structure)

3.[🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

## 📌 Background & Overview

###Objective:

###📖 What is this project about? 

-Performs RFM (Recency, Frequency, Monetary) analysis on e-commerce retail data to segment customers

-Aims to improve customer retention, purchase frequency, and customer lifetime value (CLV)

-Provides actionable marketing and sales strategies for a Superstore to target key customer segments

### Business problem
Retail/online business has a large number of customers but does not know which groups are high value, which groups are at risk of losing, which groups need to be reactivated. System: scattered marketing costs, low leg cost extraction, low advertising ROI. This project provides a process to:

-Classify customers by value (RFM)

-Tip marketing campaigns for each group

-Export the list to CRM/email tool for implementation

-Measure the level of improvement (added value) after the campaign

### 👤 Who is this project for? 

-Marketing team

-Sales team

-Business Analysts/Management

### What is RFM ? How RFM impact on business ?

-Recency (R): time since last purchase. Recent buyers are more likely to repurchase → prioritize upsell targets.

-Frequency (F): frequency of purchases over a period of time. Frequent buyers are loyal customers.

-Monetary (M): total spending value. Indicates how much revenue customers contribute.

-->Impact on business: RFM helps allocate marketing budget effectively (e.g. prioritize retaining Champions, reactivating At-Risk), optimize CPA/ROI, increase retention and CLV.

## 📂 Dataset Description & Data Structure

-Source: ecommerce retail.xlsx

-Size: 8 columns ~ 600k rows

### 📊 Data Structure & Relationships

#### 1️⃣ Tables Used

-Main table: ecommerce_retail

#### 2️⃣ Table Schema & Data Snapshot

| Column Name                      | Data Type 
|----------------------------------|-----------
| InvoiceNo                        | OBJECT    
| StockCode                        | OBJECT    
| Description                      | OBJECT  
| Quantity                         | INTEGER   
| InvoiceDate                      | DATE  
| UnitPrice                        | FLOAT   
| CustomerID                       | FLOAT   
| Country                          | OBJECT   


## ⚒️ Main Process :

1️⃣ Data Cleaning & Preprocessing

-Only get products with unitprice and quality having positive integer values

-Remove duplicate and missing values

-Convert Stock Code back to correct format to return to correct StockCode format 5 integers

<img width="245" height="29" alt="image" src="https://github.com/user-attachments/assets/4fccc3e3-45b1-44d2-8896-d54d92340208" />

<img width="565" height="302" alt="image" src="https://github.com/user-attachments/assets/d82979e0-781e-42cf-9ffb-e6436b5d421b" />

Technique:

-Choose the reference 2011-12-31. Get the most recent purchase date of each customer (max())

-Calculate the number of days from the most recent purchase to the reference date 

-Count the number of different bills (nunique()) for each customer

-Create column Monetary = quantity * unit price

-Sum the purchase value (sum()) for each customer

-Merge 3 tables Recency, Frequency, Monetary into one summary table.

-Divide each index into 5 groups (quintiles). Recency: high score = recent purchases. Frequency & Monetary: high score = frequent purchases & high value. Generate RFM codes in a string, for example 543 = Recency 5, Frequency 4, Monetary 3.

-Get the columns needed for analysis or visualization.

Operation:

-Recent indicates whether the customer has recently purchased. Low value → recent purchase, high probability of returning.

-Frequency indicates how often a customer purchases. High value → loyal or repeat customers

-Monetary shows the financial value that the customer brings. High value → the customer has great value to the business.

-Prepare data to classify customers according to RFM model.

-Allows to classify customers into different groups (VIP, potential, risk…).

-This is the RFM analysis results table, used to make marketing and customer care decisions.

<img width="761" height="459" alt="image" src="https://github.com/user-attachments/assets/c446f351-05c1-474e-9f08-546d9cc8016b" />


<img width="587" height="407" alt="image" src="https://github.com/user-attachments/assets/2a3b13d6-a75f-4334-99da-78310b481663" />


<img width="637" height="353" alt="image" src="https://github.com/user-attachments/assets/b26dbcfd-d4d7-4842-b81b-6f30b46d4aac" />


2️⃣ Exploratory Data Analysis (EDA)

- RFM Customer Segmentation: Count the number of customers in each Segment to evaluate the descriptive price and ability of each group. Helps identify VIP customers, new customers, abandoned customers, etc

- Relationship between recency and frequency: Use heat maps to observe trends: customers who buy frequently also have low Recency (i.e. recent interactions).

- Customer Percentage by Segment: The pie chart illustrates the percentage of each Segment group, supporting the balance of customer retention and expansion strategies

- Top 5 countries by number of customers and Segments: Identify key markets and Segment distribution levels in each country, serving localization marketing strategies

- Distribute Recency, Frequency, Monetary: Histogram + KDE helps understand purchasing behavior characteristics: most customers buy less often but a few contribute large revenue.

- Analyze Customer Lifetime Value (CLV): Calculate CLV = Frequency × Monetary, log-transform to reduce skewness. Group CLV into Low, Medium, High to prioritize high-value customer care resources

- Customer trends over time: Area chart shows the change in the number of customers in each Segment by month, helping to identify seasonality and the impact of marketing campaigns

- Top popular products by CLV group: Identify key products in each CLV group, supporting targeted cross-selling and up-selling.

3️⃣ Python Analysis

-Identified skewed distributions: Recency showed recent purchases clustering, Frequency was low for most customers, and Monetary was driven by a few high-spenders.

-Top products like "MEDIUM CERAMIC TOP STORAGE JAR" and "JUMBO BAG RETROSPOT" dominated low and high CLV segments, respectively.

-Seasonal peaks (May-August) and post-seasonal drops (September-December) highlighted retention challenges.

-Visualization to show the key

<img width="1402" height="588" alt="image" src="https://github.com/user-attachments/assets/1c49cb10-0476-46c4-b017-748127da4e10" />

<img width="810" height="620" alt="image" src="https://github.com/user-attachments/assets/e5700233-bad1-4cbe-bbaa-5acd4e5428a3" />

<img width="1003" height="580" alt="image" src="https://github.com/user-attachments/assets/7935a2d3-9aed-4599-9808-928d2ce55863" />

<img width="1214" height="587" alt="image" src="https://github.com/user-attachments/assets/6a811031-7406-4027-bfb4-b3192bee7598" />

-VIP customer group (R=5, F=5, M=5) accounts for a small proportion but contributes a large amount of revenue → is a key group that needs to maintain and develop relationships.

-New customer group (high R, low F, medium M) has growth potential if nurtured through good promotions and onboarding programs

-The group of customers who have left (low R, low F, low M) is at risk of being lost if there is no reactivation program

-The main markets (top 5 countries) account for the majority of revenue, while many other countries have very low revenue → focus marketing resources on the main markets to optimize ROI

-Best-selling products are different between low, medium, and high CLV groups → can use the main product of the high CLV group to upsell to the low/medium CLV group

-Seasonal purchasing trends (number of customers increases sharply in certain months) → opportunity to plan promotions at the right time

## 🔎 Final Conclusion & Recommendations

📌 Key Takeaways:

- Retain VIP groups
→ Create premium loyalty programs, special offers, and personalized care to maintain high revenue

- Increase purchase frequency for new customers
→ Apply cross-selling, early second purchase promotions, and email remarketing in the first 30 days.

-Reactivate abandoned customers
→ Send win-back emails, offer deep discounts, or introduce new products to attract them back

-Focus on key markets
→ Focus on advertising budgets and expand distribution channels in countries with high revenue

-Optimize seasonal marketing campaigns
→ Increase advertising budgets and launch campaigns during peak months

-Product strategy based on CLV
→ For low CLV groups, try selling best-selling products of high CLV groups to increase order value
