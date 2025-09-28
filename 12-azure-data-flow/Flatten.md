# **FLATTEN**

The Flatten transformation in Azure Data Flow is used to un-nest complex data types like arrays and structs into 
individual rows and columns. This is a crucial step when you're dealing with semi-structured data formats 
like JSON, Avro, or Parquet that contain nested arrays or objects. 


The Flatten transformation takes a single input stream and produces a single output stream. It works by:
Iterating through an Array: You specify the name of the array column you want to flatten.
Creating New Rows: For each element in the array, the transformation creates a new row.
Populating Columns: It then populates the new row with the data from that array element, 
                    along with the data from the parent row.


Example:

```commandline

[
{
"id":"101",
"name":"srinivas",
"gender":"male",
"languages":["English","Hindi"],
"address":{
            "city":"Hyderabad",
			"country":"india"
          } 
},
{
"id":"102",
"name":"phani",
"gender":"male",
"languages":["English","Hindi"],
"address":{
            "city":"Hyderabad",
			"country":"india"
          }
}
]

```

Expand dictionay:

<img width="900" alt="flatten1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%207.53.03%20PM.png" />

<img width="900" alt="flatten2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%207.54.48%20PM.png" />

<img width="900" alt="flatten3" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%207.57.45%20PM.png" />

<img width="900" alt="flatten4" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%207.54.53%20PM.png" />