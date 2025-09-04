# 🚖 NYC Taxi Data Engineering Project – End-to-End Cloud Pipeline

![Azure](https://img.shields.io/badge/Platform-Microsoft%20Azure-blue)
![GitHub](https://img.shields.io/badge/Repo-Version--Controlled-lightgrey)
![Pipeline](https://img.shields.io/badge/Data-Pipeline-green)

## 📌 Project Overview

This project demonstrates an **end-to-end Data Engineering pipeline** built on the **NYC Taxi dataset**.  
It covers **data ingestion, transformation, storage, querying, orchestration, and visualization** using modern cloud-based services and frameworks.

---

## 🖼️ Architecture Diagram

![Pipeline Architecture](https://github.com/darshant15/NYC-TAXI-DataEngineering-Project/blob/main/ArchitectureofProject(dataengineer).jpeg)

---

## 🚀 Project Highlights

- **Automated Ingestion**: Ingest raw NYC Taxi trip datasets (yellow/green cabs, FHV, payment data, etc.) into a **Data Lake (ADLS Gen2 / S3)**.  
- **Data Lake Architecture**:  
  - **Raw zone** → Store original CSV/Parquet files.  
  - **Curated zone** → Transformed, deduplicated, schema-optimized data for analytics.  
- **Scalable Data Processing**: Use **Databricks / PySpark** for cleaning, joins, aggregations, and enrichment of trip data.  
- **Secure Pipeline Management**: Integrate **Azure Key Vault / AWS Secrets Manager** for secure credential storage.  
- **Analytics-Ready Storage**: Processed data loaded into **Azure Synapse Analytics / Redshift / BigQuery** for downstream querying.  
- **Orchestration**: Pipelines scheduled and monitored using **Azure Data Factory (ADF) / Airflow**.  
- **BI & Dashboards**: Interactive **Power BI** dashboard showcasing insights like revenue trends, busiest routes, and payment methods.  

---

## 🏗️ Architecture Workflow

1. **Data Ingestion** – Raw CSV/Parquet datasets ingested from NYC Taxi & Limousine Commission (TLC) dataset source.  
2. **Data Lake Storage** – Organized in layered architecture (Raw → Curated).  
3. **Data Transformation** – Performed using **PySpark in Databricks**:  
   - Cleaning & handling nulls  
   - Deduplication  
   - Feature engineering (trip duration, average speed, cost per mile, etc.)  
   - Aggregations by borough, time, payment type  
4. **Data Warehouse** – Transformed data loaded into **Azure Synapse Analytics** (SQL pools) for analysis.  
5. **Automation & Monitoring** – Pipelines scheduled and monitored in **ADF / Airflow** with retry mechanisms.  
6. **Visualization** – BI dashboard built in **Power BI** to analyze trip trends and business KPIs.  

---


*(Replace the link with the actual raw path of your diagram in the repo.)*

---

##
