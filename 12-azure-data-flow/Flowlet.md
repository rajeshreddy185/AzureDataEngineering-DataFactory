# **FLOWLET**

A Flowlet is a reusable component of an Azure Data Flow that encapsulates a set of transformations. It allows you to 
modularize your data transformation logic, similar to how a function or subroutine works in programming.

Key Characteristics and Use Cases 
Reusability: The primary purpose of a Flowlet is to enable reuse. Once you design a Flowlet for a common task 
(e.g., data cleansing, address standardization, or currency conversion), you can use it across multiple data flows 
without rebuilding the logic each time.

Maintainability: By centralizing common logic in a Flowlet, you make your data pipelines easier to maintain. If you need
to change the logic of a transformation, you only have to update the Flowlet, and the change will automatically apply 
to all data flows that use it.

Encapsulation: Flowlets hide the complexity of the underlying transformations. A user of a Flowlet only needs to know 
its inputs and outputs, not the detailed steps inside.

Parameters: You can parameterize a Flowlet to make it flexible. For example, a data cleansing Flowlet could accept a
column name as a parameter, allowing it to be used on different columns in different data flows.

How to Create and Use a Flowlet
Create a Flowlet: In the Azure Data Factory studio, you create a new Flowlet and add your desired transformations. 
A Flowlet can have one or more inputs and outputs.

Save the Flowlet: Once complete, you save the Flowlet to your data factory.

Use in a Data Flow: When building a new data flow, you can drag and drop a Flowlet from the list of activities.
The Flowlet will appear as a single, encapsulated step on your canvas.

Connect and Configure: Connect your data stream to the Flowlet's input and configure any parameters. 
The output of the Flowlet can then be connected to subsequent transformations or a sink.