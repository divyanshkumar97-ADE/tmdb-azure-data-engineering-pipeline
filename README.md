# End-to-End Azure Data Engineering Project (TMDB)

## Overview
This project demonstrates an end-to-end data engineering pipeline built on Azure using real-world REST API data from TMDB (The Movie Database).

The pipeline ingests movie data, processes it through a medallion architecture (Bronze → Silver → Gold), and visualizes insights using Power BI.

---

## Architecture
TMDB API → Azure Data Factory → ADLS Gen2 (Bronze)  
→ Azure Databricks (Silver & Gold using Delta Lake)  
→ Databricks SQL → Power BI

---

## Technologies Used
- Azure Data Factory (REST API ingestion, pagination)
- Azure Data Lake Storage Gen2
- Azure Databricks (PySpark, Delta Lake)
- Databricks SQL Warehouse
- Power BI
- GitHub

---

## Data Pipeline Flow

### 1. Ingestion (Bronze)
- TMDB `/movie/popular` REST API
- Pagination handled using ADF ForEach activity
- Raw JSON stored in ADLS Gen2

### 2. Transformation (Silver)
- JSON flattened using PySpark
- Schema normalization
- Stored as Delta tables

### 3. Analytics Layer (Gold)
- Business-friendly schema
- Optimized for BI consumption
- Delta tables exposed via SQL views

### 4. Visualization
- Power BI connected via Azure Databricks connector
- Interactive dashboards showing ratings, popularity, trends, and language insights

---

##  Sample Insights
- Top rated movies
- Most popular movies
- Ratings vs popularity analysis
- Language-wise movie distribution
- Release year trends

---

##  Key Learnings
- REST API ingestion at scale
- Pagination handling in ADF
- JSON processing using Spark
- Delta Lake best practices
- BI integration using Databricks SQL


## 📌 Author
Divyansh Kumar
