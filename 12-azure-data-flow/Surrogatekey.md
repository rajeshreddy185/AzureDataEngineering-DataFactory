# **SURROGATE KEY**

A Surrogate Key in Azure Data Flow is a transformation that generates a unique, sequential integer key for each row of 
data. It's used to create a primary key for a table when the source data doesn't have a suitable natural key.


Key Features and Configuration
Start Value: You can set the starting value of the key. By default, it's 1, but you can change it to any integer. 
This is useful for continuing a key sequence from a previous load.

Increment Value: The key increments by 1 for each row by default. This value can also be configured.

Output Column Name: You must provide a name for the new surrogate key column, such as sk_product_id or EmployeeKey.

<img width="900" alt="surrogate1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2011.10.36%20PM.png" />