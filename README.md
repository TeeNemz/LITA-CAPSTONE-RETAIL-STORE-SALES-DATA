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


### DATA VISUALIZATIONS
---
#### MICROSOFT EXCEL INSIGHTS AND VISUALIZATIONS
 


   
