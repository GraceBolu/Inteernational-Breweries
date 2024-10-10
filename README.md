# PROJECT TITLE: International Breweries sales performance between 2015 and 2017
## PROJECT OUTLINE
1.	[Project Overview](#project-overview)
2.	[Data Sources](data-sources)
3.	[Tools Used](tools-used)
4.	[Data Cleaning and Preparation](#data-cleaning-and-preparation)
5.	[Exploratory Data Analysis](#exploratory-data-analysis)
6.	[Data Analysis](#data-analysis)
7.	[Results/Findings](#results/findings)
8.	[Recommendations](#recommendations)

## Project Overview
## Data Sources:
## Tools Used:
- Structured Query Language - for data querying
- GitHub for report

## Data Cleaning and Preparation
- Data loading and Inspection
- Handling missing columns
- Data cleaning and formatting

## Exploratory Data Analysis
1. SALES PERFORMANCE
- What is the total cost price by year?
- What is the total sales revenue for each year?
- What is the total profit by year?
- What are the top 5 sales rep by total sales?
- What sales rep has the highest total sales?

2. GEOGRAPHIC ANALYSIS
- Which country has the highest sales revenue?
- What is the sales distribution by region?

3. PRODUCT ANALYSIS
- What brand has the highest sales quantity?
- What is the average unit price by brand?
- What brand has the highest profit?

4. TIME BASED ANALYSIS
- What is the monthly sales trend?
- Which quarter has the highest sales revenue?

## Data Analysis
1. SALES PERFORMANCE
- What is the total cost price by year?
  ```
  ALTER TABLE [dbo].[International Breweries]
  ADD Cost_Price bigint 

  UPDATE [dbo].[International Breweries]
  SET Cost_Price = Plant_Cost * Quantity

  SELECT Years, Sum(Cost_Price) AS Total_Cost_Price FROM [dbo].[International Breweries]
  GROUP BY Years
  ```
- What is the total sales revenue for each year?
  ```
  SELECT Years, Sum(Cost) AS TotalRevenue 
  FROM [dbo].[International Breweries]
  GROUP BY Years
  ```
- What is the total profit by year?
  ```
  SELECT Years, sum(Profit) AS Total_Profit FROM [dbo].[International Breweries]
  GROUP BY Years
  ```
- What are the top 5 sales rep by total sales?
  ```
  SELECT TOP 5 Sales_rep, sum(Cost) AS Total_Revenue FROM  [dbo].[International Breweries]
  GROUP BY Sales_rep
  ORDER BY Sum(Cost) DESC
  ```
- What sales rep has the highest total sales?
  ```
  SELECT TOP 1 sales_rep, sum(cost) AS Total_Sales from [dbo].[International Breweries]
  GROUP BY Sales_rep
  ORDER  BY 2 DESC
  ```