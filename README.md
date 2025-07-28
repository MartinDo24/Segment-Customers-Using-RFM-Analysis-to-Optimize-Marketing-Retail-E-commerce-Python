# RFM-customer-segmentation

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

### 👤 Who is this project for? 

-Marketing team

-Sales team

-Business Analysts/Management

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

-Remove duplicate value, handle missing value and oulier,convert columns to correct format 

<img width="563" height="697" alt="image" src="https://github.com/user-attachments/assets/3c9d7ea4-c657-4a26-9a26-dd368850c36d" />

<img width="1256" height="755" alt="image" src="https://github.com/user-attachments/assets/82a146e5-929e-4fcc-b694-cf695225bfb2" />

-Calculate RFM and divide numerical data into groups of equal size base on quantiles

<img width="587" height="407" alt="image" src="https://github.com/user-attachments/assets/2a3b13d6-a75f-4334-99da-78310b481663" />

<img width="637" height="353" alt="image" src="https://github.com/user-attachments/assets/b26dbcfd-d4d7-4842-b81b-6f30b46d4aac" />


2️⃣ Exploratory Data Analysis (EDA)

-Conducted an Exploratory Data Analysis (EDA) and RFM (Recency, Frequency, Monetary) analysis on a dataset of 541,909 e-commerce transactions (Dec 2010 - Dec 2011) using Python (pandas, numpy, seaborn, matplotlib, plotly)

-Dataset included key fields: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, and Country.

3️⃣ Python Analysis

-Identified skewed distributions: Recency showed recent purchases clustering, Frequency was low for most customers, and Monetary was driven by a few high-spenders.

-Top products like "MEDIUM CERAMIC TOP STORAGE JAR" and "JUMBO BAG RETROSPOT" dominated low and high CLV segments, respectively.

-Seasonal peaks (May-August) and post-seasonal drops (September-December) highlighted retention challenges.

-Visualization to show the key

<img width="1402" height="588" alt="image" src="https://github.com/user-attachments/assets/1c49cb10-0476-46c4-b017-748127da4e10" />

<img width="810" height="620" alt="image" src="https://github.com/user-attachments/assets/e5700233-bad1-4cbe-bbaa-5acd4e5428a3" />

<img width="1003" height="580" alt="image" src="https://github.com/user-attachments/assets/7935a2d3-9aed-4599-9808-928d2ce55863" />

<img width="1214" height="587" alt="image" src="https://github.com/user-attachments/assets/6a811031-7406-4027-bfb4-b3192bee7598" />

## 🔎 Final Conclusion & Recommendations

📌 Key Takeaways:

✔️ Recommendation 1: Focus on improving customer retention by targeting "Hibernating Customers" and "At Risk" segments with personalized discounts and re-engagement campaigns, prioritizing those with Recency > 90 days to reduce churn (400-600 affected customers).

✔️ Recommendation 2: Enhance marketing efforts by promoting high-value products like "JUMBO BAG RETROSPOT" to "Champions" and "Potential Loyalists" via social media campaigns, and introduce diverse high-CLV products to retain this segment.

✔️ Recommendation 3: Leverage seasonal trends by launching targeted promotions (e.g., Halloween, Christmas) from September to December to convert "New Customers" and "Promising" segments into "Loyal Customers," addressing the post-peak engagement drop.
