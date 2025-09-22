## **COPY ACTIVITY CSV SOURCE SQL SINK **

Here is the example of the copy activity of files from csv to sql database:

1. Create a dataset for the source folder with an filename which contains data.
2. Create a dataset for the sink which connects to the sql database for a particular table.
3. Table needs to be created in sql database previously based on the data expecting from csv file.
4. Add a copy activity to your data pipeline.
5. Go to the Source tab of the Copy Activity and select your source dataset.
6. Go to the Sink tab and select your sink dataset.
7. Run the pipeline. The Copy Activity will read data from the specified source folder and write it to the table sink. 

<img width="900" alt="csvsrc" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.00.04%20PM.png" />

<img width="900" alt="sqlsinksrc" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.00.13%20PM.png" />

**Faced issue**

ERROR1 
----------

Operation on target Copydata failed: ErrorCode=TypeConversionFailure,Exception occurred when converting value 
'16/06/2020' for column name 'ship_date' from type 'String' (precision:, scale:) to type 'DateTime' 
(precision:, scale:). Additional info: String was not recognized as a valid DateTime  


ROOT CAUSE
----------
When CSV contains dates in UK format (dd/MM/yyyy, e.g. 22/09/2025),
ADF by default assumes US format (MM/dd/yyyy).

This causes problems:

03/09/2025 may be wrongly interpreted as March 9th instead of 9th September.

Some values may fail completely with conversion errors if the day exceeds 12.

Example error in pipeline run:

ErrorCode=TypeConversionFailure,
'Type=String, Value=31/12/2025, TargetType=DateTime'


Root cause → no locale or date format specified in Copy Activity.

RESOLUTION
----------

You need to explicitly tell ADF how to parse the date column by setting:

Date format → "dd/MM/yyyy"

Locale → "en-GB"

 "culture": "en-GB",
 "format": "dd/MM/yyyy"

"typeConversion": true,
"typeConversionSettings": {
    "allowDataTruncation": true,
    "treatBooleanAsNumber": false,
    "dateFormat": "dd/MM/yyyy",
    "culture": "en-GB"
}
}

<img width="900" alt="typeConversion" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.12.20%20PM.png" />

ERROR2
---------

Operation on target Copydata failed: ErrorCode=DelimitedTextMoreColumnsThanDefined,
'Type=Microsoft.DataTransfer.Common.Shared.HybridDeliveryException,Message=Error found when processing
'Csv/Tsv Format Text' source 'Superstore_orders.csv' with row number 34: found more columns than expected 
column count 21.,Source=Microsoft.DataTransfer.Common,'

<img width="900" alt="processingerror" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.12.28%20PM.png" />


ROOT CAUSE
-----------

This usually happens when:
The CSV has commas inside quotes ("Product Name, Extra Text"), which ADF mistakenly treats as column separators.
The file actually has an extra column in some rows.
Inconsistent data entry → missing/extra delimiters.

2,CA-2020-152156,08/11/2020,...,"Hon Deluxe Fabric Upholstered Stacking Chairs, Rounded Back",731.94,...
Here, the product name contains a comma inside quotes.
If the dataset is not configured with quoteChar, ADF will treat this as two columns instead of one.
Fix: In your CSV dataset settings, set:
"quoteChar": "\""
validate CSV schema consistency, or use fault tolerance to skip bad rows.

FINALLY DATA COPY FROM CSV TO SQL DATABASE COMPLETED:
--
<img width="900" alt="srcpreview" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.03.14%20PM.png"/>

<img width="900" alt="sinkpreview" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.03.14%20PM.png" />

<img width="900" alt="mapping" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%208.02.45%20PM.png" />

<img width="900" alt="output" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-22%20at%209.02.42%20PM.png" />

