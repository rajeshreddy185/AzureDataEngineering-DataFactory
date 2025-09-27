# **PIVOT**

The Pivot transformation in Azure Data Flow is used to convert data from a row-based format into a column-based format. 
It's a key operation in data reshaping and is useful for summarizing and aggregating data to make it easier for analysis
and reporting.

How to Use a Pivot Transformation
The Pivot transformation takes a set of distinct values from a single column and turns them into multiple new columns. 
You need to define three things:

Pivot Key: The column whose unique values will become the new column headers.

Pivot Column: The column containing the values that will populate the new pivoted columns.

Grouping Columns: One or more columns to group the data by. This is the equivalent of the GROUP BY clause and ensures 
the aggregation is done correctly for each group.

Let's say you have a sales dataset with columns for State, Product, and profit. 
You want to see the total profit for each Product and State in a single row, with State as new columns.

<img width="900" alt="pivot1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2011.39.33%20PM.png" />

<img width="900" alt="pivot2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2011.39.41%20PM.png" />

<img width="900" alt="pivot3" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2011.39.52%20PM.png" />

<img width="900" alt="pivot4" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2011.40.04%20PM.png" />
