# 🎵 Spotify Real-Time Data Engineering Pipeline (Azure | Databricks | Delta Live Tables)

![Azure](https://img.shields.io/badge/Azure-Data%20Engineering-0078D4?logo=microsoftazure&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-Delta%20Lake-EF3E42?logo=databricks&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![PySpark](https://img.shields.io/badge/PySpark-Structured%20Streaming-orange)
![ADF](https://img.shields.io/badge/Azure-Data%20Factory-blue)

---

# 📌 Project Overview

This project demonstrates a **production-grade end-to-end Azure Data Engineering solution** that ingests Spotify streaming data from Azure SQL Database, processes incremental data using Change Data Capture (CDC), and transforms it into analytics-ready datasets following the **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline leverages **Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, Delta Lake, Spark Structured Streaming, Unity Catalog, and Delta Live Tables (DLT)** to build a scalable, secure, and enterprise-ready data platform.

---

# 🏗️ Architecture

<p align="center">
  <img src="images/architecture.png" width="900">
</p>

---

# 🚀 End-to-End Workflow

```
Azure SQL Database
        │
        ▼
Azure Data Factory
(Watermark Incremental Load)
        │
        ▼
Bronze Layer (ADLS Gen2)
Raw Parquet Files
        │
        ▼
Azure Databricks
Spark Structured Streaming
        │
        ▼
Silver Layer (Delta Lake)
Data Cleansing & Transformations
        │
        ▼
Delta Live Tables (DLT)
CDC + SCD Type 1 Processing
        │
        ▼
Gold Layer
Analytics Ready Tables
        │
        ▼
Power BI / SQL Analytics
```

---

# 🛠️ Technology Stack

| Category | Technologies |
|-----------|--------------|
| Cloud | Microsoft Azure |
| Storage | Azure Data Lake Storage Gen2 |
| Database | Azure SQL Database |
| Data Processing | Azure Databricks |
| Framework | Apache Spark |
| Streaming | Spark Structured Streaming |
| Data Format | Delta Lake |
| Orchestration | Azure Data Factory |
| Catalog | Unity Catalog |
| CI/CD | Databricks Asset Bundles |
| Programming | Python, PySpark |
| Security | Azure Managed Identity |
| Data Modeling | Medallion Architecture |

---

# ⭐ Key Features

- Incremental Data Loading using CDC
- Watermark-Based Processing
- Azure Data Factory Orchestration
- Bronze, Silver & Gold Architecture
- Spark Structured Streaming
- Delta Lake
- Delta Live Tables (DLT)
- Unity Catalog
- Databricks Asset Bundles
- Managed Identity Authentication
- Schema Evolution
- Fault Tolerant Streaming
- Production Ready Design

---

# 📂 Project Structure

```
spotify-data-engineering
│
├── adf
│   ├── pipelines
│   ├── linked_services
│   └── datasets
│
├── databricks
│   ├── bronze
│   ├── silver
│   ├── gold
│   └── utils
│
├── images
│
├── architecture
│
└── README.md
```

---

# 🥉 Bronze Layer

## Objective

The Bronze layer stores raw data exactly as received from the source system without applying business transformations.

### Source

- Azure SQL Database

### Destination

- Azure Data Lake Storage Gen2

### Data Format

- Parquet

### Implementation

Azure Data Factory performs incremental ingestion by extracting only newly inserted or updated records using a watermark column.

### Key Features

- Incremental loading
- Metadata driven pipeline
- Parameterized datasets
- Dynamic SQL queries
- Watermark tracking
- Error handling

---

# 🔄 Watermark-Based Incremental Loading

The pipeline stores the latest processed timestamp after every successful execution.

During the next run:

```
Current Timestamp >
Last Processed Timestamp
```

Only newly inserted or updated records are extracted.

Benefits

- Faster execution
- Lower compute cost
- Reduced network traffic
- No duplicate processing

---

# 🥈 Silver Layer

The Silver layer performs data cleansing, validation, and standardization using Azure Databricks and Spark Structured Streaming.

---

## Processing Steps

### Read Streaming Data

Uses Auto Loader to continuously ingest files from the Bronze layer.

```python
spark.readStream \
    .format("cloudFiles") \
    .option("cloudFiles.format","parquet")
```

---

### Data Cleaning

- Remove duplicate records
- Drop rescued columns
- Standardize text values
- Handle schema evolution
- Data validation

---

### Business Transformations

Examples include:

- Convert usernames to uppercase
- Categorize track duration
- Remove invalid characters
- Create derived columns

---

### Store as Delta

The transformed data is written as Delta tables into the Silver layer.

Benefits

- ACID transactions
- Time Travel
- Schema Enforcement
- Efficient Reads
- Versioning

---

# 🥇 Gold Layer

The Gold layer contains curated, business-ready datasets optimized for reporting and analytics.

It is implemented using **Delta Live Tables (DLT).**

---

## Gold Layer Workflow

### Step 1

Read Silver Layer as Streaming Tables

### Step 2

Create Staging Tables

### Step 3

Apply CDC

### Step 4

Merge Updates using SCD Type 1

### Step 5

Publish Analytics Ready Tables

---

# 🔄 Change Data Capture (CDC)

This project uses Delta Live Tables **apply_changes()** to automatically process:

- Inserts
- Updates

The pipeline maintains only the latest version of each record using SCD Type 1.

Benefits

- Incremental processing
- High performance
- Simplified MERGE logic
- Reduced compute cost

---

# 🔐 Security

The project follows Azure security best practices.

- Azure Managed Identity
- Role Based Access Control (RBAC)
- Unity Catalog
- Least Privilege Access
- External Locations
- Secure ADLS Authentication

---

# ⚡ Performance Optimizations

- Incremental Processing
- Watermark Pattern
- Spark Structured Streaming
- Delta Lake
- Schema Evolution
- Auto Loader
- Checkpointing
- Trigger Once
- File Compaction
- Z-Ordering
- Fault Tolerant Processing

---

# 📊 Business Use Cases

- Music Streaming Analytics
- User Listening Behaviour
- Artist Popularity
- Track Performance
- Daily Streaming Metrics
- User Engagement Analysis
- Power BI Reporting
- Near Real-Time Analytics

---

# 📈 Project Highlights

✔ End-to-End Azure Data Engineering Solution

✔ Enterprise Medallion Architecture

✔ Incremental CDC Processing

✔ Azure Data Factory Pipelines

✔ Azure Databricks

✔ Delta Live Tables

✔ Unity Catalog

✔ Structured Streaming

✔ Delta Lake

✔ Databricks Asset Bundles

✔ Production-Ready Design

---

# 🎯 Skills Demonstrated

- Azure Data Engineering
- Azure Data Factory
- Azure Databricks
- PySpark
- Apache Spark
- Delta Lake
- Delta Live Tables
- Unity Catalog
- Data Warehousing
- ETL / ELT
- Data Modeling
- Incremental Processing
- Change Data Capture
- Lakehouse Architecture
- Cloud Data Engineering

---

# ✅ Conclusion

This project demonstrates a scalable, production-ready Azure Lakehouse solution built using modern cloud-native technologies. It showcases end-to-end data ingestion, incremental processing with Change Data Capture (CDC), Spark Structured Streaming, Delta Lake, and Delta Live Tables to deliver reliable, analytics-ready datasets.

The solution emphasizes performance, security, maintainability, and industry best practices, reflecting real-world enterprise data engineering workflows on Microsoft Azure.
