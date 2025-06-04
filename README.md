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

### 01-customer-insights.md

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

✅ Count so far: 10 / 37

### 📁 02-order-analysis.md

Display Order ID and the total amount of each order

List Orders with more than one Product and show number of products

List total dollar amount for each order that includes ProductID = 2

List total dollar amount for each order that includes Coffee Table

Create invoice for orders more than $2000, sorted by OrderID

For the most expensive products, display the order ID and customer name

✅ Running total: 16 / 37

### 📁 03-product-performance.md

Display average standard price for every product finish

For all ordered products, list product IDs, descriptions, and how many times ordered

List product ID, description, and price of products under avg standard price

List product ID, description, and price of underpriced products ordered more than once (sort by price)

Display the ProductFinish of products that appear in 3 or more orders

What quantity of each product finish has been ordered by customers whose postal code starts with 9 or ends with 4?

✅ Running total: 22 / 37

### 📁 04-sales-value-metrics.md

Retrieve the Product IDs and the total cost of each product in Order 1001

List Customer names and total amount spent per customer

Customers that placed orders: show customer ID, name, and order numbers (sorted by name)

Show customers with two or more orders

Retrieve customer ID and name that purchased products below average price

What are the customer states and their order IDs for orders with products over avg price?

✅ Running total: 28 / 37

### 📁 05-subqueries-and-exists.md

Customers that ordered “Natural Ash” finish and live outside CA (EXISTS)

Customer states and order IDs where order has product(s) > avg price (EXISTS)

Customers who ordered “Natural Ash” and live outside CA (EXISTS)

List customers who didn’t order or are in TX

Show description and total quantity of products with >3 quantity ordered and price > avg of product lines 1 & 2

✅ Running total: 33 / 37

### 📁 06-conditional-analysis.md

Names and addresses of Florida customers with total orders > $2000

Names of Florida customers with more than one order

For customers with one or more orders, display names and number of orders (JOINs)

Customers from FL or who ordered Cherry finish: retrieve order IDs, names, states, and order total

✅ Final Total: 37 / 37

✅ Summary
Category	Count
01-customer-insights.md	10
02-order-analysis.md	6
03-product-performance.md	6
04-sales-value-metrics.md	6
05-subqueries-and-exists.md	5
06-conditional-analysis.md	4
Total	37 ✅

