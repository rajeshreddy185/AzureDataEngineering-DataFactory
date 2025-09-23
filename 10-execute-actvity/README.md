## **EXECUTE ACTIVITY**

The Execute Pipeline activity (often simply called the "Execute activity") in Azure Data Factory (ADF) is used to run 
another pipeline from within the current pipeline. This allows you to create nested pipelines or parent-child workflows, 
which is a fundamental concept for building modular and reusable data solutions.

How It Works
-------------
**Parent Pipeline**: This is the main pipeline that contains the Execute Pipeline activity.

**Child Pipeline**: This is the pipeline that will be called and executed by the parent. 
                    The child pipeline can contain its own activities, datasets, and parameters.

**Parameters**: You can pass parameters from the parent pipeline to the child pipeline. This makes the child pipeline 
                highly reusable, as it can be configured differently for each execution. 
                For example, a child pipeline that copies a file could accept the source and sink paths as parameters.

Common Use Cases
- Modularity: By breaking down a complex workflow into smaller, single-purpose child pipelines 
    (e.g., one for data ingestion, one for transformation), you make the solution easier to manage, debug, and maintain.

- Reusability: You can create a generic child pipeline that performs a common task, like copying a file or running a stored 
    procedure, and reuse it across multiple parent pipelines simply by passing in different parameters.

- Dynamic Workflows: The Execute Pipeline activity is often used inside a ForEach activity to dynamically call a 
    child pipeline for each item in a list (e.g., process each file in a folder by calling a child pipeline for every file).



<img width="900" alt="parrentpipeline" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.53.14%20PM.png" />

<img width="900" alt="childpipeline" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.52.54%20PM.png" />

<img width="900" alt="executeactivity" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.52.45%20PM.png" />


Pipeline Variables
- Scope: Pipeline variables are defined at the pipeline level and are local to a single pipeline run. 
         They can be accessed and modified by any activity within that specific pipeline.

- Mutability: These variables are mutable, meaning their values can be changed during the pipeline run using a 
              Set Variable activity or Append Variable activity.

- Use Case: Pipeline variables are perfect for storing and manipulating intermediate results, 
          like a counter in a ForEach loop or a timestamp for an incremental load. You define them on the pipeline 
          canvas and reference them using @variables('MyVariableName').

<img width="900" alt="pipelineparams" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%209.53.01%20PM.png" />


Global Parameters
- Scope: Global parameters are defined at the data factory level and are available across all pipelines within that data 
       factory. They are a way to manage constants that are used by multiple pipelines.

- Mutability: They are immutable, meaning their values cannot be changed during a pipeline run.  
              They are set once and are often used to define environment-specific values like a database connection 
              string or a storage account URL.

- Use Case: Global parameters are ideal for handling configuration values that are consistent across your data factory 
          but may change between environments (e.g., development, testing, and production). You reference them using 
          @pipeline().globalParameters.MyGlobalParameterName.

NOTE: to set a global parameter, you need to go to the data factory and click on manage in side bar and 
        then global parameters tab add and save.

<img width="900" alt="globalparams" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%2010.01.16%20PM.png" />
