
# **Union vs. Union All**

The Union transformation in Azure Data Flow is used to combine data from two or more data streams into a single stream. 
It's a way to append rows from different sources that have a compatible schema. Unlike a join, which combines data
horizontally, a union combines data vertically.

Union vs. Union All
In SQL, there's a distinction between UNION and UNION ALL:

UNION removes duplicate rows from the final result set.

UNION ALL includes all rows from all sources, including duplicates.

In Azure Data Flow, the Union transformation is a direct equivalent of a SQL UNION ALL. It combines all rows from all 
input streams without removing duplicates. If you need to remove duplicates after a union, you would follow the Union
transformation with an Aggregate transformation (grouping by all columns) or a Sort followed by a Filter to achieve the 
equivalent of a SQL UNION.

How to Use a Union Transformation
Add the Transformation: In your data flow canvas, add a Union transformation.

Define Input Streams: Connect two or more data streams to the Union transformation. The streams must have a compatible 
schema. This means the columns should have the same names and data types, or be mappable to a common schema.

Map Columns: The Union transformation automatically tries to map columns with the same name. If your input streams 
have different column names for the same data (e.g., cust_id and customer_id), you can manually specify the mapping to
ensure the data is aligned correctly in the output stream.

<img width="900" alt="union1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2011.54.38%20PM.png" />