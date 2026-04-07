# banking_fraud_detection_pipline

## Overview
This is an end-to-end Data Engineering project built using Azure and Databricks to detect fraudulent banking transactions.
The pipeline follows Medallion Architecture (Bronze, Silver, Gold) and includes incremental processing, audit logging, and dashboard reporting.

## Objective
* Detect fraudulent transactions using rule-based logic
* Build a scalable and production-ready pipeline
* Generate business insights using Power BI dashboard

## Architecture
Source Data → Azure Data Factory → ADLS (Bronze)
→ Azure Databricks (Silver → Gold Processing)
→ Incremental Loading + Audit Logging
→ Power BI Dashboard

## Tech Stack
* Azure Data Factory (Data ingestion & orchestration)
* Azure Data Lake Storage Gen2 (Storage)
* Azure Databricks (PySpark processing)
* Unity Catalog (Data governance)
* Delta Lake (Storage format)
* Power BI (Visualization)

## Pipeline Flow
1. Data is ingested using Azure Data Factory into Bronze layer
2. Silver layer cleans and transforms the raw data
3. Gold layer applies fraud detection logic
4. Incremental notebook processes only new data using watermark
5. Audit notebook logs pipeline execution
6. Summary notebook prepares dashboard data

## Databricks Job Pipeline
A Databricks Job pipeline is created to automate execution of all notebooks in sequence:
* 01_bronze → Data ingestion
* 02_silver → Data cleaning
* 03_gold → Fraud detection
* 04_incremental → Incremental processing
* 05_audit → Logging
* 06_summary_data → Dashboard dataset

## Fraud Detection Logic
Fraud score is calculated using multiple rules:
* High-value transactions
* Night transactions
* Multiple transactions in short time
* Distance anomaly
* Rapid transactions
Transactions are flagged as fraud based on score threshold.

## Dashboard Insights
* Total Transactions
* Fraud Count
* Fraud Percentage
* Fraud trend over time
* Fraud by city and category
* Hour-wise fraud analysis
* Top risky customers and merchants

##  Key Features
* Medallion Architecture (Bronze, Silver, Gold)
* Incremental Loading using Watermark
* Delta MERGE (Upsert)
* Data Quality Handling
* Audit Logging
* End-to-End Pipeline Automation
* Databricks Job Orchestration

## Business Impact
* Early fraud detection
* Reduced financial loss
* Identification of high-risk customers and merchants
* Improved monitoring through dashboards

## Project Structure
01_bronze.ipynb
02_silver.ipynb
03_gold.ipynb
04_incremental.ipynb
05_audit.ipynb
06_summary_data.ipynb
Project_documentation_1.pdf

## Author
Dhanshree Randhavane
