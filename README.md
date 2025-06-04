# DeskStoreSQL_37_Queries
37 explained SQL queries from Furniture Store database that sells primarily desks and tables

│   ├── 01-customer-insights
│   ├── 02-order-analysis
│   ├── 03-product-performance
│   ├── 04-sales-value-metrics
│   ├── 05-subqueries-and-exists
│   ├── 06-conditional-analysis

# SQL Portfolio: 37 Query Challenges

This project showcases 37 SQL queries written against a sample database of 4 tables. Each query solves a practical business question, using joins, aggregation, filtering, and advanced SQL features.

## 🗂️ Table of Contents

| #  | Question Summary                                 | Link                            |
|----|--------------------------------------------------|---------------------------------|
| 1  | Total spend per customer                         | [View](queries/01-customer-total-spend.md) |
| 2  | Top 5 most ordered products                      | [View](queries/02-top-products.md) |
| .. | ...                                              | ...                             |

## 🔍 Schema Overview

- `Customer_T`
- `Order_T`
- `OrderLine_T`
- `Product_T`

### 📁 01-customer-insights.md
Understand customer behavior, location trends, and engagement.

List all States with more than 2 customers per state

Retrieve names and state of customers not in FL, CA, or TX

Find how many customers are there in each state

Find states with two or more customers

List Customer ID and names for customers that did not place any order

For each Florida customer with less than 3 orders, show their names and order count

For each customer with less than 2 orders and outside CA and FL, show their names and order count

List customer names and states that either ordered products with less than average price or live outside NY, NJ, TX

Retrieve names and states of customers that have placed orders and are not in CA or TX

Display names of Florida customers with more than one order

🧠 Use for customer segmentation, targeting, and identifying under/over-engaged customers.

### 📁 02-order-analysis.md
Explore order characteristics, structure, and high-value thresholds.

Display Order ID and the total amount of each order

List Orders with more than one Product and show number of products

List total dollar amount for each order that includes ProductID = 2

List total dollar amount for each order that includes Coffee Table

Create invoice for orders more than $2000, sorted by OrderID

What are the customer states and their order IDs for orders with products over avg price?

For orders placed by FL customers or including Cherry finish, show order ID, name, state, and total

For the most expensive products, display the order ID and customer name

🧠 Use for invoice reporting, high-value order targeting, and cross-product analysis.

### 📁 03-product-performance.md
Measure product demand, pricing, and sales velocity.

Display average standard price for every product finish

For all ordered products, list product IDs, descriptions, and how many times ordered

List product ID, description, and price of products under avg standard price

List product ID, description, and price of underpriced products ordered more than once (sort by price)

Display the ProductFinish of products that appear in 3 or more orders

Show description and total quantity of products with >3 quantity ordered and price > avg of product lines 1 & 2

What quantity of each product finish has been ordered by customers whose postal code starts with 9 or ends with 4?

🧠 Use for inventory restocking, sales campaigns, or product bundling.

### 📁 04-sales-value-metrics.md
Track customer spend, product revenue, and order-level metrics.

Retrieve the Product IDs and the total cost of each product in Order 1001

Display order IDs and total amount of each order (duplicate prompt)

List Customer names and total amount spent per customer

Customers that placed orders: show customer ID, name, and order numbers (sorted by name)

Show customers with two or more orders

Retrieve customer ID and name that purchased products below average price

Total sales for orders including expensive products (via EXISTS or comparison)

🧠 Use to identify top spenders, optimize cross-selling, and understand sales distribution.

### 📁 05-subqueries-and-exists.md
Demonstrate advanced SQL logic using subqueries and EXISTS clauses.

List product ID, description, and price for products with < avg standard price

List product ID, description, and price for products with < avg standard price AND ordered more than once

List customer ID and name that bought products < avg standard price

Customers that ordered “Natural Ash” finish and live outside CA (EXISTS)

Customer states and order IDs where order has product(s) > avg price (EXISTS)

Customers who ordered “Natural Ash” and live outside CA (EXISTS)

List customers who didn’t order or are in TX

Customers who ordered products < avg price or live outside NY, NJ, TX (EXISTS)

🧠 Use for smart filtering, edge case detection, and advanced reporting filters.

### 📁 06-conditional-analysis.md
Apply conditional logic using WHERE, HAVING, and multi-state filters.

Names and addresses of Florida customers with total orders > $2000

Names of Florida customers with more than one order

For customers with one or more orders, display names and number of orders (JOINs)

For customers with < 2 orders outside CA and FL, show names and order count

Quantity of product finish ordered by customers whose postal code starts with 9 or ends with 4

🧠 Use for filtering edge groups, analyzing niche patterns, and developing location-based strategies.

### 📦 Summary Table of File Assignments
Category	# of Questions
01-customer-insights.md	10
02-order-analysis.md	8
03-product-performance.md	7
04-sales-value-metrics.md	7
05-subqueries-and-exists.md	8
06-conditional-analysis.md	5

