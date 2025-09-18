## ** FLATTEN VS PRESERVE **


Flattening and preserving hierarchy are two common options for handling nested data structures when a copy activity 
is used in Azure Data Factory (ADF). These options determine how the folder structure of your source data is replicated 
at the destination.


1) Flatten: This option copies all files from a source folder and its subfolders directly into a single destination 
   folder. The original folder structure is not maintained. 
2) Preserve: This option replicates the entire folder structure of the source at the destination. The copy activity 
   maintains the relative path from the source folder to each file.
3) Merge: This is the simplest form of merging. It involves combining multiple files with the same schema from a source 
   location into a single file at the destination.

