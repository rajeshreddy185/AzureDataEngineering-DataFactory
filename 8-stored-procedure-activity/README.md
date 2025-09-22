## **STORED PROCEDURE ACTIVITY**

A stored procedure is a pre-compiled set of one or more SQL statements stored in a relational database. 
It's essentially a subprogram or function that can be called and executed from an application,
another stored procedure, or a data integration tool like Azure Data Factory.

Pre-compiled: When a stored procedure is created, the database management system (DBMS) compiles and optimizes it. 
This makes it faster and more efficient to execute than running a series of individual, uncompiled SQL statements.

Parameters: You can pass input parameters to a stored procedure and receive output parameters,
making them highly flexible for different use cases.

Common Use Cases

Data Insertion: Insert data into a table from a parameter or a variable.
Table Creation: Create a temporary table or a new table as part of a pipeline.
Data Deletion: Truncate a table or delete specific rows before a new data load.
Stored Procedure Execution: Call a stored procedure that does not return any data.

Catch is it won't return anything in return after execution
unlike lookup activity where it returns either first row only or multiple rows (limited to 5000 rows or 4mb data)
unlike script activity where it returns the output of the script for select statement in json or run dml ddl statement.

CREATE AN STORED PROCEDURE

<img width="900" alt="storedprocedureacreate" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.58.36%20PM.png" />

USE IT IN ADF

<img width="900" alt="storedprocedureactivity" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.58.01%20PM.png" />

<img width="900" alt="storedprocedureactivityoutput" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-22%20at%2010.58.18%20PM.png" />

No Return Value Needed: Unlike a Lookup activity, the Script activity does not require a return value to succeed. 
