# **JOIN**

Joining is a fundamental transformation in Azure Data Flow that combines data from two or more data streams into a 
single stream. It's used to merge rows from different sources based on matching values in a common column, much like a
SQL JOIN clause.


How to Use a Join Transformation
Add a Join Transformation: Drag and drop a Join transformation onto your data flow canvas. It will have two input streams.

Define Join Streams: Connect two different data streams (e.g., from two separate sources or other transformations) to 
the input of the Join transformation.

Configure Join Type: In the join settings, select the Join Type from the dropdown menu (e.g., Inner, Left, Right, etc.).

Set Join Conditions: Define the join condition(s). This is where you select the columns from each stream that you want to match.

<img width="900" alt="join1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%208.35.20%20PM.png" />