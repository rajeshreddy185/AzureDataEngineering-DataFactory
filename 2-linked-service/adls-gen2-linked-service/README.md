# Linked Service

A linked service in Azure Data Factory (ADF) is a component that acts like a connection string. 
It holds the connection information required for ADF to connect to external resources, 
such as databases, file systems, cloud storage, or other services.

Azure Data Lake Storage GEN2 (Adls gen2) Linked service (FROM AZURE SUBSCRIPTION)
--------------------------------------------------------
- Navigate to Linked Services
  - In the ADF authoring UI, click on the Manage tab on the left-hand menu.
  - Under the Connections section, select Linked services.
  - Click on + New to create a new linked service.

- Choose a Data Store
  - A list of supported data store types will appear. You can search for the one you want to connect to (e.g., "Azure Blob Storage," "SQL Server," or "Salesforce").
  - Here, select ADLS gen2.

- Configure the Linked Service
  - Provide a name for your linked service.
  - Fill in the required connection details. These will vary depending on the type of data store you selected.
    - For ADLS Gen2:
      - Select subscription and storage account you want to connect.
      - Authentication type: How you will authenticate the connection (e.g., Account Key, Managed Identity, Service Principal).

- Create the Linked Service
  - Once the connection test is successful, click Create to save and finalize your linked service.

<img width="900" alt="adlsgen2ls" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%209.59.24%20PM.png" />

<img width="900" alt="adlsgen2ls1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.00.34%20PM.png" />
