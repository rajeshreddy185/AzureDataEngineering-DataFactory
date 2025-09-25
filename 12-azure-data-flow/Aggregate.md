# AGGREGATE

Aggregate transformation. This transformation is the equivalent of a GROUP BY clause in SQL, allowing you to group rows 
based on a specific column and then perform calculations on each group.

Define the Group By: In the Group by tab of the Aggregate transformation settings, 
you specify the column(s) you want to group your data by.
Click on the ship_mode column from the dropdown list. This tells the data flow to create a separate group 
for each unique value in the ship_mode column (e.g., 'Standard Class', 'First Class', etc.).

<img width="900" alt="aggregate1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.19.06%20AM.png" />

Define the Aggregates: In the Aggregates tab, you define the calculations you want to perform on each group.
New Column: Give your new aggregated column a name, such as TotalSales.
Expression: Use the Expression Builder to write the aggregation function. For summing sales, you would use the sum() 
function. The expression would look like this: `sum(sales)` sales is the name of the column you want to sum.

<img width="900" alt="aggregate2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.19.13%20AM.png" />

**output looks like this**

<img width="900" alt="aggregate" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.18.56%20AM.png" />