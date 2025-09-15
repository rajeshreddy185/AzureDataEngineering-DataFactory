# **DATA SETS**


## - **DATA SETS**
    - A dataset in Azure Data Factory (ADF) is a named reference to a specific piece of data you want to use in your pipelines.
    - While a linked service acts as the connection string to a data store, 
    - the dataset defines the structure, schema, and location of the data within that store.


- **CREATE A NEW DATASET**
    - Click the + sign and select Dataset from the dropdown menu.

- **SELECT DATA STORE**
    - In the connector gallery, search for "Azure Data Lake Storage Gen2" and select it. Click Continue.

- **CHOOSE A FORMAT**
    - Next, you'll be prompted to choose a file format for your data. This is mandatory and tells the pipeline how to read the data. Common formats include:
        - Delimited Text (for CSVs)
        - Parquet
        - JSON
        - Binary (if you don't want to parse the files)
    - Click Continue.

- **CONFIGURE THE DATASET**
    - Name: Give your dataset a descriptive name.
    - Linked Service: Select the existing ADLS Gen2 linked service you created earlier.
    - File Path: Use the file browser to navigate to the specific container, folder, or file(s) you want the dataset to point to.
    - Create: Once configured, click OK or Create. The dataset is now ready to be used as a source or sink in your pipelines.
 
<img width="900" alt="adlsgen2ds1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2011.39.19%20PM.png" />

<img width="900" alt="adlsgen2ds2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2011.40.30%20PM.png" />


