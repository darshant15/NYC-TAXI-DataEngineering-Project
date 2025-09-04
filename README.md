# 🚖 NYC Taxi Data Engineering Project – End-to-End Cloud Pipeline

![Azure](https://img.shields.io/badge/Platform-Microsoft%20Azure-blue)
![GitHub](https://img.shields.io/badge/Repo-Version--Controlled-lightgrey)
![Pipeline](https://img.shields.io/badge/Data-Pipeline-green)

## 📌 Project Overview

This project demonstrates an **end-to-end Data Engineering pipeline** built on the **NYC Taxi dataset**.  
It covers **API-based ingestion, transformation (PySpark), storage in Parquet format, workflow automation, orchestration, and visualization** using Azure services.


---
## 🖼️ Architecture Diagram

![Pipeline Architecture](https://github.com/darshant15/NYC-TAXI-DataEngineering-Project/blob/main/ArchitectureofProject(dataengineer).jpeg)


---

## 🚀 Project Highlights

- **Automated Ingestion**:  
  - Pulled raw taxi trip data directly from **NYC Taxi & Limousine Commission (TLC) APIs**.  
  - Stored incoming data as **Parquet files** in **Azure Data Lake Storage (ADLS Gen2)** for compression & performance.  

- **Data Lake Architecture**:  
  - **Raw zone** → Direct API dumps in CSV/Parquet.  
  - **Curated zone** → Cleaned, deduplicated, schema-enforced Parquet files.  
  - **Analytics zone** → Aggregated tables optimized for BI reporting.  

- **Dynamic Pipeline Logic**:  
  - Used **if-else conditions** in ADF to branch logic (e.g., different pipelines for Yellow Cab vs. Green Cab).  
  - Implemented **ForEach activity** in ADF for iterating over multiple months/years of trip data ingestion.  
  - Integrated **failure conditions** for retries and logging.  

- **Scalable Data Processing**:  
  - **Azure Databricks (PySpark)** transformations included:  
    - Handling nulls and schema mismatches  
    - Deduplication of rows  
    - Feature engineering: trip duration, cost per mile, speed per trip  
    - Aggregations: revenue by borough, busiest zones, peak travel hours  

- **Analytics-Ready Storage**:  
  - Transformed data loaded into **Azure Synapse Analytics** (Lake DB) for SQL analysis.  
  - Tables partitioned by `year` and `month` for query efficiency.  

- **Visualization**:  
  - Built **Power BI dashboards** showing:  
    - Hourly/Monthly trip patterns  
    - Average fare distribution by distance  
    - Payment methods trend (Card, Cash, Others)  
    - Heatmaps for busiest pickup/drop-off locations  

---

## 🏗️ Architecture Workflow

1. **Data Ingestion** – API calls & CSV downloads for Yellow/Green cab datasets. Data saved as **Parquet files** in `raw-data` zone.  
2. **Orchestration** – **Azure Data Factory** pipeline with:  
   - **Lookup activity** → Get file paths/months  
   - **ForEach loop** → Iterate over all months of taxi data  
   - **If Condition activity** → Split logic for Yellow/Green datasets  
3. **Data Transformation** – In **Azure Databricks (PySpark)**:  
   - Read raw Parquet  
   - Apply transformations & aggregations  
   - Write back to curated zone in Parquet/Delta format  
4. **Data Warehouse** – Loaded curated datasets into **Azure Synapse Analytics** (SQL pools).  
5. **Analytics & Visualization** – Connected Power BI → Synapse for interactive dashboards.  

---

## ⚙️ Tech Stack & Tools

- **Azure Data Factory (ADF)** – Orchestration, ForEach, If/Else conditions  
- **Azure Data Lake Storage Gen2 (ADLS)** – Layered raw/curated storage  
- **Azure Databricks (PySpark)** – Transformations, schema enforcement, Parquet writing  
- **Azure Synapse Analytics** – Data warehouse queries  
- **Power BI** – Visual dashboards  
- **GitHub** – Version control  

---

## 📊 Key Insights (Examples)

- 🚖 Trips per hour/day/month – demand forecasting  
- 💳 Payment method trends – card vs. cash  
- 🌍 Borough-level heatmaps – busiest pickup zones  
- 💵 Average fare per mile vs. trip distance  
- ⏱️ Peak congestion hours & average trip duration  

---

## 🚀 How to Run

1. Clone repository notebook of databricks :
   ```bash
   git clone https://github.com/darshant15/NYC-TAXI-DataEngineering-Project.git
   cd NYC-TAXI-DataEngineering-Project
