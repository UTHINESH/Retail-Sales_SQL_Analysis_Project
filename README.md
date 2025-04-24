# Retail Sales SQL Analysis Project

This project focuses on analyzing a retail sales dataset using SQL. The analysis includes data cleaning, exploration, and answering real-world business questions. A basic stored procedure has also been added for dynamic data retrieval.

---

## 📁 Database & Table Created

The project uses a single table:

- **retail_sales**: Contains all transaction-level sales data, including:
  - `transaction_id`, `sale_date`, `sale_time`, `customer_id`, `gender`, `age`
  - `category`, `quantity`, `price_per_unit`, `cogs`, `total_sale`

---

## 🔧 Tasks Performed

### ✅ Data Cleaning
- Checked and removed rows with NULL values in important columns:
  - `transaction_id`, `sale_date`, `sale_time`, `gender`, `category`, `quantity`, `cogs`, `total_sale`

### ✅ Data Exploration
- Viewed sample data using `LIMIT`
- Counted total rows
- Listed unique product categories

### ✅ Data Analysis & Business Questions

Below are the key business questions answered using SQL queries:

1. **Sales on a Specific Date**
   - *"Get all sales made on 2022-11-05"*

2. **Category Sales with Quantity Filter**
   - *"Get Clothing transactions with quantity more than 4 in Nov 2022"*

3. **Total Sales by Category**
   - *"What are the total sales and total orders for each category?"*

4. **Customer Age Insight**
   - *"What is the average age of customers buying 'Beauty' products?"*

5. **High Value Transactions**
   - *"List all transactions where the total sale is greater than 1000"*

6. **Sales by Gender and Category**
   - *"Get total transactions grouped by gender and category"*

7. **(Skipped in SQL) — Reserved for future monthly sale trend analysis**

8. **Top Customers**
   - *"Who are the top 5 customers by total sales?"*

9. **Customer Count by Category**
   - *"How many unique customers purchased from each category?"*

10. **Sales by Shift**
   - *"Create sales shifts (Morning, Afternoon, Evening) and show order counts by shift"*

11. **Stored Procedure Usage**
   - *"How can we get all transactions for a specific product category using a stored procedure?"*

---

## 🧠 Stored Procedure

A basic stored procedure was created to retrieve all transactions for a given product category.

```sql
DELIMITER $$

CREATE PROCEDURE GetSalesByCategory(IN cat_name VARCHAR(50))
BEGIN
    SELECT * FROM retail_sales
    WHERE category = cat_name;
END$$

DELIMITER ;

-- Usage:
CALL GetSalesByCategory('Clothing');
