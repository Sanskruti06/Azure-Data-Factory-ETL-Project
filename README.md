# Azure Data Factory ETL Project
## Project Overview

This project demonstrates an end-to-end data engineering pipeline built using **Azure Data Factory** and **Azure Data Lake Storage**.
The pipeline ingests data from source systems, processes it through the **Medallion Architecture (Bronze, Silver, Gold layers)**, and prepares it for analytics and reporting.

## Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c05d522a-06c4-4f2b-9eee-844f8f82849a" />


* **Bronze Layer** – Raw data ingestion
* **Silver Layer** – Data cleaning and transformation
* **Gold Layer** – Business-ready data for analytics


### Project Implementation Steps

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

<img width="2934" height="1548" alt="image" src="https://github.com/user-attachments/assets/0ec4d8df-7ee2-4059-920a-6c2736a2eeae" />


### a) Incremental Data Loading in ADF

* Implemented **incremental data loading** using the **watermark technique**.
* Used **Lookup Activity** to retrieve the last processed watermark value.
* Identified new records in the source table using a **timestamp / incremental column**.
* Used **Copy Activity** to load only new or updated records into **Azure Data Lake**.
* Updated the watermark value after each successful pipeline run for future loads.

<img width="2938" height="1548" alt="image" src="https://github.com/user-attachments/assets/fd847404-91e6-4803-b4c1-578c04c1efd3" />

<img width="2938" height="1550" alt="image" src="https://github.com/user-attachments/assets/8a7e3116-2467-4232-adeb-8ac24707e526" />


### b) Logic App Integration

* Created an **Azure Logic App** to automate pipeline notifications.
* Configured a **trigger to detect pipeline events / failures**.
* Integrated Logic App with **Azure Data Factory pipeline alerts**.
* Added an **email notification step** to notify users about pipeline status.
* Enabled **automated monitoring and alerting** for pipeline execution.

<img width="2918" height="1550" alt="image" src="https://github.com/user-attachments/assets/42e1fb5f-e1cf-4b55-b2f4-710e9f15a9be" />

<img width="2938" height="1488" alt="image" src="https://github.com/user-attachments/assets/4a8da884-bf13-4abd-8517-d6fd303e381a" />


### 7. Silver Layer (Data Cleaning & Transformation)

Data from the Bronze layer is processed and cleaned.

Transformations include:

* Removing duplicates
* Handling null values
* Data formatting
* Data validation

<img width="2938" height="1540" alt="image" src="https://github.com/user-attachments/assets/77ca34a8-a10a-4351-bec6-c38b3892729a" />

<img width="2938" height="1540" alt="image" src="https://github.com/user-attachments/assets/0162a8e3-6f1a-4869-a816-0af12548132c" />


### 8. Gold Layer (Business Ready Data)

The Gold layer contains aggregated and business-ready datasets.

Used for:

* Reporting
* Business intelligence
* Analytics dashboards

<img width="2938" height="1544" alt="image" src="https://github.com/user-attachments/assets/423ee64f-2547-4ebb-9025-54ae980dffa4" />


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
