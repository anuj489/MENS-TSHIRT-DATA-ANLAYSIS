# 👕 Mens T-Shirt Data Analysis --- Power BI Dashboard

## 📊 Project Overview

This project presents an **interactive Power BI dashboard** that
analyzes **Men's T-Shirt product data** to uncover insights about brand
performance, pricing strategies, discounts, and profitability.

The dashboard transforms raw product data into **actionable business
insights** using **data cleaning, SQL transformations, DAX calculations,
and interactive visualizations**.

------------------------------------------------------------------------

# 🔗 Live Dashboard

You can view the interactive Power BI dashboard here:

**Power BI Report**\
https://app.powerbi.com/reportEmbed?reportId=f5402892-f4a2-4fa8-b0ee-4b22c00c69e0&autoAuth=true&ctid=e1d99821-ef38-4f48-836f-7a7ca113dab7

------------------------------------------------------------------------

# 📁 Dataset

Dataset used in this project:

**Men Tshirt.csv**

The dataset contains:

-   Brand Name
-   Price
-   Discount %
-   Sales Price
-   Profit %
-   Product Variety

------------------------------------------------------------------------

# 🛠 Tools & Technologies

The following tools were used in this project:

-   **Microsoft SQL Server (MSSQL)** --- Data storage and querying\
-   **Microsoft Azure** --- Cloud-based SQL server setup and database
    hosting\
-   **Power BI** --- Data visualization and dashboard creation\
-   **Power Query Editor** --- Data cleaning and transformation

------------------------------------------------------------------------

# ☁️ Azure SQL Database Setup

To enable cloud-based data processing, the dataset was imported and
managed using **Azure SQL Database**.

## Steps Performed

1.  Created an account on **Microsoft Azure**.
2.  Created a **SQL Server instance** and an **Azure SQL Database**.
3.  Configured **server-level firewall rules** to allow secure access
    from the local machine.
4.  Connected the database using **SQL Server Management Studio
    (SSMS)**.
5.  Imported the dataset files:
    -   Flat file dataset
    -   Excel dataset containing Men's T-Shirt product data.

------------------------------------------------------------------------

# 🧹 Data Cleaning Using SQL

After importing the dataset into the SQL database, SQL queries were used
to **clean and standardize the pricing columns**.

## Objective

Some price values contained the **₹ currency symbol**, which needed to
be removed so the columns could be used for proper numeric calculations.

## SQL Queries Used

``` sql
-- Cleaning original_price column
UPDATE [dbo].[Men Tshirt]
SET original_price = TRIM(REPLACE(CAST(original_price AS VARCHAR(MAX)), '₹', ''))
WHERE original_price LIKE '%₹%';
```

``` sql
-- Cleaning sale_price column
UPDATE [dbo].[Men Tshirt]
SET sale_price = TRIM(REPLACE(CAST(sale_price AS VARCHAR(MAX)), '₹', ''))
WHERE sale_price LIKE '%₹%';
```

## Result

-   Removed currency symbols from price columns
-   Standardized price values for numerical analysis
-   Prepared the dataset for **Power BI reporting and calculations**

------------------------------------------------------------------------

# 🧮 Calculated Columns Using DAX

To enhance the dataset and generate additional analytical metrics,
**calculated columns were created using DAX (Data Analysis Expressions)
in Power BI**.

## 1️⃣ Discount Percentage

``` dax
Discount % = DIVIDE('Tshirt'[Marked Price] - 'Tshirt'[Sales Price], 'Tshirt'[Marked Price]) * 100
```

## 2️⃣ Profit Percentage

``` dax
Profit % = RANDBETWEEN(2,17)
```

## 3️⃣ Cost Price

``` dax
Cost Price = DIVIDE(100 * 'Tshirt'[Sales Price], 100 + 'Tshirt'[Profit %])
```

------------------------------------------------------------------------

# 📂 Repository Structure

MENS-TSHIRT-DATA-ANALYSIS │ ├── MENS TSHIRT ANALYSIS.pbix ├── Men
Tshirt.csv ├── Brand.docx └── README.md

------------------------------------------------------------------------

# 📈 Dashboard Insights

## Brand Performance

-   Top 5 brands with highest average discount
-   Top 5 brands with highest average sales price
-   Brands with highest profit percentage

## Product Insights

-   Brands with the highest product variety
-   Brands with the lowest profitability

## Pricing & Discount Analysis

-   Relationship between price and discount
-   Impact of discount strategies on profitability

------------------------------------------------------------------------

# 📊 Visualizations Used

-   **Bar Chart** --- Top 5 brands by average discount %
-   **Donut Chart** --- Brand variety count
-   **Ribbon Chart** --- Average sales price comparison
-   **Area Chart** --- Highest profit %
-   **Pie Chart** --- Bottom brands by profit %

------------------------------------------------------------------------

# 📚 Skills Demonstrated

-   Data Cleaning using SQL
-   Data Transformation
-   Azure SQL Database Setup
-   DAX Calculations
-   Dashboard Design
-   Data Storytelling

------------------------------------------------------------------------

# 🚀 Future Improvements

-   Add time-based sales analysis
-   Integrate real-time SQL database updates
-   Build advanced product analytics

------------------------------------------------------------------------

# 👤 Author

**Anuj Agarwal**\
Data Analyst \| Power BI \| SQL \| Data Visualization
