# Northwind Data Warehouse using PySpark & Databricks

An end-to-end data engineering and data warehouse project built using **MySQL, PySpark, Databricks, and Delta Lake**.

The project demonstrates how raw relational data can be extracted, transformed, cleaned, modeled into a dimensional data warehouse, analyzed for business insights, and processed through incremental data pipelines.

---

## Project Overview

The goal of this project was to build a complete data warehouse pipeline using the Northwind sales database.

The project follows a **Bronze → Silver → Gold** architecture and includes:

- Source database analysis
- Data extraction
- PySpark data processing
- Data cleaning and transformation
- Fact and dimension modeling
- Business analysis
- Incremental data loading
- Delta Lake MERGE operations
- Data-quality validation
- Invalid-record quarantine

---

## Architecture

```text
                 MySQL Northwind Database
                          |
                          ↓
                  Source Table Analysis
                          |
                          ↓
                     CSV Extraction
                          |
                          ↓
                  PySpark / Databricks
                          |
                          ↓
                    Bronze Layer
                          |
                          ↓
                    Silver Layer
                          |
                          ↓
                     Gold Layer
                          |
              +-----------+-----------+
              |                       |
              ↓                       ↓
        Fact & Dimensions       Business Insights


Incremental Processing:

              New Incremental CSV
                       |
                       ↓
                 Read & Transform
                       |
                       ↓
              Standardize Columns
                       |
                       ↓
              Convert "NULL" → NULL
                       |
                       ↓
                  Deduplicate
                       |
                       ↓
               Data Quality Checks
                    /       \
                   /         \
              Valid           Invalid
                |                |
                ↓                ↓
          Delta MERGE       Quarantine Table
                |
                ↓
             Silver
