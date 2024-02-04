# Lesson Context
This activity is meant to help me get better at understanding, explaining, and subsequently writing complex SQL queries. I am going to write documentation for a set of complex queries.

# Activity

## Query 1
```
WITH ranked_products AS (
    SELECT 
        p.ProductID,
        p.Name AS ProductName,
        p.Color,
        p.Size,
        p.Weight,
        p.ListPrice,
        s.OrderQty,
        ROW_NUMBER() OVER (PARTITION BY p.ProductID ORDER BY s.OrderQty DESC) AS rank
    FROM 
        Production.Product p
    JOIN 
        Sales.SalesOrderDetail s ON p.ProductID = s.ProductID
),
top_selling_products AS (
    SELECT 
        ProductID,
        ProductName,
        Color,
        Size,
        Weight,
        ListPrice,
        OrderQty
    FROM 
        ranked_products
    WHERE 
        rank = 1
)
SELECT 
    p.ProductID,
    p.Name AS ProductName,
    p.Color,
    p.Size,
    p.Weight,
    p.ListPrice,
    COALESCE(SUM(s.OrderQty), 0) AS TotalOrderQuantity,
    COALESCE(SUM(s.OrderQty * p.ListPrice), 0) AS TotalSalesRevenue
FROM 
    Production.Product p
LEFT JOIN 
    Sales.SalesOrderDetail s ON p.ProductID = s.ProductID
GROUP BY 
    p.ProductID,
    p.Name,
    p.Color,
    p.Size,
    p.Weight,
    p.ListPrice
ORDER BY 
    TotalSalesRevenue DESC
LIMIT 10;
```

### Answering questions about the Query:
- What do we want from this query?
We need to create a table for leadership that shows our top 10 best selling products ranked by their sales. Note: totalsalesrevenue is just listprice x totalorderquantity.

- What is the purpose of each Common Table Expression (CTE) used in the query?
 CTE: ranked_products gives us a table partitioned by Product ID and ranked by OrderQty. 
 This means we will get a temporary table we can work with later by taking only the Rank 1 order from each list of orders.
- How does the ROW_NUMBER() OVER function work and what does it achieve in this context?
ROW_NUMBER is a function that gives a unique sequential number to a partition.
Quick definition check: A partition is just a group of rows that share the same value in given column. 
When used with ROW_NUMBER you get a unique sequential number for every set of rows that share a given column value. 

See diagram:
<img width="1100" alt="Screenshot 2024-02-04 at 5 14 08 PM" src="https://github.com/ericbjames/Data_Engineering_Learns/assets/101911329/76a691ec-1c10-4723-a682-f9f89d578d97">


- What are the tables involved in the query, and what are their primary relationships?
Production.Product 
Sales.SalesOrderDetail
the temp table created in the CTE: top_selling_products

Production.Product has a one to many relationship with Sales.SalesOrderDetail through productid. ProductID is a PK in Product table but not a PK in SalesOrderDetail.

- How is the LEFT JOIN different from an INNER JOIN, and why is it used in this query?

- What does the COALESCE() function do, and why is it necessary in this query?

- How are the columns selected and aggregated in the final result set?

- What criteria are used to determine the top selling products?

- How is the final result set sorted and limited to only the top 10 products?

- What is the significance of each column selected in the final result set?

- How would you test and validate the correctness of this query's output?

- Are there any potential performance considerations or optimizations that could be made to this query?

- How would you modify this query to obtain different insights or metrics about the sales data?
