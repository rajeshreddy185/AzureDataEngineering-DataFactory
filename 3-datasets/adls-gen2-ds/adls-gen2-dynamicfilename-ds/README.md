# **DYNAMIC FILE NAME DATASET**

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
    - File Path: Use the file browser to navigate to the specific container, folder you want the dataset to point to.
    - Dynamic File Name: Use the dynamic content feature to define a variable for the file name.
    - Create: Once configured, click OK or Create. The dataset is now ready to be used as a source or sink in your pipelines.
 
