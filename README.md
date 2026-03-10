# Azure Data Factory ETL Project
## Project Overview

This project demonstrates an end-to-end data engineering pipeline built using **Azure Data Factory** and **Azure Data Lake Storage**.
The pipeline ingests data from source systems, processes it through the **Medallion Architecture (Bronze, Silver, Gold layers)**, and prepares it for analytics and reporting.

## Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c05d522a-06c4-4f2b-9eee-844f8f82849a" />


* **Bronze Layer** – Raw data ingestion
* **Silver Layer** – Data cleaning and transformation
* **Gold Layer** – Business-ready data for analytics


## Project Implementation Steps

### 1. Create Azure Resources

* Created a **Resource Group** in Azure.
* Created **Azure Data Factory** instance.
* Created **Azure Data Lake Storage Gen2** account.
* Created necessary containers for storing data.


### 2. Launch Azure Data Factory Studio

Opened ADF Studio to build and manage pipelines.

ADF Studio contains three main sections:

* **Author** – Build pipelines and data flows
* **Monitor** – Track pipeline runs
* **Manage** – Configure linked services and integration runtime


### 3. Create Linked Services

Linked Services were created to connect Azure Data Factory with external systems.

Examples:

* Azure Data Lake Storage
* Azure SQL Database


### 4. Create Datasets

Datasets represent the **structure and location of the data** used in pipelines.

Datasets were created for:

* Bronze layer data
* Silver layer data
* Gold layer data


### 6. Bronze Layer (Raw Data Ingestion)

- Azure Data Factory pipelines ingest CSV data from Github (API).
- Raw data is stored in Azure Data Lake Storage Gen2 (Bronze container).


<img width="2938" height="1546" alt="image" src="https://github.com/user-attachments/assets/e531b113-c6a4-420a-8d29-052a3ec007d4" />



### 7. Silver Layer (Data Cleaning & Transformation)

Data from the Bronze layer is processed and cleaned.

Transformations include:

* Removing duplicates
* Handling null values
* Data formatting
* Data validation


### 8. Gold Layer (Business Ready Data)

The Gold layer contains **aggregated and business-ready datasets**.

Used for:

* Reporting
* Business intelligence
* Analytics dashboards


## Project Outcome

This project demonstrates:

* End-to-end ETL pipeline development
* Implementation of Medallion Architecture
* Data orchestration using Azure Data Factory
* Cloud data storage using Azure Data Lake
* Version control using GitHub


## Future Improvements

* Integration with Databricks for advanced data transformation
* Automation using CI/CD pipelines
* Integration with Power BI for reporting

  
## Technologies Used

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure SQL Database
* Azure Resource Group
