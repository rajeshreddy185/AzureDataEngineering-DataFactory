# FILTER 

To filter data in an Azure Data Flow, you use the Filter transformation. This transformation allows you to select a 
subset of rows from your data stream based on a logical condition, similar to a WHERE clause in SQL. 
It's a key part of data cleansing and reducing the volume of data processed.


How to Use the Filter Transformation
Add the Filter Transformation: In your data flow, add a Filter transformation and connect it after your data source or a 
preceding transformation.
Define the Condition: In the filter settings, you use the Expression Builder to define a condition that returns a boolean 
(true or false) value. Rows for which the condition evaluates to true will be passed to the next stage of the data flow,
while rows that evaluate to false will be dropped.

Example Expression:
`ship_mode == 'Standard Class'`

<img width="900" alt="filter" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.10.25%20AM.png" />

<img width="900" alt="filter1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.11.35%20AM.png" />

