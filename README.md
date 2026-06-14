# Melbourne Housing Lakehouse Analytics Platform

## Project Overview

This project demonstrates an end-to-end Data Engineering pipeline built using Databricks, PySpark, Delta Lake, and Spark SQL. The solution implements Medallion Architecture (Bronze, Silver, and Gold layers) to ingest, clean, transform, and analyze Melbourne housing market data.

The pipeline processes raw property transaction data, applies data quality checks and transformations, and generates business-ready datasets for analytics, reporting, and visualization. Gold-layer datasets provide insights into average property prices, suburb-level market performance, and property type trends.

## Technology Stack

* Databricks
* PySpark
* Delta Lake
* Spark SQL
* GitHub
* Databricks Visualizations

## Architecture

```text
Raw CSV Data
      ↓
Bronze Layer
      ↓
Silver Layer
      ↓
Gold Layer
      ↓
Analytics & Visualization
```

## Bronze Layer

The Bronze layer stores the raw Melbourne housing dataset exactly as it was ingested from the source CSV file.

### Key Activities

* Loaded source CSV data into Databricks
* Created a Delta Lake table
* Preserved original records for traceability and auditing

### Table

`bronze_melb_housing`

## Silver Layer

The Silver layer applies data quality and cleansing rules to create a trusted analytics-ready dataset.

### Key Activities

* Removed records with null property prices
* Removed records with null suburb values
* Removed duplicate records
* Prepared clean datasets for downstream analysis

### Table

`silver_melb_housing`

## Gold Layer

The Gold layer generates business-focused datasets and metrics for reporting and decision-making.

### Generated Tables

#### `gold_suburb_metrics`

Average property price by suburb.

#### `gold_property_count`

Property transaction count by suburb.

#### `gold_property_type`

Average property price by property type.

## Key Insights

Analysis of Melbourne housing transactions identified significant variation in property prices across suburbs.

### Findings

* Kooyong recorded the highest average property price.
* Canterbury and Middle Park were among the most expensive suburbs.
* Property prices exceeded AUD 2 million in several premium suburbs.
* Gold-layer aggregates provide business-ready insights for property market analysis and investment research.
