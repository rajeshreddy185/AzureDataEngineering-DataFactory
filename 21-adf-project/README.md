# Dynamic File Ingestion Pipeline in Azure Data Factory

## Overview
This project demonstrates how to create a reusable Azure Data Factory pipeline that dynamically ingests multiple files into their corresponding database tables without hardcoding file or table names.

## Solution Architecture
The solution uses a control table pattern with the following components:
1. **Control Table: Stores mappings between source files and target tables
2. Lookup Activity: Retrieves file-to-table mappings
3. ForEach Activity: Iterates through the mappings
4. Copy Activity: Performs the actual data movement

<img width="900" alt="preparedata" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%208.56.08%20AM.png" />


## Implementation Steps

### 1. Set Up Control Table
Create a control table with at least these columns:
- `FileName`: Path to the source file
- `TableName`: Target database table name

<img width="900" alt="preparedata1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%208.57.45%20AM.png" />

### 2. Retrieve the Mappings (Lookup Activity)
- First, use a Lookup activity to read the mapping information from your control table. 
  This table should contain at least two columns: one for the filename (FileName) and one for the destination 
  table name (TableName).

- Configure the Lookup Activity: Set the source to a dataset that points to your control table.

- Query: Provide a SQL query (e.g., SELECT FileName, TableName FROM YourControlTable) to retrieve the mapping or 
  fetch multiple if the table contains only tablename and filename columns.

Result: The Lookup activity will execute this query and return the results as a JSON array. This array is the list of 
items your pipeline will iterate over.

## 2. Loop Through Mappings (ForEach Activity)
- Next, use a ForEach activity to iterate through the array of mappings returned by the Lookup activity.

- Configure the ForEach Activity: Set its Items property to the output of the Lookup activity using dynamic content:
    @activity('LookupActivityName').output.value

- Inside the Loop: All subsequent activities you want to run for each file-to-table mapping will be placed inside this ForEach loop.

## 3. Copy Data Dynamically (Copy Activity)
- Finally, place a Copy activity inside the ForEach loop. This activity will dynamically pick up the filename and tablename for each iteration.

- Source Dataset: In the Copy activity's Source tab, pass the current filename from the loop to your source dataset's file path parameter using dynamic content:
@item().FileName

- Sink Dataset: In the Sink tab, pass the corresponding tablename to your sink dataset's table name parameter using dynamic content:
@item().TableName

To create dynamic file dataset:

[https://github.com/rajeshreddy185/AzureDataEngineering-DataFactory/blob/main/3-datasets/adls-gen2-ds/adls-gen2-dynamicfilename-ds/README.md
](https://github.com/rajeshreddy185/AzureDataEngineering-DataFactory/blob/main/3-datasets/adls-gen2-ds/adls-gen2-dynamicfilename-ds/README.md#:~:text=DYNAMIC%20FILE%20NAME,in%20your%20pipelines.) 

Dynamic table dataset:

<img width="900" alt="dynamictable" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.09.36%20AM.png" />

<img width="900" alt="projectview" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.09.56%20AM.png" />

<img width="900" alt="output" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.13.28%20AM.png" />
