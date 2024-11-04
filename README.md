# LITA-CAPSTONE-RETAIL-STORE-SALES-DATA

## PROJECT TITLE: RETAIL STORE SALES
---

### PROJECT OVERVIEW
---
This Data Analysis project aims to generate insight into the sales performance of a Retail store. By analyzing the various parameters in the data received we seek to uncover key insights such as top-selling products, regional performance, and monthly sales trends, that can guide business decisions and foster growth.

### PROJECT OBJECTIVES
---
The primary objectives of this data analysis project are to:

- Understand Customer Preferences: Identify which Product categories, styles, and price points resonate most with customers.

- Analyze Sales Trends:Track sales trends across region,months and year to optimize inventory and marketing efforts with high-demand times.

- Optimize Inventory Management: Determine fast-moving and slow-moving items to ensure optimal stock levels, reducing overstock and stockouts.

- Customer Segmentation: Segment customers based on purchase patterns and demographics to personalize marketing and improve customer retention.

### DATA SOURCE
---
The primary source of Data used here is Sales data.xlsx and this is an open source data that was provided by the instructors of Ladies In Tech program, it can be freely downloaded from an open source online such as Kaggle or FRED or any other data repository site.

### DATA DESCRIPTION
---
The dataset includes the following fields:

- ORDER ID: A unique identifier for each individual order. This ID helps in tracking orders across different transactions, ensuring each sale or order is distinct

- CUSTOMER ID: A unique identifier for each customer.

-  PRODUCT: The name or ID of the product sold. There are 6 product category; Hat, Shoes, Jacket, Shirt, Socks, Gloves

- REGION: The region on which each product is been sold by different outlet ( North, South, East and South)

- ORDER DATE: The date on which the order was placed. 

- QUANTITY SOLD: The number of units of the product sold in each order. 

- UNIT PRICE: The selling price of each product

- TOTAL REVENUE: The total sales revenue generated from each order. It can be calculated as Quantity Sold * Price per Unit. This is essential for revenue analysis, profit calculations, and sales performance metrics.

  ### TOOLS USED
  ---
- Microsoft Excel 

1. For Data Cleaning
2. For Analysis
3. For Visualization
   
- SQL - Structured Query Language for querying of Data

- Microsoft Power Business Intelligence ( POWER BI) for Visualizations and creation of compelling insights

- Github for Portfolio Building

### DATA CLEANING AND PREPARATIONS
---
1. Data Cleaning
   - Using Microsoft Excel, all duplicated data were removed by going to the Data tab > Data tools > Remove duplicates
     
2. Data Importation
   - A copy of the cleaned data was converted to CSV flat and imported into SQL Server Management Studio 20
   - A copy of the cleaned data was also imported into Power BI, the  data was transformed and appropriate data types were chosen and applied
  
3. Data Visualization
 - In Microsoft Excel, Pivot tables were used to summarize the data and Bar charts were created to visually represent key insights.
 - In SQL Server Management Studio, codes were written to provide answers to research questions and screenshots of the output was taken.
 - In Power BI, several visualizations were made using Bar charts, tables, cards, Pie charts, Slicers, etc.

   
### EXPLORATORY DATA ANALYSIS
---
EDA involved the exploring of Data to answer some questions about the Data such as;

1. MICROSOFT EXCEL:
i. Using pivot tables to summarize 
- total sales by product
- total sales by region
- total sales by month.
ii. Use Excel formulas to calculate metrics such as average sales per product and 
total revenue by region

2. SQL: Codes were written to validate these queries
- retrieve the total sales for each product category.
- find the number of sales transactions in each region.
- find the highest-selling product by total sales value.
- calculate total revenue per product.
- calculate monthly sales totals for the current year.
- find the top 5 customers by total purchase amount.
- calculate the percentage of total sales contributed by each region.
- identify products with no sales in the last quarter.

3. POWER BI: Create a Dashboard that visualizes the insights found in Excel and SQL, the dashboard should include
- Sales overview
- Top-performing products, and 
- Regional breakdowns


### DATA ANALYSIS
---
This is where we include some basic lines of code or queries or even some of the DAX expressions used during your analysis;

1. SQL SERVER MANAGEMENT STUDIO 20 CODE/QUERIES

```SQL

SELECT * FROM [dbo].[Capstone Sales main]


SELECT Product, Sum(Quantity*unitprice) AS Total_sales
FROM [dbo].[Capstone Sales main]
GROUP BY Product


SELECT Region, Count(*) AS NumberOfTransaction
FROM [dbo].[Capstone Sales main]
GROUP BY Region


SELECT Top 1 product, Sum(Quantity*unitprice) AS Total_sales
FROM [dbo].[Capstone Sales main]
GROUP BY Product
ORDER BY Total_sales DESC



SELECT Top 5 Customer_id, Sum(Quantity*unitprice) AS Total_Purchase_Amount
FROM [dbo].[Capstone Sales main]
GROUP BY Customer_id
ORDER BY Total_Purchase_Amount DESC


SELECT Month(OrderDate) AS Month, Sum(Quantity*unitprice) AS Monthly_Sales
FROM [dbo].[Capstone Sales main]
WHERE Year(OrderDate) = Year(GetDate())
GROUP BY Month(OrderDate)
ORDER BY Month 

 
SELECT Region, sum(Quantity*unitprice) AS Total_sales,
sum(Quantity*unitprice) * 1.0/ (select sum(Quantity*unitprice)
FROM [dbo].[Capstone Sales main]) * 100 AS Percentage_Of_Total_Sales
FROM [dbo].[Capstone Sales main]
GROUP BY Region


SELECT Distinct Product
FROM [dbo].[SALES DATA SQL]
WHERE Product Not IN(
SELECT Product
FROM [dbo].[Capstone Sales main]
WHERE OrderDate >= DateAdd(quarter,-1,GetDate()) and OrderDate < GetDate())
```

### DATA VISUALIZATIONS
---
#### MICROSOFT EXCEL INSIGHTS AND VISUALIZATIONS


   
![excel sales by product](https://github.com/user-attachments/assets/8ea788e6-9f2f-4f12-8267-99b2b78e18e8)


![excel sales by region](https://github.com/user-attachments/assets/79016ae7-b624-40ca-a898-2b9244f88f60)


![excel sales by year](https://github.com/user-attachments/assets/f714263a-0773-4f0c-aabc-9746954986f5)


![excel quantity per year sales](https://github.com/user-attachments/assets/cb9a3518-04fc-4c46-8084-981f44ccf24d)



#### SQL CODES AND VALIDATED QUERIES
---


![SQL SALES](https://github.com/user-attachments/assets/14b02f27-c8ac-4956-b3cb-a18b02cfcd6c)


![SQL SALES 2](https://github.com/user-attachments/assets/039a8160-c7a2-4347-9bce-76d0f9f785b0)


![SQL SALES 3](https://github.com/user-attachments/assets/8d150f2e-8c06-43d2-9b6a-6ca990f554c9)


![SQL SALES 4](https://github.com/user-attachments/assets/ded86b8a-4bd6-4e8c-a1f8-190ac83f8aaf)


![SQL SALES 5](https://github.com/user-attachments/assets/dcadbe92-68a4-4c10-99e0-34eb88785c19)


![SQL SALES 6](https://github.com/user-attachments/assets/db127eed-a5eb-4080-a825-a02b264f11bc)


![SQL SALES 7](https://github.com/user-attachments/assets/9c4d06d2-7b24-43cc-99c0-07c55f6543fe)
