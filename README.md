### Proof of Concept: ETL Pipeline on Databricks
### Overview

This repository demonstrates a Proof of Concept (POC) for building an end-to-end ETL pipeline on Databricks using Delta Lake. The pipeline ingests deeply nested JSON data, applies transformations, and implements Slowly Changing Dimension (SCD) Type 2 logic before aggregating into a Gold layer.

### Objectives

Ingest deeply nested JSON files from multiple source folders in Databricks Volumes.

Flatten and transform JSON structures using Spark SQL and PySpark.

Apply data cleaning, filtering, and standardization rules.

Dynamically extract columns based on a mapping provided in an Excel sheet.

Implement SCD Type 2 logic to track historical changes.

Aggregate curated data into a Gold layer Delta table for downstream analytics.

### Architecture

###   1.Bronze Layer

Raw ingestion of JSON files from 3 source folders in Databricks Volumes.

Stored as Delta tables for schema inference and reliability.

### 2.Silver Layer

Explode nested JSON structures.

Data cleaning, filtering, and transformation.

Column extraction based on mapping defined in Excel.

Conformance applied to ensure standardized schema.

### 3.Gold Layer

Implementation of SCD Type 2 for dimension tables.

Aggregations on curated data for analytics and reporting.

Optimized Delta tables ready for BI consumption.

 ###Tech Stack

Databricks (Spark + Delta Lake)

PySpark / SQL (for transformations)

Excel Mapping Sheet (to define column extraction paths)

Delta Tables (Bronze, Silver, Gold layers)

### Data Flow

### Source → Bronze:

JSON files ingested as raw Delta tables.

### Bronze → Silver:

Explode nested arrays and objects.

Apply filters and cleaning rules.

Select required columns as per Excel mapping.

### Silver → Gold:

Implement SCD Type 2 logic (tracking history with effective and expiry dates).

Perform aggregations (business KPIs, summaries).




