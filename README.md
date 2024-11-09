# Sales_Data
For the past three months I've been involved in intensive data analysis training on microsoft excel, Sql (Stuctured Query Langue) and Power BI. Each data analysis tool we were trained lasted for four weeks respectively. The facilitators were very relatable and were readily responsive to our questions. I especially enjoyed every class but most particularly the POWER BI sessions. As a requirement for advanced training, I have been tasked with a project known as the LITA CAPSTONE PROJECT to present all I've learnt thus far.

# Project Overview
In this project, a Sales data for a retail store is analyzed to find sales performance in determining key insights such as top performing products, regional performance and sales trends. Many tools were used to determine this. The project's goal is to make logical suggestions for how to maximize sales performance across all regions of the retail store.

# Data Sources
The primary source of data used here is LITA Capstone Dataset_27027859 and this is a source that was provided for by the Incubator Hub Data Analysis Instructors.

# Tools Used
Microsoft Excel: This tool was used for
Data Cleaning
summarize Analysis(Pivot Table)
Visual representation using pivot charts and Graphs
SQL- Structured Query Language:
Running Queries
Validating Queries
PowerBI:
Creating Dahsboard for visualizations for interactive Presentations
Github for Portofolio Building
Data Cleaning and Preparations

# Steps taken for the Data cleaning and Preparation;
Data Loading and inspection
Removal of Duplicates
Data Formatting
Identify and document missing values
Checking column quality
Tranform Data

# Exploratory Data Analysis
This involves the exploring of the Data to answer some question such as; -
Total sales in each region,
Average sales by each region, 
Average sales by Product,
Top selling product, 
Best sales region,
# Data Analysis
Below is the sturctured query language I used to analyse the sales data for the retail store
create database oluwatoblib_db
select * from [dbo].[book3]
---retrieve total sales for each product category---
select product, sum(Total_Sales) as TotalSales from [dbo].[book3]  group by product
---number of sales transactions in each region---
select region, count(*) as numberofsalestransaction from [dbo].[book3] group by region 
---highest selling product by total sales values---
select top 1 product, sum(Total_Sales) as HighestSellingProduct from [dbo].[book3] group by Product order by 2 desc
---total Revenue per product---
select product, sum(total_sales) as TotalRevenue from[dbo].[book3] group by product
---monthly sales total for the current year---
select FORMAT(OrderDate, 'yyyy-mm') as sales_month, sum(Total_Sales) as monthly_sales_total
from [dbo].[book3] where YEAR(OrderDate) = 2024 group by FORMAT(OrderDate, 'yyyy-mm')
order by FORMAT(OrderDate, 'yyyy-mm')
---top 5 customers by total purchase amount---
select top 5 Customer_ID, sum(Total_Sales) as TotalPurchase from [dbo].[book3] group by Customer_Id 
order by 2 desc
---percentage of total sales contributed by each region---
select
      YEAR(OrderDate) AS SalesYear,
	  MONTH(OrderDate) AS SalesMonth,
	  SUM(Total_Sales) AS TotalSales
From [dbo].[book3]
Where Year(OrderDate) = YEAR(GETDATE())-----Filter from the current year
Group by YEAR(OrderDate), MONTH(OrderDate) Order by SalesYear, SalesMonth;
 ---Products with no sales in the last quarter---
select product from [dbo].[book3] group by product having 
sum(case when OrderDate >= '2024-01-01' and OrderDate < '2024-04-01'
then 1 else 0 end) = 0; -- Q1 of 2024


# Data Visualization
![sales excel](https://github.com/user-attachments/assets/e43e029a-079f-4bb4-b032-444a90173406)




![sql sales](https://github.com/user-attachments/assets/98af7a9f-6d97-49a8-9abe-240698b785ef)



![sales power bi](https://github.com/user-attachments/assets/d2f9ae16-02cf-4407-9623-f04bf0e5b37f)



