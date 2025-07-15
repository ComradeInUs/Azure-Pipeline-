# Retail analysis using azure etl pipeline 
This project outlines a comprehensive Extract, Transform, and Load (ETL) pipeline built on **Microsoft Azure**, designed for analyzing e-commerce sales data. It efficiently pulls data from **Azure Blob Storage**, transforms it using **Azure Databricks** and **Azure Data Factory**, and stages it in **Azure Data Lake** (supporting Delta and Parquet formats). A key component involves **PySpark** within Databricks for in-depth sales analysis, with the final processed data stored in an **Azure SQL layer** for reporting. This solution streamlines data processing to deliver actionable sales insights.

---

### Dataset Overview

The project utilizes a detailed e-commerce dataset of **Amazon India sales transactions**. This dataset encompasses customer information, product details, order specifics, payment methods, and shipping data, enabling a thorough examination of sales trends, customer behavior, and profitability within the e-commerce domain.

---

### Prerequisites

To implement this project, the following Azure services are essential:
* **Microsoft Azure Subscription**
* **Azure Blob Storage**: For scalable unstructured data storage.
* **Azure Data Lake Gen2 Storage**: A highly scalable solution for big data analytics.
* **Azure Databricks**: An advanced Apache Spark-based platform for processing and data science.
* **Azure SQL Server** / **Azure SQL Database**: Managed relational database services for storing processed data.
* **Azure Data Factory**: For orchestrating and automating ETL/ELT workflows.

---

### Data Flow

The project's data flow is structured into distinct phases:

* **Extract Data**: CSV data is retrieved from Azure Blob Storage and loaded into Azure Data Lake Storage Gen-2.
* **Transform Data**: **PySpark** on Azure Databricks processes and analyzes the data, storing results in Azure Data Lake Storage Gen2.
* **Load Data**: The transformed data is then transferred into an Azure SQL database, serving as a reporting layer.
* **Automation**: End-to-end pipelines are constructed in **Azure Data Factory** to automate the entire data flow, from extraction to the reporting layer.

---

### Setup and Configuration

Setting up the pipeline involves configuring each Azure component:

* **Azure Blob Storage**: Create a container and upload input data.
* **Azure Data Lake Storage**: Create a file system and a directory for processed Parquet files.
* **Azure Databricks**: Set up a cluster (e.g., 9.1 LTS with Spark 3.1.2) and create a new notebook.
* **Azure SQL Database**: Create a SQL database and define necessary tables for processed data.
* **Azure Data Factory**: Create a new pipeline, establish linked services for Blob Storage, Data Lake Gen2, Databricks, and SQL. Add activities to copy data, process in Databricks, and load into SQL DB.
* **Running the Pipeline**: Trigger and monitor the "Run All Pipelines" in Azure Data Factory for successful completion. The pipelines are structured sequentially: `Pipeline #1: Copy Data from Blob to ADLS`, `Pipeline #2: Trigger all Databricks Notebook Runs`, `Pipeline #3: Copy Data from ADLS to SQL DB`, and `Pipeline #4: Trigger all Pipelines` to orchestrate the entire workflow.

---

### Analysis

This project performs a comprehensive analysis of e-commerce sales data, organized into six key areas to provide diverse business insights:

* **Statewise Sales Analysis**: Provides a detailed breakdown of sales metrics (orders, quantity, amount) across Indian states to understand regional trends and performance for targeted marketing.
* **Categorywise Sales Analysis**: Offers insights into sales data by apparel type, including orders, quantity, and sales amount, to identify popular categories and inform inventory and product development.
* **Promotion Impact Analysis**: Evaluates the effectiveness of sales promotions by comparing metrics with and without promotional application, helping to understand their influence on purchasing behavior.
* **Cancellation Impact Analysis**: Assesses the effect of order cancellations on sales, providing metrics on cancelled orders, quantity, and sales amount to identify patterns and minimize negative impacts.
* **Size-wise Sales Analysis**: Delivers insights into sales by apparel size, covering both sales amount and quantity, to inform product sizing, inventory management, and marketing strategies based on customer preferences.
* **International Orders Analysis**: Focuses on sales data for apparel shipped outside India, including order counts and sales amounts, to understand global demand and guide international expansion and marketing efforts.

Overall, these analyses provide actionable insights for optimizing sales performance, managing inventory, and tailoring strategies to meet customer demands effectively across various dimensions.
