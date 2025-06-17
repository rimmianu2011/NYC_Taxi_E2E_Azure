# 🗽 Real-Time NYC Taxi Data Analytics Pipeline

A complete data engineering pipeline using **Azure Data Factory**, **Databricks**, and **Azure Data Lake**, designed to process and analyze **NYC Taxi Trip Data** in both batch and streaming modes using the **Medallion Architecture**.

[![Project Status](https://img.shields.io/badge/status-complete-brightgreen)](#)
[![Tech Stack](https://img.shields.io/badge/stack-Azure%20%7C%20Databricks%20%7C%20PySpark-blue)](#)

---

## 🧠 Overview

This project showcases a scalable and modular data pipeline built on Azure services, enabling real-time insights into NYC taxi activity. The architecture is organized into **Bronze**, **Silver**, and **Gold** layers following the Medallion pattern for data reliability, quality, and performance.

---

## ⚙️ Architecture Diagram

```plaintext
[NYC Taxi Trip Data (HTTP CSV)] 
        ↓
[Azure Data Factory]
        ↓
[Bronze Layer — Raw Data in ADLS]
        ↓
[Databricks (Silver Layer) — Cleaned Data]
        ↓
[Databricks (Gold Layer) — Aggregated KPIs]
        ↓
[Power BI — Dashboard]
```

---

## 🔁 Workflow Breakdown

### 1. Azure Data Factory — Bronze Layer
- Ingests raw NYC Taxi data from HTTP source.
- Stores it in **Azure Data Lake Gen2** as csv and parquet format.
- Scheduled with ADF triggers (hourly ingestion).

### 2. Azure Databricks — Silver & Gold Layers
- **Silver Layer**:
  - Cleans and enriches raw data (e.g., null removal, data types).
- **Gold Layer**:
  - Aggregates key metrics and KPIs.
  - Utilizes **Delta Lake** for ACID transactions and versioning.

### 3. Gold-Level KPIs
- Trips per borough
- Average fare per hour
- Total revenue per day

---

## Visualization Dashboard

- Built using **Power BI** connected directly to Gold Delta Tables.
- Features include:
  - Pickup heatmap by zone
  - Borough-wise revenue breakdown
  - Time-series fare analysis

---

## Tech Stack

| Layer         | Tool/Tech                      |
|---------------|-------------------------------|
| Ingestion     | Azure Data Factory             |
| Processing    | Azure Databricks, PySpark      |
| Storage       | Azure Data Lake Gen2 + Delta   |
| Visualization | Power BI                       |
| Languages     | Python, SQL                    |

---

## Project Structure

```bash
notebooks/
  ├── bronze_ingestion_adf/         # ADF HTTP as source, pipeline configs
  ├── nyc_taxi_silver.dbc           # Cleansing and enrichment logic
  └── gold_layer.dbc                # KPI aggregation logic

adf_pipeline/
  └── copy_data_from_source.json   # ADF pipeline: Copy data from source to sink (bronze layer)

README.md
```

---

## 🎯 Key Learning Outcomes

- 🧩 End-to-end orchestration using Azure Data Factory
- 🧱 Layered data lake architecture with Delta Lake
- ⚡ Real-time and batch processing via Spark (Databricks)
- 📊 Insight generation using Power BI or Synapse

---

## 📎 Repo Link

🔗 [GitHub Repository](https://github.com/your-username/nyc-taxi-azure-pipeline)

> *Feel free to fork this repository and adapt it to your own datasets or industry-specific workflows.*

---
