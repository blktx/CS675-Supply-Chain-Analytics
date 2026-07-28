# Holiday Demand and Supply Chain Inventory Analytics Using PySpark

## Project Overview

This project analyzes supply chain inventory behavior using PySpark and multiple
data sources.

The primary dataset contains daily 2024 inventory and demand records by SKU and
warehouse. It is enriched with:

- U.S. federal holiday data
- Daily weather observations

The project includes data exploration, preprocessing, cross-source joins,
inventory-risk analysis, forecast evaluation, financial estimation, and a cloud
deployment using AWS.

---

## Technologies

- Apache Spark
- PySpark
- Spark SQL / DataFrame API
- Spark ML preprocessing tools
- Docker
- Jupyter Notebook
- Parquet
- Git / GitHub
- Amazon S3
- AWS Glue Data Catalog
- Amazon Athena
- Terraform

---

## Datasets

### Supply Chain Inventory Dataset

- 91,250 records
- 365 dates
- 50 SKUs
- 5 warehouses
- 10 suppliers
- 4 regional categories

Dataset grain:

`Date + SKU_ID + Warehouse_ID`

### U.S. Federal Holiday Dataset

Contains the 11 federal holidays observed in 2024.

The holiday dataset is joined to the supply chain fact table using `Date`.

### Weather Dataset

Daily weather observations from one Missouri weather station.

Weather is joined by date and treated as an exploratory external factor because
warehouse-specific geographic locations are unavailable.

---

## Project Structure

```text
CS675_Supply_Chain_Project/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_data_join_clean.ipynb
│   └── 04_analysis.ipynb
│
├── output/
├── .gitignore
└── README.md
