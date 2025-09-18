## **UNTIL ACTIVITY**

The Until activity in Azure Data Factory (ADF) is a control flow activity that repeatedly executes a block of activities 
until a specified condition becomes true.


How It Works
Activities: You place one or more activities like a Copy activity inside the Until activity. These are the activities 
            that will be executed in each loop.

Condition: You define a boolean expression that must evaluate to true to stop the loop. This condition is typically 
            based on the output of an activity inside the loop. The loop will continue to run as long as this expression 
            is false.

Common Use Cases

Waiting for a File: You could use an Until activity to wait for a file to arrive in a storage account. You'd place a 
                    Get Metadata activity inside the loop to check if the file exists. The Until condition would 
                    be `@activity('GetMetadataActivity').output.exists` as true.
                    

<img width="900" alt="until" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-18%20at%2011.19.35%20PM.png" />
