# Conditional Split

The Conditional Split transformation in an Azure Data Flow is a powerful tool for routing data rows into different streams
based on logical conditions. It functions like a CASE statement or if-then-else structure in programming, allowing you 
to process different subsets of your data in parallel or send them to different destinations.

If a row doesn't meet any of the defined conditions, it can be routed to an optional default stream.

Here is an example:

Let's imagine you have sales data and you want to process orders based on their ship_mode. You can use a Conditional Split 
to separate them into three streams: one for First Class & Same Day, 
and a default stream for  Standard Class & Second Class.

Add the Transformation: In your data flow canvas, add a Conditional Split transformation after your data source.

Define Conditions: In the settings for the Conditional Split, you'll define your conditions using the Expression Builder. 
You'll give each output stream a name and a condition.

Output 1: First_Class_Same_Day_Orders

Condition: `ship_mode == 'First Class' || ship_mode == 'Same Day'`

This will capture all rows where the ship_mode is "First Class".

<img width="900" alt="conditionalsplit1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.41.00%20AM.png" />

Output 2: Standard_Second_Class_Orders

Condition: `ship_mode == 'Standard Class' || ship_mode == 'Second Class'` & everything else (if needed we can separate it with tird output)
This expression will evaluate to true for every row where the ship_mode column is exactly "Standard Class".


Default Stream: Any rows the above conditions will be routed to a default output. 
This is a crucial feature for handling unexpected data or for a "catch-all" category. 
For example, any rows with ship_mode of any of four would fall into this stream.

output:

<img width="900" alt="conditionalsplit2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.41.55%20AM.png" />

<img width="900" alt="conditionalsplit3" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%209.42.18%20AM.png" />
