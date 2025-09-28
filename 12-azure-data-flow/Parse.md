# **PARSE**

Parsing in an Azure Data Flow is the process of extracting specific data from complex data types like nested arrays, 
structs, or maps and converting it into a flat, usable format. You use different transformations to achieve this based 
on the data structure.

Parsing Skills from an Array
To parse a nested array like skills in an Azure Data Flow, you use the Parse transformation. This is a crucial step 
to convert the array elements into individual rows that can be processed and analyzed.


Configure Parse:

Using parse select source, select array, select delimiter, select output columns and click on ok.
add it in expression ```(skill1 as string,skill2 as string,skill3 as string) ```

Result: The output will be a new row for each skill, duplicating the data from the parent record.

Before: "name": "Alice", "skills": "Azure|SQL|Python"] 

After:

"skills1": "Azure" , "skills2": "SQL" , "skills3": "SQL" 

Parsing City and Country from a Dictionary
To parse data from a dictionary (or a map in Data Flow terminology) and get the city and country,
you use the Derived Column transformation.

Add a Source Transformation: Read your data, which contains a address dictionary with city and country keys.

Add a Derived Column Transformation: Add a Derived Column transformation after your source.

Define New Columns: Create a new derived column for each piece of data you want to extract.

add it in expression ```(city as string,country as string) ```

Result: The output will be two new columns, city and country, populated with the values extracted from the location dictionary.


<img width="900" alt="parse1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.36.58%20PM.png" />

<img width="900" alt="parse2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.37.06%20PM.png" />

<img width="900" alt="parse3" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.18.08%20PM.png" />

<img width="900" alt="parse4" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.18.24%20PM.png" />

<img width="900" alt="parse5" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.34.06%20PM.png" />

<img width="900" alt="parse6" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.33.55%20PM.png" />