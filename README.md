# Zepto SQL Data Analysis Project  

## 📖 Overview  
This project simulates how data analysts in the e-commerce industry use SQL for:  
- Setting up and cleaning real-world inventory data  
- Performing exploratory data analysis (EDA)  
- Deriving business insights to support decision-making  

Dataset was sourced from Kaggle and represents product listings from **Zepto**.  

---

## 🗂️ Dataset Details  
- **sku_id**: Unique identifier  
- **name**: Product name  
- **category**: Product category (Snacks, Fruits, etc.)  
- **mrp**: Maximum Retail Price (₹)  
- **discountPercent**: Discount applied  
- **discountedSellingPrice**: Final selling price  
- **availableQuantity**: Stock available  
- **weightInGms**: Product weight  
- **outOfStock**: Availability flag  
- **quantity**: Units per package  

---

## 🔧 How to Use This Project  

1. Clone this repository  
   ```bash
   https://github.com/harshith949/zepto-sql-analysis

2. Open zepto_sql_analysis.sql in your SQL client (PostgreSQL / pgAdmin).

Create the table using the provided SQL script.

Import the dataset (zepto_v2.csv).

Run the queries step by step for:

Data cleaning

Exploratory data analysis

3.Business insights

📊 Business Insights Derived

Top 10 products by highest discount

Categories with maximum revenue potential

Out-of-stock high-value products

Average discount % by category

Price-per-gram comparison to find best value
