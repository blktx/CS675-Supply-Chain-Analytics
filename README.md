# Holiday Demand and Supply Chain Inventory Analytics Using PySpark

## Project Overview

This project analyzes supply chain inventory behavior using PySpark and multiple
data sources.

The main supply chain dataset contains daily SKU-level inventory and demand
records for 2024. It is enriched with:

- U.S. federal holiday data
- Daily weather observations

The project focuses on demand patterns, inventory risk, promotions, supplier
lead time, forecast accuracy, estimated financial performance, and external
factors.

The workflow includes data exploration, preprocessing, cross-source joins,
Spark optimization, and business analysis.

---

## Research Questions

1. How does demand differ between holidays and non-holidays?
2. Does demand vary across individual federal holidays?
3. Are inventory-risk conditions more common during holidays?
4. How do promotions affect demand and inventory risk?
5. How does supplier lead time relate to inventory risk?
6. How accurate is the demand forecast?
7. What is the estimated financial impact of demand patterns?
8. Are daily weather conditions associated with demand or inventory risk?

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

Cloud-scale deployment will use course-provided AWS infrastructure.

---

## Datasets

### Supply Chain Inventory Dataset

The primary fact table contains:

- 91,250 records
- 365 dates
- 50 SKUs
- 5 warehouses
- 10 suppliers
- 4 regional categories

The grain of the dataset is:

`Date + SKU_ID + Warehouse_ID`

Each combination appears once.

Important fields include:

- Units_Sold
- Inventory_Level
- Supplier_Lead_Time_Days
- Reorder_Point
- Order_Quantity
- Unit_Cost
- Unit_Price
- Promotion_Flag
- Stockout_Flag
- Demand_Forecast

### U.S. Federal Holiday Dataset

The holiday dimension contains the 11 federal holidays observed in 2024.

Fields include:

- Date
- Official holiday name
- Date definition
- Year established

The dataset is joined to the supply chain fact table using `Date`.

### Weather Dataset

The weather dataset contains daily observations from Branson West Municipal
Emerson Field Airport in Missouri.

Fields used include:

- Temperature
- Maximum temperature
- Minimum temperature
- Precipitation
- Wind speed

Weather is joined by date only and is treated as an exploratory external factor
because specific warehouse locations are not available.

---

## Project Structure

```text
CS675_Supply_Chain_Project/
│
├── data/
│   ├── raw/
│   │   ├── supply_chain_dataset1.csv
│   │   ├── us_holidays_2024.csv
│   │   └── weather2024.csv
│   │
│   └── processed/
│       └── final_joined/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_data_join_clean.ipynb
│   └── 04_analysis.ipynb
│
├── output/
│   ├── tables/
│   └── charts/
│
├── .gitignore
└── README.md
