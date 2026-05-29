# Instacart Market Basket Analysis

## Project Overview
This project performs a comprehensive data analysis on the Instacart Market Basket dataset using **Apache Spark (PySpark)**. The goal is to process over 32 million transaction records to extract actionable business insights regarding customer purchasing behavior, product popularity, and departmental performance. 

By leveraging big data processing techniques, this pipeline transforms raw transactional data into strategic intelligence that can drive inventory management, staffing optimizations, and targeted marketing.

---

## 🛠️ Technology Stack
* **Big Data Processing:** Apache Spark (PySpark), SparkSQL
* **Languages:** Python, SQL
* **Environment & APIs:** Google Colab, Kaggle Dataset API

---

## 🏗️ Pipeline Architecture

### 1. Data Engineering & Preprocessing
The foundation of the project involves ingesting and unifying massive, disparate datasets into a single analytical view:
* **Automated Ingestion:** Configured a SparkSession integrated with `kagglehub` for automated retrieval of large-scale CSV files (Orders, Products, Departments, Aisles, and Order-Products).
* **Schema Optimization:** Loaded data into Spark DataFrames with optimized schema inference to handle memory efficiently.
* **Data Cleansing:** Performed rigorous deduplication and null-value analysis. Specifically handled missing values in the `days_since_prior_order` column to ensure longitudinal analytical integrity.
* **Data Unification:** Executed complex joins across the five relational tables to create a unified dataset of over 32 million records.

### 2. Feature Engineering
Advanced metrics were calculated utilizing **Spark Window Functions** to build a deeper understanding of user habits:
* Calculated total items per specific order.
* Derived reorder ratios per transaction.
* Engineered average order frequency metrics per unique user.

### 3. Business Intelligence & SQL Analytics
Leveraging both SparkSQL and the DataFrame API, the unified data was queried to answer critical operational questions:

| Focus Area | Strategic Insights Extracted |
| :--- | :--- |
| **Volume & Revenue** | Identified the top 10 departments by order volume, highlighting the percentage contribution of each to total sales (with Produce and Dairy driving majority traffic). |
| **Operational Strategy** | Mapped peak shopping hours (10 AM - 4 PM) to provide data-backed suggestions for warehouse and delivery staffing optimizations. |
| **Inventory & Loyalty** | Calculated reorder rates per department to pinpoint high-retention categories. Identified the most frequently reordered 'staple' products (e.g., Bananas, Organic Baby Spinach) for supply chain prioritization. |

### 4. Customer Segmentation
To transition from descriptive analytics to actionable marketing strategy, a user segmentation model was developed. Customers were categorized into **Low, Medium, and High Activity** cohorts based on their lifetime order frequency. This enables targeted retention campaigns and personalized promotional strategies.

---

## 🚀 How to Run
1. Open the provided `.ipynb` notebook in Google Colab (or your local Spark environment).
2. The Kaggle API will automatically fetch the necessary datasets during the initial setup cell.
3. Run the notebook sequentially to execute the data ingestion, ETL pipeline, and SQL analytics.
