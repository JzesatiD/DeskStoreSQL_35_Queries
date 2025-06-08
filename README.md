# <center>Furniture Store: 35 SQL Requests</center>
This analysis of 35 queries leveraged SQL as the primary tool to explore a relational database representing a furniture store’s operations. SQL's power to perform complex joins, filtering, group-based aggregation, and subqueries made it ideal for answering layered business questions drawn from customer, order, product, and sales data.

## ERD (Entity Relationship Diagram) 
![ERD](https://github.com/JzesatiD/DeskStoreSQL_35_Queries/blob/main/assets/furniturestoreERD.png?raw=true)

## <center>Analysis</center>

### Why SQL Was Used for This Analysis

SQL enabled structured interrogation of the data to reveal insights across multiple levels of the business - from regional customer activity and order composition, to product demand patterns and revenue concentration. The language’s flexibility in combining data across multiple related tables (Customer, Order, OrderLine, Product) allowed for targeted business questions to be answered with clarity and precision.

### Business Insights Discovered
Through the use of SQL, several strategic findings were uncovered:

Customer Insights: Patterns emerged around where customers were concentrated, how engaged they were (based on order frequency), and which states showed untapped or declining activity. This surfaced opportunities for location-based re-engagement and more personalized outreach.

Order Composition and Value: Orders were not only analyzed by volume and contents, but also by spend thresholds — identifying high-value orders, frequently bundled products, and customers contributing the most revenue. This has direct implications for loyalty programs and sales forecasting.

Product Performance: SQL was instrumental in highlighting which product finishes were consistently lower or higher priced, and which products were most commonly ordered. These insights support pricing strategy, inventory planning, and marketing focus on best-sellers.

Revenue and Sales Metrics: Customer-level spend aggregation and per-order cost analysis made it possible to pinpoint top customers and high-performing SKUs. These findings guide customer prioritization and can help align marketing with profitability.

Advanced Filtering and Segmentation: Using subqueries and conditional logic, the analysis could surface nuanced customer groups — such as those who ordered premium products but reside outside major states, or those who have lapsed in engagement. These refined cohorts are critical for targeted campaign development.

## <center>Technical (SQL) Insights:</center>

It is helpful to think of a query request as broken down into its components and analyizing the language.
A typical query is in the form of:

_Display... Source... (GROUP)... Conditional..._

<center>Example: Show all orders from customers that are located in Texas</center>
&emsp;

**Display** → 
  **SELECT** OrderID

All action words, such as "retrieve," "list," and "show," etc. 

**Source** →
**FROM**: Customer_Table, Order_Table ...<br> 
_See later on cases where this clause is required._

Usually intuitive or comes easily from being familiar with the database.
We know that records of orders are in the order table, and customer data live in the designated customer table

**GROUP** → Explicit groups that require **GROUP BY** clause are sometimes distinguishable from keywords such as 'for each' or 'per'.

Our implicit group is the customers who placed orders but this does not require a **GROUP BY**<br> _See later on cases where this clause is required._

**Conditional** → **WHERE** CustomerState = 'TX' 

Common language: that __ , whose __ , that include(s) ___ , contain(s) ___ , a part / not a part of ___ , with ___ , more than/ less than ___ , etc. 

The condition or filter component is often the most challenging to get right the first time. 
This is because there are at least 3 methods for applying filters to look out for <br> (in order of least complex)<br>

A. Filtering by records using WHERE clause<br>
B. Filtering by groups using HAVING clause<br>
C. Utilizing Subqueries and operators such as EXISTS
_(see more on this later)_

With experience, one can distinguish common keywords or scenarios that provide cues to the necessity of implementing logic operators, comparison operators, JOIN operators, and even subquery. 

### Technical Observations:
1. A general tip, having a physical copy of the first 10 or so records of all tables will go a long way
2. A GROUP BY clause is required after the use of an AGGREGATE (ex. MAX, MIN, COUNT) in the SELECT clause
3. Aggregates in their natural form, can not be used in the WHERE clause. From the perspective of syntax, they must live in the HAVING clause since creating them in the SELECT results in a group
4. A subquery can be used to bypass the need for an additional JOIN
5. Sometimes, a subquery is required just for an aggregate to compare records because an aggregate can not be present in the WHERE clause in its natural form (see observation #2)
6. In a bind while working with subqueries, we can use a GROUP BY clause just as a precursor for accessing a necessary HAVING clause for filtering
7. In this dataset, customer data and product data are on opposite ends of the ERD. Thus, a question or query request that involves both will require joining all tables
8. It can be challenging to know during the 1st attempt of a query if a DISTINCT operator will be necessary. You probably can not go wrong with adding one whenever an aggregate is not present in the SELECT clause. In addition, being familiar with a handful of the records of the tables can also help
9. Outer joins can be helpful for including records that are not shared on both tables. Commonly with this dataset, we would like to include ALL customers in our Order analysis and an OUTER JOIN allows us to do this


  
### Compound Subqueries
These are often the most challening scenarios. Be sure to pace yourself with these types of problems and analyze the keywords from earlier.<br>
EXAMPLE: '___ with ___ that have' → Compound Subquery<br>


1. Ask yourself are the components within the SELECT clause compatible with the conditional demands I am required to implement at the individual records level? This alone could be a clue that a subquery is needed when our analysis shows the display components are separate from our filtering needs.<br>
_See above about nuances of the WHERE clause_<br>
2. Do I need to implement an aggregate at my record or entry filtering stage? 
3. Am I being asked to compare all records to the necessary conditions?

This mindset along with the other insights could help you solve these cases. 

### Summary
By leveraging SQL to model real business questions, this analysis demonstrated how raw transactional data can be transformed into decision-ready insights. Each query went beyond syntax — it addressed a tangible operational, sales, or marketing need. The process reflects what data analysts do in real-world roles: not just retrieve data, but uncover what matters and why it matters to the business.

## Queries Folder

- 01-customer-insights
- 02-order-analysis
- 03-product-performance
- 04-sales-value-metrics
- 05-subqueries-and-exists
- 06-conditional-analysis

### 📁 01-customer-insights.md

1. List all States with more than 2 customers per state

2. Retrieve names and state of customers not in Florida, California, and Texas

3. Find how many customers are there in each state

4. List Customer ID and names for customers that did not place any order

5. For each Florida customer with less than three orders, display their names and how Many times each customer placed orders

6. For each customer with less than 2 orders and outside California and Florida, display their names and how many times each customer placed orders

7. List customer names and states that either ordered products with less than average price or they are located in any state except NY, NJ, TX (EXISTS Operator)

8. Retrieve names and states of customers that have placed orders and are not located in California or Texas

### 📁 02-order-analysis.md

1. Display Order ID and the total amount of each order (each order may include multiple products)

2. List Orders with more than one Product and show number of products in each of these orders

3. List total dollar amount for each order that includes ProductID = 2

4. List total dollar amount for each order that includes Coffee Table

5. For orders more than $2000, create an invoice and show the total dollar amount of each order. Sort the result by orderID

6. For the most expensive products, display the order ID and customer name

### 📁 03-product-performance.md

1. Display average standard price for every product finish

2. For all ordered products, list product IDs, their description and the number of times each product has been ordered.

3. List product ID, description and price of products with less than average standard price of all products.

4. List product ID, description and price for products with less than average standard price that have been ordered more than once. Sort the result based on the product price. (Use subqueries)

6. What quantity of each product finish has been ordered by customers whose postal code starts with 9 or ends with 4? Show each Product finish along with its total quantity ordered.

7. List in alphabetic order the product finish and the average price for each product finish with the average price of less than 750.

### 📁 04-sales-value-metrics.md

1. Retrieve the Product IDs and the total cost of each product in Order 1001

2. List Customer names and total amount spent per customer

3. For all customers that have placed orders, display customer IDs, names and their order numbers. Sort the result based on customer names

4. Show customers with two or more orders. Include customer ID, name and number of orders.

5. Retrieve customer ID and name that purchased products below average price

### 📁 05-subqueries-and-exists.md

1. List customer names and states that ordered products with “Natural Ash” finish and are located outside California.

2. What are the customer states and their order IDs that include product(s) with more than the average standard price? (EXISTS)
Customers who ordered “Natural Ash” and live outside CA (EXISTS)

3. Retrieve name and IDs of customers that have not placed any orders or they are located in Texas. Sort the result based on the customer ID

4. Show description and total quantity of products that have been ordered a total of more than 3 quantity and are more expensive than the average price of product lines 1 and 2

### 📁 06-conditional-analysis.md

1. Display the names and addresses of Florida customers with total orders of more than $2000 value

2. Names of Florida customers with more than one order

3. For Customers with one or more orders, display their names and number of times they placed orders Customers from FL or who ordered Cherry finish: retrieve order IDs, names, states, and order total

4. For orders placed by customers from Florida or include products with “Cherry” finish, retrieve order IDs, Customer names, their state, and the total amount of orders

5. For each customer with less than 2 orders and outside of California and Florida, display their names and how many times each customer placed orders.

✅ Summary
Category	     &emsp;&emsp;&emsp;&emsp; Count

1. customer-insights.md	   &emsp;&emsp;&emsp; 8
2. order-analysis.md	    &emsp;&emsp;&emsp;&emsp;&emsp;6 
3. product-performance.md&emsp;&emsp;7
4. sales-value-metrics.md&emsp;&emsp;&emsp;5
5. subqueries-and-exists.md&emsp;&emsp;4
6. conditional-analysis.md&emsp;&emsp;&emsp;5

Total &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;  35 
