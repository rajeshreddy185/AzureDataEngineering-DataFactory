# **COPY ACTIVITY STATIC SOURCE DYNAMIC SINK**

Static Source 
how to create a static source in below link 
https://github.com/rajeshreddy185/AzureDataEngineering-DataFactory/blob/main/4-copy-activity/README.md#:~:text=Step%2Dby%2DStep,your%20source%20file.


Dynamic Sink
- To create a dynamic sink, follow these steps:
  1. Create a dataset for the outbound folder with an empty filename.
  2. In the copy activity, use the sink dataset.
  3. When you run the copy activity, it will automatically take the input file name as the filename to create in the outbound folder.

