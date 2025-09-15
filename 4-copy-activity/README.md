# **COPY ACTIVITY**

- A copy activity is a core component in data integration services like Azure Data Factory (ADF).
- Its primary purpose is to:
  - Copy data from a source data store to a sink (destination) data store.

Step-by-Step Guide

1. Configure the Source Dataset
  - Open or Create the Source Dataset: In Azure Data Factory Studio, go to the Author tab and open your source ADLS Gen2 dataset.
  - Set the File Path: In the Connection tab of the dataset, provide the full file path.
  - File System: Select or enter the name of your container.
  - Folder path: Specify the folder path (e.g., devcontainer1/inbound).
  - File name: Type in the exact name of the source file (e.g., azurede_index.pdf).
  - Confirm: The combination of the file system, folder path, and file name defines the static location of your source file.

2. Configure the Sink Dataset
  - Open or Create the Sink Dataset: Create or open the ADLS Gen2 dataset for the sink. This dataset can use the same linked service as the source, or a different one.
  - Set the File Path: Similar to the source, specify the full static file path.
  - File System: Enter the container name (e.g., devcontainer1).
  - Folder path: Enter the destination folder (e.g., outbound).
  - File name: Enter the exact name you want the output file to have (e.g., azure_dataeng.pdf). This will overwrite the file if it already exists in the destination.

3. Configure the Copy Activity
  - Add a Copy Activity: In your data pipeline, drag a Copy data activity onto the canvas.
  - Set Source and Sink:
    - Go to the Source tab of the copy activity and select your static source dataset.

Here are the steps to configure the copy activity:

- Add a Copy Activity: In your data pipeline, drag a Copy data activity onto the canvas.

- Set Source and Sink:
  - Go to the Source tab of the copy activity and select your static source dataset.
  - Go to the Sink tab and select your static sink dataset.

- Run the Pipeline: When you run or debug the pipeline,
  - The copy activity will read data from the specified source file and write it to the specified sink file.