## **IF ACTIVITY**


The If Condition activity in Azure Data Factory (ADF) is a control flow activity that allows you to execute different 
sets of activities based on whether a given expression evaluates to true or false

How It Works
Expression: You provide a boolean expression that the activity evaluates. This expression can be based on the output of previous activities, pipeline parameters, or system variables.

Branches: The If Condition activity has two branches:

True branch: A container for activities that will be executed if the expression is true.

False branch: A container for activities that will be executed if the expression is false.

Common Use Case
A typical scenario is to check for the existence of a file before attempting to copy it. This prevents the pipeline from failing if the file isn't present.

Step 1: Use a Get Metadata activity to check if a file exists. The output of this activity will have a property called exists.

Step 2: Use an If Condition activity immediately after the Get Metadata activity.

Step 3: In the If Condition's Expression field, you'd use the dynamic content: @activity('Get Metadata').output.exists.

Step 4:

In the True branch, you'd place a Copy activity to copy the file.

In the False branch, you might add a Set Variable activity to log a message, or simply do nothing.


