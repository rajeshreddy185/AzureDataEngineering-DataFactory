# **Get Metadata Activity** 

- Extracts metadata from data stores
- Retrieves information about data without moving it

## Common Use Cases

### File Operations
- Get lists of files/folders in a directory
- Check if specific files or folders exist
- Retrieve file properties (size, dates)
- Identify and skip empty files

### Configuration
- Dataset: You must link the activity to a dataset that points to the data store you want to inspect.

- Field List:
  - This is mandatory part of the configuration.
  - You select which metadata properties you want to retrieve.
  - The options vary depending on the data store you are inspecting.

### Key Properties
- Child Items:
  - Returns a list of all files and folders in the specified path. 
  - This is crucial for iterating over multiple files.
- Exists:
  - Returns a boolean (true/false) indicating if the file or folder exists.
- Size:
  - Returns the size of the file in bytes.
- Item Name:
  - Returns the name of the file or folder.
- Last Modified:
  - Returns the last modified timestamp.

    
### Use Cases
- Validate data before processing
- Implement conditional logic based on metadata
- Trigger alerts for missing files
- Process only recently modified files


