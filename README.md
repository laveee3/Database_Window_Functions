# 🍽️ Restaurant Loyalty Program SQL Analysis  

This project contains solutions to a series of SQL questions related to a restaurant's loyalty program. The dataset includes three tables:  
- **members** – information about customers and their membership join dates  
- **sales** – purchase history of customers  
- **menu** – menu items and their prices  

The objective is to analyze customer spending habits, menu popularity, and loyalty program performance.

---

## **Dataset Structure**

### `members` table  
| customer_id | join_date  |
|-------------|------------|
| A           | 2021-01-07 |
| B           | 2021-01-09 |

### `sales` table  
| customer_id | order_date | product_id |
|-------------|------------|------------|
| A           | 2021-01-01 | 1          |
| B           | 2021-01-04 | 2          |

### `menu` table  
| product_id | product_name | price |
|------------|--------------|-------|
| 1          | sushi        | 10    |
| 2          | curry        | 15    |

---

## **Questions & Solutions**

1️⃣ What is the total amount each customer spent at the restaurant?
Query:
```sql
SELECT m.customer_id, SUM(price) AS total_spent
FROM members m
JOIN sales s ON m.customer_id = s.customer_id
JOIN menu ON s.product_id = menu.product_id
GROUP BY 1;

2️⃣ How many days has each customer visited the restaurant?

3️⃣ What was the first item purchased by each customer?
Uses a window function to identify the first purchase

4️⃣ What is the most purchased item on the menu and how many times was it purchased?

Advanced Questions
The later queries explore:
Customers' favorite items
Items purchased before and after joining the loyalty program
Points earned based on spending and bonus rules

Key Concepts Used
- Joins (INNER JOIN) to combine tables
- Aggregate functions (SUM, COUNT)
- Window functions (ROW_NUMBER, RANK)
- CASE statements for conditional logic
- CTEs (WITH clauses) for query readability

How to Run
Load the members, sales, and menu tables in any SQL database (e.g., PostgreSQL, MySQL, SQLite).
Run each query in sequence to get results for the respective questions.


#-----------------------  Code named SQL window functions --------------------#

# 📊 SQL Practice Problems – Window Functions, Aggregations & Joins  

This repository contains a collection of **advanced SQL problems** inspired by YouTube tutorials and interview-style questions.  

The focus is on:  
- Window Functions (ROW_NUMBER, DENSE_RANK, NTILE, LEAD, LAG, etc.)  
- Aggregations and Grouping  
- Self-Joins  
- Cumulative and Moving Averages  
- Top-N problems

2️⃣ Find Employees Who Earn More Than Their Managers (Self-Join)
3️⃣ Create a Histogram of Ages Using FLOOR()
4️⃣ Find the Nth Most Experienced Employee (DENSE_RANK)
5️⃣ Calculate a 7-Day Moving Average of Sales
6️⃣ Using FIRST_VALUE() and LAST_VALUE()
7️⃣ LEAD/LAG Window Functions
8️⃣ NTILE() – Divide Scores into Quartiles
9️⃣ Cumulative Sum
🔟 Top 10 Records for Each Category
1️⃣1️⃣ Top 10 Customers by Day/Week/Month
1️⃣2️⃣ Find the 3rd Purchase of Each User
1️⃣3️⃣ Find the Highest Sale for Each Day
