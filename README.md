📊 End-to-End Data Warehouse Project (Bronze → Silver → Gold)
🚀 Project Summary

This project demonstrates the implementation of a modern data warehouse pipeline using the Medallion Architecture (Bronze, Silver, Gold layers).

The solution processes raw CRM and ERP data, transforms it into clean and structured datasets, and finally builds a business-ready analytical model for reporting and insights.

🏗️ Architecture Overview
Bronze Layer  →  Silver Layer  →  Gold Layer
 Raw Data        Clean Data       Business Ready Data
🥉 Bronze Layer – Raw Data
📌 Description

The Bronze layer stores raw, unprocessed data directly from source systems. No transformations are applied at this stage.

📂 Tables
crm_cust_info
crm_prd_info
crm_sales_details
erp_loc_a101
erp_cust_az12
erp_px_cat_g1v2
⚙️ Key Characteristics
Stores original source data
Maintains data history
Minimal validation
Supports traceability and debugging
🥈 Silver Layer – Cleaned & Transformed Data
📌 Description

The Silver layer performs data cleaning, transformation, and standardization to improve data quality and usability.

🔄 Transformations Applied
Removed duplicates using ROW_NUMBER()
Trimmed and standardized text (TRIM, UPPER)
Converted raw date formats into DATE
Standardized categorical values:
Gender (M/F → Male/Female)
Marital Status (S/M → Single/Married)
Handled missing and invalid data
Recalculated incorrect sales values
Implemented Slowly Changing Dimension (SCD Type 2) using LEAD()
📂 Tables
crm_cust_info
crm_prd_info
crm_sales_details
erp_loc_a101
erp_cust_az12
erp_px_cat_g1v2
🥇 Gold Layer – Business-Ready Data
📌 Description

The Gold layer contains modeled and aggregated data optimized for reporting, dashboards, and business intelligence tools.

⭐ Data Model (Star Schema)
🔹 Dimension Tables
dim_customer
dim_product
dim_location
🔹 Fact Table
fact_sales
📊 Business Use Cases
Sales performance analysis
Customer segmentation
Product category insights
Regional sales trends
KPI reporting
🛠️ Tech Stack
SQL Server (T-SQL)
Data Warehousing Concepts
ETL Pipeline Design
Power BI (for visualization)
🔍 Key Concepts Demonstrated
Medallion Architecture (Bronze → Silver → Gold)
Data Cleaning & Transformation
Window Functions (ROW_NUMBER, LEAD)
Data Quality Handling
Slowly Changing Dimensions (SCD Type 2)
Star Schema Modeling
▶️ How to Run This Project
1️⃣ Create Schemas
CREATE SCHEMA bronze;
CREATE SCHEMA silver;
CREATE SCHEMA gold;
2️⃣ Execute Scripts in Order
Run Bronze Layer scripts (table creation + data load)
Run Silver Layer scripts (cleaning & transformation)
Run Gold Layer scripts (data modeling)
📁 Project Structure
project/
│
├── bronze/
│   ├── create_tables.sql
│
├── silver/
│   ├── create_tables.sql
│   ├── transformations.sql
│
├── gold/
│   ├── dim_tables.sql
│   ├── fact_tables.sql
│
├── README.md
