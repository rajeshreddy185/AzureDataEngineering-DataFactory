## **FOR LOOP ACTIVITY**


The ForEach activity in Azure Data Factory (ADF) is a control flow activity that allows you to iterate over a 
collection of items and execute a specified set of activities for each item in the collection. 
It is the equivalent of a for loop in programming.


How It Works:

- Input: The ForEach activity takes an array as its input. This array is typically the output from a previous activity, 
         such as the childItems array from a Get Metadata activity or the results of a database query.

- Iteration: For each element in the input array, the ForEach activity executes all the activities placed inside it.

- Dynamic Content: Within the loop, you can use the expression @item() to reference the current item in the iteration. 
                   This is how you make the activities inside the loop dynamic.