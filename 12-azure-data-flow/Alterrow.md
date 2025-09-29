# **ALTERROW**


The Alter Row transformation in Azure Data Flow is used to specify how rows should be handled in a database sink 
(destination), enabling insert, update, delete, and upsert operations based on logical conditions. It is the core
mechanism for Change Data Capture (CDC) within a data flow.

How to Use the Alter Row Transformation

Add the Alter Row Transformation: In your data flow, add an Alter Row transformation and connect it to the data stream 
containing the data you want to modify.

Define the Operation: In the Alter Row settings, you define the operation to perform on each row. You can choose from:

Insert: Insert a new row into the database.
Update: Update an existing row in the database.
Delete: Delete an existing row from the database.
Upsert: Update or insert a row based on a unique key.

Define the Condition: You can define a condition to determine which rows should be modified. 

Define the Key: You can define the key to use for the upsert operation. 

Define the Output Columns: You can define the output columns to be used for the upsert operation.

Let's say we have a data set of movie ratings:

Deleting Data 
The first example shows how to delete specific rows from a movie database table.

Setup: The data flow uses the same database table as both the source and the sink.
This allows it to read data from the table and then write changes back to it.

Condition: An Alter Row condition is set to delete() for any row where 
the movie's year is before 1900 or the year is null.

Action: The database sink is specifically configured to only allow delete operations. 
This prevents the transformation from accidentally inserting or updating any records.

This process efficiently removes old or incomplete movie records from the table.


The video uses two main examples to demonstrate the Alter Row transformation: one for deleting data and another for updating data.

Deleting Data 🗑️
The first example shows how to delete specific rows from a movie database table.

Setup: The data flow uses the same database table as both the source and the sink. This allows it to read data from the table and then write changes back to it.

Condition: An Alter Row condition is set to delete() for any row where the movie's year is before 1900 or the year is null.

Action: The database sink is specifically configured to only allow delete operations. This prevents the transformation from accidentally inserting or updating any records.

This process efficiently removes old or incomplete movie records from the table.

Updating Data
The second example demonstrates how to update existing data, specifically to resolve a duplicate record issue.

Problem: There are two different movies with the same title, "20,000 Leagues Under the Sea."

Solution: A Derived Column transformation is used to create a new, unique title by appending the year to the existing 
title (e.g., "20,000 Leagues Under the Sea (1954)").

Condition: The Alter Row transformation is configured to update() rows where the title matches the original, 
non-unique name. This ensures that only the two specific records are targeted for the change.

Action: The sink is then configured to only allow update operations.