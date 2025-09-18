## **FILTER ACTIVITY**

The Filter activity in Azure Data Factory (ADF) is a control flow activity that filters a collection of items based on 
a specified condition. 

How it works:

Input: The Filter activity takes an array as its input. This array is typically the output of a previous activity, 
        such as the childItems array from a Get Metadata activity.

Condition: You define a condition or an expression that is applied to each item in the input array.

Output: The activity produces a new array containing only the items that meet the specified condition.

Use case:
You can use a Get Metadata activity to get a list of all files in a directory, then use a Filter activity to
narrow down that list to only include files that meet a certain naming convention (e.g., endsWith('.csv')).

