# Azure Data Factory (ADF) Overview

## What is Azure Data Factory?
- **Type**: Fully managed, serverless, cloud-based data integration service
- **Purpose**: Create, schedule, and orchestrate automated data workflows (pipelines)
- **Primary Role**: 
  - Extract data from various sources
  - Perform lightweight transformations
  - Load data into target destinations

## Key Characteristics
- Acts as a control service that orchestrates other Azure compute services
- Leverages services like Databricks or Synapse for heavy data transformation
- Provides visual tools for pipeline creation and management

## Use Cases

### 1. Data Migration
- Migrate large volumes of data from on-premises systems to Azure
- Supports sources like SQL Server, Oracle, Azure Data Lake Storage, Azure SQL Database etc.

### 2. ETL/ELT Workflows
- Central orchestrator for complete data integration pipelines
- Supports both ETL (Extract, Transform, Load) and ELT (Extract, Load, Transform) patterns
- Features Data Flow for visual data transformation
- Integrates with data warehouses like Azure Synapse Analytics

### 3. Hybrid Data Integration
- Uses Self-Hosted Integration Runtime for secure connections
- Enables data movement from private networks to cloud
- Supports on-premises to cloud data integration

### 5. Operational Data Pipelines
- Builds and schedules recurring data pipelines
- Ensures analytical data remains up-to-date
- Example: Automates daily sales data ingestion from operational databases to data lakes


# AZURE DATA FLOW
----------------

Azure Data Flow is a feature within Azure Data Factory (ADF) that provides a visual, no-code/low-code environment for 
data transformation. It helps us to build and manage complex data transformation logic using a drag-and-drop interface. 
Data flows run on scaled-out Apache Spark clusters, which are fully managed by ADF, so you don't need to manage 
the underlying infrastructure.


## Key Characteristics
- Visual, no-code/low-code environment for data transformation
- Data flows run on a fully managed Apache Spark cluster in the background no need to manage.
- Because they run on Spark clusters, data flows are designed for large-scale data processing.
-  Data flows come with a rich set of built-in transformations for common data manipulation tasks 
   (ex filter, join, aggregate, etc.)
- Building your data flow, you can turn on debug mode to interactively preview data at each transformation step.
- Data flows are built to be resilient to changes in the source schema. With schema drift.
- As an activity within an ADF pipeline, data flows seamlessly integrate with all other ADF features.
- Data flows can connect to and transform data from numerous data stores, both within and outside of Azure. 




## Three main parts:

**Sources**: Where you read the data from.
**Transformations**: The logic you apply to the data, such as filtering, joining, aggregating, or cleansing.
**Sinks**: The destination where the transformed data is written.


## USE CASE

**Data Lake Ingestion and Transformation**
Data flows are excellent for processing large volumes of data in a data lake, which often contains raw, unstructured, 
or semi-structured files.
File Transformation: Reading data from various file formats (CSV, JSON, Parquet) and transforming it into a structured 
and optimized format like Parquet or Delta Lake.
Schema Enforcement and Evolution: When dealing with files that might have inconsistent schemas (schema drift), data 
flows can automatically handle these changes, ensuring a resilient pipeline.

**Data Migration & Incremental Data Loading**
When you need to migrate large volumes of data from on-premises systems to the cloud, data flows can be a key part 
of the solution. Data flows support incremental data loading patterns. Instead of processing all the data every time, 
you can configure the data flow to only process new or changed data. This is done by using "watermarks," where the data 
flow remembers the last processed timestamp or a specific key to only retrieve new data in subsequent runs. 

**Data Integration from Multiple Sources**
Data flows are designed to integrate data from diverse sources into a single, cohesive dataset.you can combine data from 
one system with transaction data from a relational database and stream data from a file-based source.

**Data Quality and Validation**
You can use data flows to build data quality checks directly into your pipelines. For instance, you can use the 
Conditional Split transformation to route records that fail a validation check

