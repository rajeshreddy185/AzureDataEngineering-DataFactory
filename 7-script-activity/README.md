## **SCRIPT ACTIVITY**

The Script activity in Azure Data Factory (ADF) that allows you to execute SQL or other database scripts directly 
against a data store. It's designed for scenarios where you need to run commands that don't necessarily return a value,
such as data manipulation language (DML) or data definition language (DDL) statements.


**Common Use Cases**

- Data Insertion: Insert data into a table from a parameter or a variable.
- Table Creation: Create a temporary table or a new table as part of a pipeline.
- Data Deletion: Truncate a table or delete specific rows before a new data load.
- Stored Procedure Execution: Call a stored procedure that does not return any data.
- Logging: Write audit records or logging information into a control table.

<img width="900" alt="scriptinsert" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.30.48%20PM.png" />

<img width="900" alt="scriptinsertoutput" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.31.07%20PM.png" />

No Return Value Needed: Unlike a Lookup activity, the Script activity does not require a return value to succeed. 
It's ideal for INSERT, UPDATE, DELETE, or CREATE TABLE statements.

Flexible Inputs: You can pass parameters to the script from your pipeline, making the commands dynamic. 
For instance, you could pass a file name or a row count to an INSERT statement.

Multiple Scripts: The activity can execute a single script or multiple scripts.

However, if the script fails, the activity will fail, and you won't get any output.

<img width="900" alt="scriptselect" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.32.24%20PM.png" />

<img width="900" alt="scriptselectoutput" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.32.15%20PM.png" />

