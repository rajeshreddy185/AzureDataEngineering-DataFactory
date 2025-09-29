# **Assert**


The Assert transformation in Azure Data Flow is a debugging and validation tool used to define custom data quality rules
and check if rows meet specific conditions. Unlike other transformations that modify or filter data, Assert is purely 
for testing and verification. 

How to Use the Assert Transformation
Add the Transformation: Add an Assert transformation to your data flow. It's often placed before a sink to validate data 
just before it's loaded.

Define Assertions: In the Assertions tab of the transformation, you define your rules. Each assertion has three components:

Assertion ID: A unique name for the rule (e.g., Check_OrderID_NotNull).

Type: You can choose between two types:

Is true: The most common type. The assertion fails if the condition is false.

Is false: The assertion fails if the condition is true.

Expression: A logical expression that defines your validation rule.

Example:

Here is an example of an assertion that checks if the row ID is unique:

Select Expect_unique from drop down of `assert type`
Select ID from drop down of `Expression` column 

Click on `Add` button to add the assertion.

Click on `OK` to save the assertion.

<img width="900" alt="assert1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-29%20at%208.59.16%20AM.png" />

<img width="900" alt="assert2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-29%20at%208.59.26%20AM.png" />



