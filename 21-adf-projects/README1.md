# **WAIT FOR A FILE TO ARRIVE IN AZURE DATA FACTORY**


This is a common scenario where you want to wait for a file to arrive in Azure Data Factory, you use an Until activity 
that polls for the file's existence. 
Inside the loop, a Get Metadata activity checks for the file if it does not exist it will got to wait activity and wait 
for given number of seconds and continue to loop. Once the file is found, a Set Variable activity changes a 
control variable to true, causing the loop to exit and allowing a Copy activity to run.


1. Initialize a Control Variable

- First, you need a variable to control the loop.
- In your pipeline, go to the Variables tab.
- Click + New to create a new variable.
- Name it something like `FileFound`, and set its type to **Boolean** and its default value to **false**.

2. Set Up the Polling Loop (Until Activity)

- The Until activity is the core of this workflow. It will contain all the steps that need to be repeated until the condition is met.
- Drag an Until activity onto your pipeline canvas.
- In the Settings tab of the Until activity, set the Expression to check if the FileFound variable is true: @equals(variables('FileFound'), true).
- You can also configure a Timeout and Wait time here to control how long the loop runs and how often it checks.

3. Check for the File (Get Metadata Activity)

- This step goes inside the Until activity and checks if the file has arrived.
- Inside the Until activity, drag a Get Metadata activity.
- Configure the Get Metadata activity to point to the file you are waiting for.
- In the Field List settings, select only the **Exists** field. The output of this activity will be `true` or `false`.

4. Conditionally Process or Wait (If Condition)
- Based on the output of the Get Metadata activity, the pipeline will either proceed with the copy or wait.
- Place an If Condition activity immediately after the Get Metadata activity (inside the Until loop).
- Set the Expression for the If Condition to be the output of the Get Metadata activity: @activity('Get Metadata').output.exists.
- The If Condition will have two branches:
  - "True" Branch (File Exists):
    - Inside the "True" branch, place your Copy activity to move the file.
    - After the Copy activity, add a Set Variable activity.
    - Set the FileFound variable to true. This will cause the Until loop to exit on the next check.
  - "False" Branch (File Not Found):
    - Inside the "False" branch, add a Wait activity.
    - Set the Wait time in seconds to 30 (or your desired polling interval).
    - This pauses the pipeline for a short period before the Until loop's next iteration.


<img width="900" alt="wait" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%208.35.38%20PM.png" />

<img width="900" alt="wait" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-23%20at%208.34.51%20PM.png" />