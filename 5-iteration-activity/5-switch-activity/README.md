## **SWITCH ACTIVITY**


The Switch activity in Azure Data Factory (ADF) is a control flow activity that provides a way to execute different 
activities based on a specific input value.

How It Works
Expression: You provide a single expression, often a pipeline parameter, an activity output, or a variable.

Cases: You define a number of "cases" or possible values for the expression. Each case corresponds to a container of activities.

Default Case: You can also define an optional "Default" case, which will be executed if the expression's value does 
              not match any of the defined cases.

Common Use Cases
The Switch activity is best for scenarios with multiple, distinct execution paths based on a single variable or value.

Conditional Processing: For example, you could have a pipeline parameter called DataSourceType like (csv, txt, orc)