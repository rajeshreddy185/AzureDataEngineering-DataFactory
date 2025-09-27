# **SORT**

The Sort transformation is used to arrange rows in a data stream in a specific order. You can sort data in ascending or 
descending order based on one or more columns.

How to Use a Sort Transformation
Add a Sort Transformation: In your data flow, add a Sort transformation. Place it in the data stream where you want to perform the sorting.

Configure Sorting Columns: In the sort settings, you define the columns you want to sort by and the order for each.

Add Columns: Click on the input box to select the column you wish to sort.

Set Order: For each column, you specify the sort direction:

Ascending: Orders values from smallest to largest (e.g., A-Z, 1-100).

Descending: Orders values from largest to smallest (e.g., Z-A, 100-1).



How to Sort by Profit
Add a Sort Transformation: In your data flow canvas, add a Sort transformation. Connect it to the data stream containing your profit data.

Configure Sorting Column: In the settings for the Sort transformation, you specify the column to sort by.

Select profit from the list of available columns.

Set the Order: Choose the sort direction:

Descending: This is the most common choice for profit, as it places the highest profit orders at the top of the list.

Ascending: This would show the lowest profit or even loss-making orders at the top.


<img width="900" alt="sort1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2010.43.21%20PM.png" />



