# AzureDataEngineering-DataFactory
Azure data factory activity's

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
