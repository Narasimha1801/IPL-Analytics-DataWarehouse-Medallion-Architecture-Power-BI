# 🏏 IPL InsightHub – End-to-End Cricket Analytics Data Warehouse Using Medallion Architecture (MS SQL Server)

## 📌 Project Overview

IPL InsightHub is a complete end-to-end analytical data warehouse project built using Microsoft SQL Server and Medallion Architecture (Bronze → Silver → Gold). This project processes raw IPL cricket datasets and transforms them into analytics-ready fact and dimension tables suitable for business intelligence and advanced reporting.

The project demonstrates real-world data engineering concepts such as ETL pipelines, layered architecture, data cleansing, dimensional modeling, surrogate keys, and analytical aggregation. The Gold layer is optimized for visualization tools like Power BI.

---

## 🏗️ Architecture – Medallion Pattern

### 🥉 Bronze Layer (Raw Data Ingestion)

Purpose:
- Stores raw CSV data without transformation.
- Acts as immutable historical storage.

Tables:
- matches  
- batting_scorecard  
- bowling_scorecard  
- deliveries_ball_by_ball  
- innings_totals  

Loading Method:
- BULK INSERT
- Stored Procedure: bronze.proc_load_bronze_ipl

---

### 🥈 Silver Layer (Cleaned & Standardized)

Purpose:
- Data cleansing
- Null handling
- Type casting
- Date standardization
- Column normalization
- Deduplication

Transformations:
- Standardized match dates
- Removed invalid rows
- Normalized team and player names
- Converted numeric fields
- Structured operational tables

Scripts:
- silver_ddl.sql  
- proc_insert_silver.sql  

---

### 🥇 Gold Layer (Analytics & Star Schema)

Purpose:
- Dimensional modeling
- Surrogate keys
- Fact and dimension tables
- Aggregations for BI tools

Dimensions:
- dim_team  
- dim_player  
- dim_venue  
- dim_season  
- dim_match  

Facts:
- fact_batting  
- fact_bowling  
- fact_match  
- fact_deliveries  

Features:
- ROW_NUMBER surrogate keys
- Relationship-ready schema
- Optimized analytical structure

Script:
- gold_ddl.sql

---

## 📁 Project Folder Structure

IPL-Analytics-Data-Warehouse/

datasets/
- matches_fixed_full1170.csv  
- batting_scorecard.csv  
- bowling_scorecard.csv  
- deliveries_ball_by_ball_corrected.csv  
- innings_totals.csv  

scripts/
- init_database.sql  

bronze/
- bronze_ddl.sql  
- proc_load_bronze_ipl.sql  

silver/
- silver_ddl.sql  
- proc_insert_silver.sql  

gold/
- gold_ddl.sql  

README.md

---

## ⚙️ Setup Instructions

### Step 1 – Create Database

Run:
scripts/init_database.sql

---

### Step 2 – Create Bronze Tables

Run:
scripts/bronze/bronze_ddl.sql

---

### Step 3 – Load Raw Data

Update CSV paths inside proc_load_bronze_ipl.sql

Execute:
EXEC bronze.proc_load_bronze_ipl;

---

### Step 4 – Create Silver Layer

Run:
scripts/silver/silver_ddl.sql

Populate:
EXEC silver.proc_insert_silver;

---

### Step 5 – Create Gold Layer

Run:
scripts/gold/gold_ddl.sql

Gold tables are now ready for analytics.

---

## 📊 Example Analytics Use Cases

- Total runs per season  
- Top run scorers  
- Best economy bowlers  
- Team win percentages  
- Venue-wise performance  
- Player consistency  
- Match outcome analysis  

---

## 🚀 Key Skills Demonstrated

- SQL Server Data Warehousing  
- Medallion Architecture  
- ETL using Stored Procedures  
- Dimensional Modeling  
- Surrogate Key Generation  
- Star Schema Design  
- Data Cleaning & Transformation  
- Analytical Data Engineering  

---

## 🎯 Ideal For

- Data Engineering portfolios  
- Final year academic projects  
- Resume showcase  
- Interview discussions  
- BI dashboard foundations  

---

## 🔮 Future Enhancements

- Incremental loading pipelines  
- Slowly Changing Dimensions (SCD Type 2)  
- Performance tuning & indexing  
- Power BI dashboards  
- Player clustering and ML analytics  
- Workflow orchestration using Airflow  

---

## 👨‍💻 Author

M. Lakshmi Narasimha  
Data Science & Data Engineering Enthusiast  

---

## ⭐ If you like this project, please give it a star on GitHub!
