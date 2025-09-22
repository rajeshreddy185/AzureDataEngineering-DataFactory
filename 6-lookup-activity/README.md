## **LOOKUP ACTIVITY**

The Lookup activity in Azure Data Factory (ADF) is a control flow activity used to retrieve a dataset from a data 
source and use its output.

It's designed to read a small amount of data, not for moving large data volumes. (less than 5000 rows or 4 MB)
If the data retrieved by the Lookup activity exceeds either of these limits, the activity will fail.
The data it retrieves is returned as a JSON array.
which can then be referenced by other activities in the pipeline.
Lookup activity expects the return value and how you handle it depends on whether you need a single row or multiple rows.
It can get the data from sql query or from a dataset in adls like list of files.
If it is sql query then it will return a single row or multiple rows based on the query.
By default it is selected as single row.
If it is adls dataset then it will return a single row or multiple rows based on the dataset.


**Common Use Cases**

- Get list of files to copy.
- Get list of tables to loop through.
- Read pipeline configuration values from a control table.
- Validate pre-conditions (e.g., check row counts before proceeding).



Corner Cases:

- If the data retrieved by the Lookup activity exceeds either of these limits, the activity will fail.
- If insert data into table using lookup activity then it will insert all the data into table. but even though it 
  successfully inserted the pipeline will be failed because it is not able to get the return value.
- If the insert statement followed by select query then it will return the inserted data and pipeline is also sucessfull
  (Other ways like script is better for statement or query where there is no return value)