# LITA-CAPSTONE-RETAIL-STORE-SALES-DATA

## PROJECT TITLE: RETAIL STORE SALES
---

## TABLE OF CONTENT
---

[PROJECT OVERVIEW](#Project-overview)

[PROJECT OBJECTIVES](#Product-Objectives)

[DATA SOURCE](#Data-source)

[DATA DESCRIPTION](#Data-description)

[TOOLS USED](#Tools-used)

[DATA CLEANING AND PREPARATIONS](#Data-cleaning-and-preparations)

[EXPLORATORY DATA ANALYSIS](#Exploratory-data-analysis)

[DATA ANALYSIS](#Data-analysis)

[KEY INSIGHTS AND INFERENCE](#Key-insights-and-inference)

[SUGGESTIONS](#Suggestions)

[CONCLUSION](#Conclusion)




### PROJECT OVERVIEW
---
This Data Analysis project aims to generate insight into the sales performance of a Retail store. By analyzing the various parameters in the data received we seek to uncover key insights such as top-selling products, regional performance, and monthly sales trends, that can guide business decisions and foster growth.

### PROJECT OBJECTIVES
---
The primary objectives of this data analysis project are to:

- Understand Customer Preferences: Identify which Product categories, styles, and price points resonate most with customers.

- Analyze Sales Trends: Track sales trends across region,months and year to optimize inventory and marketing efforts with high-demand times.

- Optimize Inventory Management: Determine fast-moving and slow-moving items to ensure optimal stock levels, reducing overstock and stockouts.

- Customer Segmentation: Segment customers based on purchase patterns and demographics to personalize marketing and improve customer retention.

### DATA SOURCE
---
The primary source of Data used here is Sales data.xlsx that was provided by the instructors of  Incubator hub for the Ladies In Tech program.


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

1. Microsoft Excel (Ms Excel)

- Revenue column was added and calculated using this function

```
   =Revenue (Unit Price * Quantity)
```
- Metrics such as Average sales per product and total revenue by region where calculated

Example for Average sales of shirt:

```
 =AVERAGEIFS(H2:H9922, C2:C9922,M6)
```

2. Structured Query Language

The following queries were written to analyse the sales performance


```SQL

SELECT * FROM [dbo].[Capstone Sales main]
```
a. Retrieve the total sales for each product category:
```

SELECT Product, Sum(Quantity*unitprice) AS Total_sales
FROM [dbo].[Capstone Sales main]
GROUP BY Product

```
b. Find the number of sales transcations in each region:
```

SELECT Region, Count(*) AS NumberOfTransaction
FROM [dbo].[Capstone Sales main]
GROUP BY Region

```
c. Find the highest selling product by total sales value:
```

SELECT Top 1 product, Sum(Quantity*unitprice) AS Total_sales
FROM [dbo].[Capstone Sales main]
GROUP BY Product
ORDER BY Total_sales DESC

```
d. Calculate total revenue per product:
```

Select Product, sum(Quantity*unitprice) as Total_revenue
From [dbo].[Capstone Sales main]
Group By Product

```
e. Find the top 5 customers by total purchase amount:
```

SELECT Top 5 Customer_id, Sum(Quantity*unitprice) AS Total_Purchase_Amount
FROM [dbo].[Capstone Sales main]
GROUP BY Customer_id
ORDER BY Total_Purchase_Amount DESC

```
f. Calculate monthly sales totals for the current year:
```

SELECT Month(OrderDate) AS Month, Sum(Quantity*unitprice) AS Monthly_Sales
FROM [dbo].[Capstone Sales main]
WHERE Year(OrderDate) = Year(GetDate())
GROUP BY Month(OrderDate)
ORDER BY Month

```
 g. Calculate the percentage of total sales contributed by each region:
```

SELECT Region, sum(Quantity*unitprice) AS Total_sales,
sum(Quantity*unitprice) * 1.0/ (select sum(Quantity*unitprice)
FROM [dbo].[Capstone Sales main]) * 100 AS Percentage_Of_Total_Sales
FROM [dbo].[Capstone Sales main]
GROUP BY Region

```
h. Identify products with no sales in the last quarter:
```

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


#### POWER BI INSIGHTS AND VISUALIZATIONS

A Dashboard that visualizes the insights found in excel and SQL.
The dashboard include sales overview, top performing products, regional and yearly breakdown



### KEY INSIGHTS AND INFERENCE:

i.  Product Performance:

It was observed that the product 'Shoes' yielded the highest total sales revenue of $613,380, followed by Shirt ($485,600), Hat ($316,195), Gloves ($296,900), Jacket ($208,230) with Socks being the lowest with a total sales revenue of $180,785. The reasons for this could be related to the following;

- Frequency of Use: Shirts and shoes are everyday essentials. People tend to wear shirts regularly, often needing multiple options for different occasions, while shoes can also vary based on style, activity (like running vs. casual), and season.
  
- Climate, Comfort and Fit: Consumers often prioritize comfort in clothing choices. Well-fitting shirts and comfortable shoes are crucial for daily wear, whereas items like jackets and gloves might not be needed as frequently, depending on the climate.

- Versatility: Shirts and shoes are often more versatile and can be worn in a variety of settings. A good shirt can be dressed up or down, making it suitable for casual outings, work, or formal events. Similarly, shoes, especially styles like sneakers or loafers, can complement a wide range of outfits and occasions.

- Fashion Trends: Shirts, being a staple item in most wardrobes, are frequently updated with new styles, colors, and patterns. Footwear trends also evolve, leading to increased consumer interest and purchasing frequency for shoes.

- Price Points: Shirts and shoes can be found in a wide range of price points, making them accessible to a broader audience. This accessibility can encourage more purchases, as customers feel they can find options within their budget.

- Seasonal Demand: Shirts and shoes can be purchased year-round, While jackets and gloves are typically seasonal items. This continual demand keeps sales consistent, unlike more seasonal items that may see spikes in specific months.

ii. Region Performance:

It was observed that the region with the highest sales was South ($927,820) followed by the East ($485,925), North ($387,000) with the West having the lowest with a revenue of $300,345. The Sales performance in these regions can be attributed to several factors:

- Population Density and Urbanization: In Nigeria, The South and East regions include highly populated and urbanized regions such as Lagos, Rivers, and Abia. These areas have larger consumer bases with increased purchasing power, resulting in higher sales for everyday items like shirts and shoes.
  
- Economic Activities and Disposable Income: The Southern and Eastern regions have strong economic activities asa result of being the center for commerce and proximity to sea port, they are aslso home to several oil wells, trade, and manufacturing industries, particularly around Rivers, Lagos and Ogun. These industries contribute to higher average disposable incomes, allowing consumers to spend more on apparel and fashion products. As people in these regions often have more disposable income, they are more likely to purchase items beyond basic needs, including trendy or high-quality clothing and accessories.

- Infrastructure and Retail Presence: The South and East regions have more developed retail infrastructure, including shopping malls, boutiques, and e-commerce delivery services, making it easier for customers to access and purchase clothing items.

- Climate and Seasonal Demand: Nigeria has a generally warm climate, but the South and East experience relatively more rainfall. This drives demand for certain items like shoes and hats that can be used year-round, while demand for items like jackets might be more seasonal. In contrast, the North tends to be hotter and drier, with less demand for items like jackets or gloves.

- Fashion Trends and Social Influence: The Southern and Eastern regions, especially urban centers like Lagos, are known for their vibrant fashion scenes. Influencers, celebrities, and local trends drive higher demand for stylish clothing items.
  

iii. Monthly trends:

It was observed that February has the highest revenue in both 2023 and 2024, with a revenue of $247,500 and $288,800 for 2023 and 2024 respectively. 
This can be attributed to Post-Holiday Sales. Many retailers run clearance and discount events to move leftover inventory from the holiday season, hence attracting bargain hunters.

Additionally, new spring collections may be launching thus sparking fresh interest. Also Valentine Day is in February, Apparel is often a popular gift choice for Valentine's Day, boosting sales of items like shirts, hats, and socks.


### SUGGESTIONS

- A combo deal of Shoes and socks can be initiated to  help improve the sales of socks.



### CONCLUSIONS
In summary, population density, economic strength, fashion trends, retail infrastructure, and cultural practices all contribute to the higher sales performance of clothing items in Nigeria's South and East compared to the West and North.
