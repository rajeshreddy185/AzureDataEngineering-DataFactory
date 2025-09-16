## **EXISTS FIELD**

The Exists field is a boolean property in the Get Metadata activity in Azure Data Factory. 
- When you select exists field, the activity's sole purpose is to check if a specified file 
  or folder exists at the location defined by the dataset.
- Based on the file exists or not it will return true else false.

Here is how to configure a dataset with the filename.

https://github.com/rajeshreddy185/AzureDataEngineering-DataFactory/blob/main/4-copy-activity/1-copy-activity-static-source-static-sink/README.md#:~:text=Configure%20the%20Source,your%20source%20file.

Now configure the Get Metadata activity with the exists field to see the file exists or not.

<img width="900" alt="existsfield" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-16%20at%2010.25.44%20PM.png" />

Finally output of exists field looks like below:

<img width="900" alt="existsfield" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-16%20at%2010.26.08%20PM.png" />
