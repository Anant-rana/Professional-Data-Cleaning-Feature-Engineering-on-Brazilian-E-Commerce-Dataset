# End-to-End E-Commerce Analytics System

**Professional Data Cleaning & Feature Engineering on Brazilian E-Commerce Dataset (Olist)**


## Problem Statement

Real-world e-commerce data is usually messy — with missing timestamps, inconsistent date formats, and incomplete delivery information. This makes it difficult for companies to analyze delivery performance, customer behavior, seasonality, and late deliveries.

This project solves these challenges by building a complete **pandas-based End-to-End Data Cleaning Pipeline** for the popular Olist Brazilian E-commerce dataset.

## Solution

I developed a robust **data cleaning and transformation system** using pandas that:

- Loads 5 raw datasets
- Handles missing values with proper business logic
- Safely converts date columns
- Creates useful business features
- Generates 5 clean, analysis-ready CSV files

The cleaned data is now ready for dashboards (Power BI/Tableau), SQL analysis, or further machine learning.

## Objectives

- Load raw e-commerce datasets (customers, orders, items, payments, products)
- Perform professional pandas data cleaning and missing value handling
- Safely manage datetime columns and avoid common errors
- Engineer business-relevant features (delivery days, late delivery flag, seasonality, etc.)
- Produce clean datasets for downstream analysis

## Dataset Description

**Original Messy Data:** `archive.zip` (contains raw CSV files downloaded from Kaggle - Olist Brazilian E-commerce)

**Cleaned Files Created:**
- `customers_clean.csv`
- `orders_clean.csv`
- `items_clean.csv`
- `payments_clean.csv`
- `products_clean.csv`

## Data Cleaning & Transformation (Using Pandas)

### Key Steps Performed:

1. **Loading Raw Data**
   - Loaded all 5 datasets using `pd.read_csv()`

2. **Missing Value Handling**
   - Identified large number of missing values in timestamp columns (`order_approved_at`, `order_delivered_carrier_date`, `order_delivered_customer_date`)
   - Safely converted all date columns to datetime with `pd.to_datetime(errors='coerce')`
   - Filled `order_approved_at` using `order_purchase_timestamp`
   - For **delivered orders**, intelligently imputed carrier and delivery dates using logical estimates
   - Created `carrier_date_missing` flag to track originally missing values
   - Preserved canceled and unavailable orders (realistic business behavior)

3. **Feature Engineering**
   - Extracted temporal features: `year`, `month`, `day_of_week`, `quarter`, `is_weekend`
   - Created delivery performance metrics: `delivery_days` and `late_delivery` flag
   - Added `carrier_date_missing` indicator for analysis

4. **Saving Clean Data**
   - Exported 5 production-ready clean CSV files

## Technologies Used

- Python 3
- pandas (main library for data cleaning and transformation)
- numpy
- KaggleHub (dataset download)
- Jupyter Notebook

## Project Structure

- `End_to_End_E_commerce_Analytics_System.ipynb` → Complete Jupyter Notebook with full pipeline
- `archive.zip` → Original raw/messy dataset (for reference)
- Cleaned CSV files (customers_clean.csv, orders_clean.csv, etc.)

## Results - Phase 1

### Place 1: Data Cleaning & Feature Engineering Screenshots


## Missing Values Before Cleaning
<img width="427" height="275" alt="before cleaoning missing values pandas" src="https://github.com/user-attachments/assets/7fe0feee-2ddc-4538-829f-ebcbd432722b" />

## Missing Values After Cleaning 
<img width="342" height="422" alt="after cleaing missing values pandas" src="https://github.com/user-attachments/assets/1760fb7d-65b4-4681-a6ba-55a33213107c" />

## Feature Engineering Output 
<img width="916" height="177" alt="feature engineering pandas" src="https://github.com/user-attachments/assets/4f10f4f2-273c-4bcd-ab89-ac3dcfd4d030" />

## Clean Files Saved Confirmation 
<img width="535" height="178" alt="Screenshot 2026-04-13 224510" src="https://github.com/user-attachments/assets/8451a484-2ff9-4e8b-948d-377139a35df0" />


**Key Achievements:**
- Successfully handled hundreds of missing timestamp values using business logic
- Created 8+ new actionable features for analytics
- Generated clean, consistent datasets ready for visualization and reporting

## Real-Life Business Benefits

- Accurate delivery performance tracking (late deliveries, average delivery days)
- Seasonality and weekend sales analysis
- Better logistics and customer experience insights
- Ready for Power BI / Tableau dashboards
- Foundation for advanced analytics or predictive models

## How to Run

1. Clone this repository
2. Open `End_to_End_E_commerce_Analytics_System.ipynb` in Jupyter Notebook or Google Colab
3. Run all cells in order
4. Cleaned CSV files will be generated automatically

## Future Improvements (Phase 2)

- Merge all tables into a star schema
- Build interactive Power BI / Tableau dashboard
- Perform RFM customer segmentation
- Add predictive modeling for late delivery risk
- Automate the pipeline as ETL process

## Full Notebook

The complete step-by-step code with detailed comments and realistic data engineering decisions is available in the Jupyter Notebook.

---

**Professional pandas data cleaning for real-world e-commerce analytics.**

Made with ❤️ | Quebec, Canada
