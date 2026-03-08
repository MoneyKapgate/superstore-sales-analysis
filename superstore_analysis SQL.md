-- **Create Database**

CREATE DATABASE superstore\_db;



-- **Use Database**

USE superstore\_db;



-- **Total Sales of the Company**

SELECT SUM(Sales) AS Total\_Sales

FROM superstore;



-- **Sales by Region** **of the company**

SELECT Region, SUM(Sales) AS Total\_Sales

FROM superstore

GROUP BY Region

ORDER BY Total\_Sales DESC;



-- **Sales by Category**

SELECT Category, SUM(Sales) AS Revenue

FROM superstore

GROUP BY Category

ORDER BY Revenue DESC;



-- **Top 10 Products by sales of the company**

SELECT 'Product Name', SUM(Sales) AS Revenue

FROM superstore

GROUP BY 'Product Name'

ORDER BY Revenue DESC

LIMIT 10;



-- **Monthly Sales Trend of the company**

SELECT MONTH('Order Date') AS Month, SUM(Sales) AS Total\_Sales

FROM superstore

GROUP BY Month

ORDER BY Month;



-- **Sales by Customer Segment**

SELECT Segment, SUM(Sales) AS Revenue

FROM superstore

GROUP BY Segment

ORDER BY Revenue DESC;





**-- Top 10 customers by total sales**

SELECT 'Customer Name', SUM(Sales) AS Total\_Revenue

FROM superstore

GROUP BY 'Customer Name'

ORDER BY Total\_Revenue DESC

LIMIT 10;





-- **Average shipping days**

SELECT AVG(DATEDIFF('Ship Date', 'Order Date')) AS Avg\_Shipping\_Days

FROM superstore;





-- **Top states by sales**

SELECT State, SUM(Sales) AS Total\_Sales

FROM superstore

GROUP BY State

ORDER BY Total\_Sales DESC

LIMIT 10;





-- **Top products in each category**

SELECT Category, 'Product Name', SUM(Sales) AS Revenue

FROM superstore

GROUP BY Category, 'Product Name'

ORDER BY Category, Revenue DESC;





-- **Most Used Shipping Mode**

SELECT 'Ship Mode',

COUNT(\*) AS Total\_Orders

FROM superstore

GROUP BY 'Ship Mode'

ORDER BY Total\_Orders DESC;



-- **Average Sales per Order**

SELECT AVG(Sales) AS Avg\_Order\_Value

FROM superstore;





