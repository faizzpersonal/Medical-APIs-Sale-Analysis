[![Open In Power Bi](https://img.shields.io/badge/open_in_power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiMWY1YzM2YzgtZmFiYi00ZjI1LWJjYmQtNjViYjMxYWM5ZmNjIiwidCI6IjM0YmQ4YmVkLTJhYzEtNDFhZS05ZjA4LTRlMGEzZjExNzA2YyJ9)  

# Medical APIs Sales Analysis
In this ‘Data Analysis’ project, we’ll analyze the sales data of a Medical API (Active Pharmaceutical Ingredient) Manufacturing Company to extract meaningful insights.

## Features

- **Power Query Editor**: Utilized for data transformation and modeling, ensuring the data is clean, structured, and ready for analysis.
- **Power BI Service**: Enables online access to the report without requiring a Power BI login, making it easily shareable and accessible.
- **Multi-page, Fully Interactive Report**: Designed to generate insights and analysis through a user-friendly interface, allowing for in-depth exploration of data across multiple dimensions.


## Table of Contents
- [Introduction](#introduction) 
- [Objective](#objective)
- [Dataset](#dataset)
- [Prerequisites](#prerequisites)
- [Report Creation](#report)
- [Deploy](#deploy)
- [License](#license)


## Introduction
In this Data Analysis project, we focus on the sales data of a leading Medical API (Active Pharmaceutical Ingredient) Manufacturing Company. APIs are the critical components of pharmaceuticals, responsible for the therapeutic effects of medications. Understanding the sales patterns, trends, and performance metrics within this sector is vital for strategic decision-making, market positioning, and operational efficiency.

Through detailed analysis, we aim to uncover key insights that will shed light on sales performance, regional distribution, product demand, and customer behavior. 

## Objective

The primary objective of this project is to analyze the sales data of a Medical API (Active Pharmaceutical Ingredient) Manufacturing Company to uncover actionable insights that can drive strategic decision-making. By leveraging Power BI's advanced data transformation, modeling, and visualization capabilities, we aim to:

1. **Identify Key Sales Trends and Patterns**: Analyze sales performance across different regions and products.
2. **Monthly and Yearly Change Analysis**: Track sales performance over time, highlighting significant growth or decline periods.
3. **Top 5 Best-Selling Drugs**: Rank and analyze the top 5 drugs to understand their market performance and contribution to overall sales.
4. **Interactive Power BI Report**: Enable stakeholders to explore the data interactively through a comprehensive, multi-page Power BI report that is accessible online without requiring a Power BI login.


***Table-1 : Requirements***

## Dataset
There are three different table linked with primary key, `CustomerTable.csv`,`DrugLookup.csv`,`FactTable.csv`, Can be downloaded from Dataset folder present in repository.

***Table-1 : CustomerTable***

|Field|Description|
|:---|:--|
|CustomerID| Unique identifier for each customer|
|Age| Age of customer|
|Gender| Gender of customer|
|Country| Customer's country|
|FullName| Name of customer|
|Age Bin| Age group classification based on age ranges|

***Table-2 : DrugLookup***

|Field|Description|
|:---|:--|
|DrugID| Unique identifier for each drug|
|DrugName| Name of the drug|
|RegulatoryComplianceID| Identifier for regulatory compliance|
|UnitSalesPrice| Sales price per unit|
|CostOfProduction| Cost to produce the drug|

***Table-3 : FactTable***

|Field|Description|
|:---|:--|
|SaleID| Unique identifier for each sale|
|CustomerID| Unique identifier for each customer|
|UnitsSold| Number of units sold|
|SaleDate| Date of the sale|
|BuyerType| 	Type of buyer (e.g., buyer, seller)|

## Prerequisites

### Exploratory Data Analysis (EDA) [pandas]
To understand, be familiar with and check the sanity of the given data, the first step is EDA. This project's initial data exploration has been carried out using the `pandas` python package. Here, in general, we are checking... 
 * Presence of any missing values 
 * Any unusual value (outliers) 
 * Incorrect values
 * Determine `categorical` and `numeric` columns
 * Determine dimensions of categorical columns and range of numeric columns
Note that these steps can be performed using `PowerQuery Editor` and/or excel; however, `pandas` makes it much easier and faster; on top of that, `pandas` can handle massive datasets.

EDA steps can be found in the `Medical APIs Sales Data EDA.ipynb` notebook.


### Data Cleaning and Transform [PowerQuery Editor]
The provided dataset was relatively clean and well organized; hence only a little work was required in this step; the following steps were carried out.

### Data Model Creation [Power BI Desktop]

In this phase, we create a data model in Power BI Desktop using the provided dataset, which consists of three interconnected tables. The tables are linked based on specific keys to ensure accurate data relationships and facilitate meaningful analysis:

1. **Tables and Relationships**:
   - **`CustomerTable.csv`**: Contains customer details and is linked to the `FactTable.csv` using the `CustomerID` field.
   - **`DrugLookup.csv`**: Contains drug-related information and is linked to the `FactTable.csv` using the `DrugID` field.
   - **`FactTable.csv`**: Records sales transactions and serves as the central table, linking to both the `CustomerTable.csv` and `DrugLookup.csv` tables.

2. **New Date Table**:
   - A new **Date Table** is created to handle time-based analysis and support DAX queries. This table allows for more sophisticated date filtering and aggregation in the reports.

By establishing these relationships and incorporating the Date Table, we ensure that the data model supports comprehensive analysis and reporting capabilities, enabling insights into sales trends, customer demographics, and drug performance.

<img width="1034" alt="Screenshot 2024-08-14 at 11 11 35 AM" src="https://github.com/user-attachments/assets/70e4e2b5-20b5-401f-ada5-c89343d112c3">

## Report

The Power BI report is meticulously crafted across three distinct pages, each designed to offer comprehensive insights into various aspects of the sales data:

1. **Main Page**:
   - **Monthly Metrics**: This page provides a detailed overview of key metrics on a monthly basis. It includes data on quantity sold, cost of goods sold (COGS), revenue, and profit. Additionally, it features a comparison of these metrics with the previous month, allowing users to easily identify trends and changes in performance over time.
   - **Top N Revenue-Generating APIs and Customers**: Highlights the top N APIs and customers contributing the most to revenue. This helps in identifying high-value areas and clients.
   - **Filters**: Users can apply filters for selecting specific months and years, enabling them to customize the view according to their needs and focus on particular time periods.
     
<img width="1242" alt="Screenshot 2024-08-14 at 12 28 47 PM" src="https://github.com/user-attachments/assets/1f1a0d5b-3205-42a7-8b87-4d5d5d7f479e">

<img width="1239" alt="Screenshot 2024-08-14 at 12 35 16 PM" src="https://github.com/user-attachments/assets/8ee842b2-6f66-416b-8a2a-32d469cf4abc">


2. **Customer Page**:
   - **Customer Analysis**: Focuses on analyzing customer-related data. It includes:
     - **Revenue by Gender**: Breaks down revenue based on customer gender to understand purchasing patterns.
     - **Revenue by Age Bin**: Analyzes revenue across different age groups, providing insights into which age segments are driving sales.
     - **Revenue by Country**: Examines revenue performance by country to identify geographical trends and market strengths.
     - **Revenue by Buyer Type**: Differentiates revenue based on buyer types (e.g., buyer, seller) to assess the impact of different buyer categories.
       
<img width="1242" alt="Screenshot 2024-08-14 at 12 29 17 PM" src="https://github.com/user-attachments/assets/698115ae-9aba-4eb8-b448-66bc262b3e38">

3. **Report Page**:
   - **Quarterly and MoM Performance**: Provides a detailed report on quarterly performance, showing how sales metrics have evolved over each quarter. It also includes month-over-month (MoM) performance to track short-term trends and fluctuations.
   - **Weekly Revenue of Top 5 Drugs**: Features a heatmap visualization that displays the weekly revenue performance of the top 5 drugs. This allows for a granular view of sales trends and helps in identifying the most profitable products.
   - **Filters**: Offers filters for country and gender, enabling users to focus on specific demographic or regional segments and gain more targeted insights.
     
<img width="1243" alt="Screenshot 2024-08-14 at 12 29 46 PM" src="https://github.com/user-attachments/assets/5e333b0c-6dbe-43e5-b1b6-cdcdfa57b5bb">

<img width="1239" alt="Screenshot 2024-08-14 at 12 37 56 PM" src="https://github.com/user-attachments/assets/475ae8cd-6100-4656-8acb-c2c7020db278">



This multi-page report is designed to facilitate a thorough analysis of sales performance, customer demographics, and drug revenue trends. By providing detailed metrics, comparisons, and interactive filters, the report supports informed decision-making and strategic planning.

## Deploy
### Read-only direct access via the web
[![Open In Power Bi](https://img.shields.io/badge/open_in_power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiMWY1YzM2YzgtZmFiYi00ZjI1LWJjYmQtNjViYjMxYWM5ZmNjIiwidCI6IjM0YmQ4YmVkLTJhYzEtNDFhZS05ZjA4LTRlMGEzZjExNzA2YyJ9)  
Explore the fully functional report with native PowerBI interactive experience.

### Full access via PowerBI desktop
If you have PowerBI desktop installed, download the `APIs.pbix` from the repo and open it using PowerBI desktop. There is no need to download the raw dataset; the `pbix` files contain the complete normalized data model, feel free to modify and experiment with it.   

## License
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
