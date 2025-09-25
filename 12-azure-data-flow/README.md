# CSV TO CSV

**Adding a Select transformation to a simple CSV-to-CSV data flow:**

- Adding a Select transformation to a simple CSV-to-CSV data flow allows you to choose, rename, or reorder columns before 
  the data is written to the sink. This is a crucial step for controlling the output schema without affecting the source data.

- The Process with a Select Transformation
- Create Data Flow: Start by creating a new data flow in Azure Data Factory.
- Add a Source: Drag a Source transformation onto the canvas. Configure it to read data from your input CSV file. 
                The data flow automatically infers the columns from this source.
- Add a Select Transformation: Drag a Select transformation and connect its input stream to the output of the Source 
                              transformation. The Select transformation appears between the Source and the Sink.
- Configure the Select: In the Select settings, you will see all the columns from your source. Here, you can:
- Add a Sink: Drag a Sink transformation and connect its input to the output of the Select transformation. 
               Configure this sink to write the data to your destination CSV file.
- Run the Pipeline: Put the data flow into a pipeline and execute it.

<img width="900" alt="dataflowactivity" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%208.19.00%20AM.png" />


## How to Execute:

- You don't execute a data flow directly. Instead, a data flow is executed as an activity within an Azure Data Factory pipeline.

**Here's the general process for execution:**

Create a Data Flow: In the Azure Data Factory studio, you design your data flow with its sources, transformations, and sinks. 
                    You can test and debug the data flow interactively using the debug mode, which uses a live Spark cluster.

Create a Pipeline: In the same ADF studio, you create a new pipeline. A pipeline is a logical grouping of activities 
                   that you want to run together.

Add a Data Flow Activity: Drag the Data Flow activity from the Activities pane onto the pipeline canvas. 
                          This activity is the step that will run your data flow.

Configure the Activity: In the settings for the Data Flow activity, you select the data flow you designed in step 1 
                         and specify the integration runtime to be used for the execution.

<img width="900" alt="dataflowactivity1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-25%20at%208.19.16%20AM.png" />


**Schedule**

Manual Trigger: You can manually trigger the pipeline for an immediate, one-time run.

Scheduled Trigger: You can create a trigger that runs the pipeline on a predefined schedule 
                   (e.g., every day at 8:00 AM) or based on an event (e.g., when a new file is added to a storage account).


