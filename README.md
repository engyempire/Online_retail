# Online_retail

## Overview:
 **This is a report for online retail**

 ---
 
## Contents
 [Project Overview](#Project-Overview) |+ [Data Source](#Data-Source) |+  [Tools Used](#Tools-Used) |+  [Table Outlay](#Table-Outlay) |+  [Query Languages)](#Query-Languages) |+  [Visualization](#Visualization)

---

## Project Overview:
> > This project analyzes a transactional data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail.

## Data Source:
https://archive.ics.uci.edu/

 ## Tools Used:
+	Pivot Table / Charts
+	PowerBI
+ SQL

  ## Table Outlay:

## Table Outlay:
First Three Records

|InvoiceNo	|StockCode	|Description	|Quantity	|InvoiceDate	|UnitPrice	|CustomerID	|Country
|----- | -----|----- |----- |----- |----- |----- |-----|
|536365	|85123A	|WHITE |HANGING HEART T-LIGHT HOLDER|	6	12/1/2010 |8:26|	2.55	|17850|	United Kingdom
|536365	|71053	|WHITE |METAL LANTERN	|6	12/1/2010| 8:26	|3.39|	17850|	United Kingdom
|536365	|84406B	|CREAM |CUPID HEARTS COAT HANGER|	8	12/1/2010 | 8:26|	2.75	|17850|	United Kingdom

## Query Languages
### SQL
Some of the query languages to retrieve records are displayed here

1SELECT CustomerID,
2       MAX(InvoiceDate) AS LastPurchase,
3       COUNT(InvoiceNo) AS Frequency,
4       SUM(Quantity * UnitPrice) AS Monetary,
5       CASE
6           WHEN SUM(Quantity * UnitPrice) > 2000 THEN 'High Value'
7           WHEN SUM(Quantity * UnitPrice) > 500 THEN 'Medium Value'
8           ELSE 'Low Value'
9       END AS Segment
10FROM OnlineRetail
11GROUP BY CustomerID
