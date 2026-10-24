# Olist E-Commerce: Regional Order & Delivery Performance Analysis

A portfolio-oriented data analytics project using public Olist Brazilian
e-commerce order data. The project examines regional order volume,
average order value, and delivery performance using Python and Pandas,
with an optional PostgreSQL output step prepared using SQLAlchemy.

## Project Objective

Analyze order and delivery data to understand differences across
Brazilian states and translate descriptive metrics into practical
operational insights.

The analysis addresses the following business questions:

-   Which states generate the highest order volume?
-   How long do deliveries typically take?
-   Which states have the longest average delivery times?
-   How does average order value (AOV) vary by state?
-   How can order volume, order value, and delivery performance be
    interpreted together?

## Key Findings

The figures below reflect the saved outputs in
`olist_delivery_analysis.ipynb`.

-   **99,441 orders** and **112,650 order items** were included in the
    source tables.
-   Customers are represented across **27 Brazilian states**.
-   **São Paulo (SP)** had the highest order volume, with **41,746
    orders**. Rio de Janeiro (RJ) and Minas Gerais (MG) followed with
    12,852 and 11,635 orders, respectively.
-   The **median delivery time was 10 days**.
-   The **90th percentile (P90) delivery time was 23 days**. This means
    the 90th-percentile threshold of the observed delivery-time
    distribution was 23 days; it does not, by itself, indicate whether a
    delivery SLA was met.
-   The largest difference between state-level average delivery times
    was approximately **20.68 days**. Roraima (RR) had the highest
    average delivery time in the saved output, while São Paulo (SP) had
    the lowest.
-   The five states with the longest average delivery times were **RR,
    AP, AM, AL, and PA**.
-   The five states with the highest average order value in the saved
    output were **PB, AP, AC, AL, and RO**.

These are descriptive findings from the current notebook outputs.
Regional differences should not be interpreted as causal relationships
without additional evidence.

## Analysis Workflow

1.  Load the Olist orders, order items, and customer tables.
2.  Prepare timestamps and calculate delivery duration for delivered
    orders.
3.  Join orders with customer location data.
4.  Aggregate order volume by state.
5.  Calculate delivery-time metrics, including median and P90.
6.  Compare average delivery times across states.
7.  Calculate average order value by state.
8.  Visualize the results and interpret them from a business
    perspective.
9.  Optionally write state-level delivery performance results to
    PostgreSQL.

## Repository Structure

``` text
Olist-Ecommerce-Delivery-Analysis/
├── README.md
├── README_Eng.md
├── olist_delivery_analysis.ipynb
├── olist_customers_dataset.csv
├── olist_order_items_dataset.csv
└── olist_orders_dataset.csv
```

## Data Sources

The notebook currently loads the three source tables directly from the
public VBO AI & Data Summer Camp 2026 GitHub repository:

-   `olist_orders_dataset.csv` --- order status and purchase/delivery
    timestamps.
-   `olist_order_items_dataset.csv` --- order items, seller IDs, prices,
    freight values, and shipping-limit timestamps.
-   `olist_customers_dataset.csv` --- customer identifiers and
    geographic information, including state.

Source repository:\
https://github.com/cemalcici/vbo-summer-camp-2026/tree/main/data

Copies of these CSV files are also included in this repository. **The
notebook's current loading code uses the public source URL above rather
than reading the local CSV copies.** If the notebook is changed to load
local files, update this section and the loading code accordingly.

## Technologies

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   PostgreSQL
-   SQLAlchemy
-   Neon PostgreSQL
-   Jupyter Notebook / Google Colab

## Run the Notebook

Open `olist_delivery_analysis.ipynb` in Google Colab or a local Jupyter
environment with internet access.

Install the required libraries if they are not already available:

``` bash
pip install pandas numpy matplotlib sqlalchemy psycopg2-binary
```

The notebook downloads the source tables from the public GitHub URL, so
internet access is required for the current data-loading approach.

### Optional PostgreSQL Integration

The notebook includes an optional SQLAlchemy step to write state-level
delivery-performance results to PostgreSQL. To run it, define a valid
`DATABASE_URL` environment variable or configure it through a secure
secrets manager such as Google Colab Secrets.

Do not commit database credentials to the repository.

**Execution note:** In the saved notebook run, `DATABASE_URL` was not
configured, so the PostgreSQL write step was not executed. The notebook
contains the integration code, but this saved run does not demonstrate a
completed database upload.

## Business Interpretation

High order volume and long delivery times should be examined as separate
dimensions. Combining regional demand, delivery duration, and order
value can help identify areas for further investigation. Additional
data---such as shipping distance, carrier performance, freight cost, and
logistics network coverage---would be needed to investigate the reasons
behind observed differences.

The analysis is descriptive; it does not establish causal relationships
or confirm SLA compliance because an explicit SLA target is not defined
in the current analysis.

## Author

**Ulaş Yolal**\
Data Analytics · Business Intelligence · Python · SQL · Data Platforms
