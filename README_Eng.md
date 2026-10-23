# Olist E-Commerce — Regional Order & Delivery Analysis

Portfolio-oriented data analytics case study using the Olist Brazilian E-Commerce dataset.

## Project Objective

Analyze regional order volume, order value and delivery performance to identify differences across Brazilian states.

## Business Questions

- Which states generate the highest order volume?
- What is the typical delivery time?
- Which states have the longest delivery times?
- How does average order value vary by state?
- How should commercial and operational KPIs be interpreted together?

## Key Results

- 27 customer states are represented.
- São Paulo (SP) has the highest order volume.
- Median delivery time: **10 days**
- P90 delivery time: **23 days**
- Top three states by delivered-order volume: **SP, RJ, MG**
- Slowest states by average delivery time in the original analysis: **RR, AP, AM, AL, PA**
- Difference between the slowest and fastest state-level average delivery times: approximately **20.68 days**
- Highest average order-value states in the original analysis: **PB, AP, AC, AL, RO**

## Technologies

Python · Pandas · NumPy · Matplotlib · PostgreSQL · SQLAlchemy · Neon PostgreSQL

## Project Structure

```text
olist-ecommerce-delivery-analysis/
├── README.md
└── olist_ecommerce_regional_delivery_analysis.ipynb
```

## Data

The notebook loads the Olist tables from the public VBO AI & Data Summer Camp 2026 repository.

The notebook is designed to run in Google Colab or a standard Python/Jupyter environment with internet access.

## Analysis Workflow

```text
Raw Olist Data
      ↓
Data Preparation
      ↓
Customer / Order Joins
      ↓
Regional Aggregations
      ↓
Delivery KPIs
      ↓
Order Value Analysis
      ↓
Visualizations
      ↓
Business Insights
      ↓
Optional PostgreSQL Output
```

## Notes

The analysis is descriptive. Regional differences are observed patterns in the dataset and should not be interpreted as causal findings without additional operational and geographic data.

Database credentials are read through Colab Secrets and are not stored in the repository.

## Author

**Ulaş Yolal**  
Data Analytics / BI / Python / SQL / Data Platforms
