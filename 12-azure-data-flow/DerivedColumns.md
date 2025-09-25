# Derived Columns


In Azure Data Flow, the Derived Column transformation is a powerful tool for creating new columns or modifying existing 
ones using expressions. It's a fundamental part of the data enrichment process in ETL.

To combine order_id and ship_mode into a single, new column using a concat function, you'd use the Derived Column transformation in an Azure Data Flow. This is a common practice for creating a unique key or a more descriptive identifier.

The Derived Column Transformation
The Derived Column transformation allows you to define a new column and provide an expression to populate its values. In this case, the expression would use the concat() function.
New Column Name: You would give your new column a descriptive name, like order_shipmode_comb.
Expression: The expression would join the two existing columns. A common approach is to separate them with a delimiter for readability.

Example Expression:
`concat(order_id, ship_mode)`

<img width="900" alt="derivedcolumns1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.03.54%20AM.png" />

<img width="900" alt="derivedcolumns" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.03.36%20AM.png" />

