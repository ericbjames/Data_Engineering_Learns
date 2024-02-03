# Lesson Context
This activity is meant to help me get better at understanding, explaining, and subsequently writing complex SQL queries. I am going to write documentation for a set of complex queries.

# Activity

## Query 1
"""
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
"""

### My Documentation

wip