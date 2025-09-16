## To create a dynamic source and sink in the Copy Activity, follow these step-by-step instructions:

## Step 1: Configure the Source Dataset

1. create the Source Dataset.
2. Specify the folder path (e.g., `devcontainer1/inbound`).
3. Leave the File Name field empty.

<img width="900" alt="inbounddir" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-16%20at%209.45.01%20PM.png" />

## Step 2: Configure the Sink Dataset

1. create the Sink Dataset.
2. Specify the folder path (e.g., `devcontainer1/outbound`).
3. Leave the File Name field empty.

<img width="900" alt="outdboundir" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-16%20at%209.40.50%20PM.png" />

## Step 3: Configure the Copy Activity

1. Add a Copy Activity to your data pipeline.
2. Go to the Source tab of the Copy Activity and select your dynamic source dataset.
3. Go to the Sink tab and select your dynamic sink dataset.
4. Run the pipeline. The Copy Activity will read data from the specified source folder and write it to the specified sink folder dynamically at runtime. The output files will be created based on the input files in the source folder.

Remember to replace `devcontainer1` with your actual container name and provide the correct folder paths for both the source and sink datasets.

That's it! You have successfully created a dynamic source and sink in the Copy Activity.

<img width="900" alt="dynamicsourcesink" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-16%20at%2010.04.14%20PM.png" />
