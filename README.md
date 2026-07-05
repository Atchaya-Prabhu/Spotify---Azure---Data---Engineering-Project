# Spotify Azure Data Engineering Project

## 📌 Project Overview

This project demonstrates an end-to-end Azure Data Engineering pipeline that ingests, transforms, and prepares Spotify data for analytics using a modern Lakehouse architecture. The solution combines Azure services with Databricks to build scalable, incremental, and production-style data pipelines from ingestion through curated datasets.

The project follows the Bronze–Silver–Gold architecture and showcases modern data engineering concepts including incremental loading, Delta Lake, Delta Live Tables, streaming data processing, and CI/CD deployment.

---

## 🛠️ Technology Stack

- Microsoft Azure
- Azure Data Factory (ADF)
- Azure SQL Database
- Azure Data Lake Storage Gen2 (ADLS)
- Azure Databricks
- PySpark
- Delta Lake
- Delta Live Tables (DLT)
- Unity Catalog
- Databricks Asset Bundles (DAB)
- GitHub

---

## 🏗️ Project Architecture

The solution follows the Medallion Architecture:

- **Bronze Layer** – Stores raw data ingested from source systems.
- **Silver Layer** – Cleanses, validates, and transforms data using PySpark.
- **Gold Layer** – Produces analytics-ready datasets for reporting and business intelligence.

---

## 🚀 Key Features

### Data Ingestion

- Built Azure Data Factory pipelines for automated data ingestion.
- Loaded source data into Azure Data Lake Storage.
- Implemented incremental loading to process only newly available records.

### Data Transformation

- Processed data using Azure Databricks and PySpark.
- Applied data cleansing, validation, and transformation logic.
- Managed Delta tables for reliable and scalable data storage.

### Lakehouse Implementation

- Organized data using Bronze, Silver, and Gold layers.
- Implemented Delta Lake to support ACID transactions and schema evolution.
- Registered datasets in Unity Catalog for centralized governance.

### Analytics Layer

- Created curated Gold datasets optimized for reporting.
- Implemented Delta Live Tables to automate transformation workflows.
- Applied Slowly Changing Dimension (SCD) logic for dimensional data management.

---

## 🔐 Security

- Used Azure Managed Identity for secure authentication.
- Applied role-based access control (RBAC) for storage resources.
- Managed data access through Unity Catalog permissions.

---

## ⚡ Performance Optimizations

- Incremental data processing
- Delta Lake optimizations
- Streaming ingestion with Structured Streaming
- Checkpointing for fault tolerance
- Optimized Delta table storage and query performance

---

## 📊 Business Use Cases

- Spotify listening activity analysis
- User engagement reporting
- Artist and track popularity insights
- Analytics-ready datasets for Power BI dashboards
- Reference implementation of an Azure Lakehouse solution

---

## 🎯 Key Learnings

- Designing scalable Azure data pipelines
- Building Medallion Architecture using Delta Lake
- Developing PySpark transformation pipelines
- Implementing Delta Live Tables
- Working with Unity Catalog
- Applying CI/CD using Databricks Asset Bundles
- Building production-style cloud data engineering workflows

---

## ✅ Conclusion

This project demonstrates an end-to-end Azure data engineering solution using Azure Data Factory, Azure Databricks, Delta Lake, and Unity Catalog. It highlights modern data engineering practices for building scalable, maintainable, and analytics-ready data platforms while following industry-standard Lakehouse architecture.
