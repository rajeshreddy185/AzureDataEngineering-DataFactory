# **EXISTS**

Exists transformation is a core feature in Azure Data Flow. It's used to check for the existence of rows in one stream 
based on the values in a second stream. This is different from a regular join because it doesn't merge the columns from 
the two streams; it simply checks for a match and returns a boolean value.

How it Works
The Exists transformation takes two input streams: a "left" stream and a "right" stream. You define a condition 
based on columns from both streams. The transformation then evaluates whether a row in the left stream has a 
corresponding row in the right stream that satisfies the condition.

The result is a boolean value for each row in the left stream:
true if a match is found in the right stream.
false if no match is found.

The Two Types of Exists
The Exists transformation can operate in two modes:

Exists (IN condition): This mode returns true for every row in the left stream that has a matching value in the right 
                       stream. It's equivalent to a SQL WHERE EXISTS or WHERE IN clause.

Use Case: Filtering a customer list to find only those who have placed an order.

Not Exists (NOT IN condition): This mode returns true for every row in the left stream that does not have a matching 
                            value in the right stream. It's equivalent to a SQL WHERE NOT EXISTS or WHERE NOT IN clause.

Use Case: Identifying customers who have never placed an order to target them for a marketing campaign.


<img width="900" alt="exists1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-27%20at%2010.23.25%20PM.png" />