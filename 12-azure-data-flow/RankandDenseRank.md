# **RANK**

Rank transformation in Azure Data Flow is used to generate a rank column for rows within a data stream. 
This is typically done to find the top N records or to assign a numerical order based on certain criteria. 
It's the equivalent of a RANK() window function in SQL.

Assigns a unique rank to each row, skipping ranks if there are ties. For example, if two rows tie for 1st place, the next rank would be 3.

<img width="900" alt="rank1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.10.59%20AM.png" />

<img width="900" alt="rank2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.23.50%20AM.png" />

# **DENSE RANK**

Dense Rank transformation in Azure Data Flow is used to generate a dense rank column for rows within a data stream. 
This is typically done to find the top N records or to assign a numerical order based on certain criteria without 
skipping the ranks for equal values. It's the equivalent of a DENSE_RANK() window function in SQL.

Assigns a unique rank without skipping numbers in case of ties. If two rows tie for 1st place, the next rank would be 2.


How It Works
The Rank transformation takes two key configurations: 
Group By: This is an optional setting that partitions the data into groups before ranking. 
          If you specify a group by column, the rank will reset to 1 for each new group. 
          For example, if you group by ProductCategory, the ranking will restart at 1 for each category.

Order By: This is the most important part. You must specify one or more columns to sort the data by, as the ranking 
          is based on this order. You can set the order to be either ascending or descending. For example,
          to find the top-selling products, you'd order by TotalSales in a descending order.


Add a Rank Transformation: Add a Rank transformation after your sales data stream.

Configure Group By: Set the Group By to ProductCategory. This will partition your data so that the ranking is performed
                    within each category separately.

Configure Order By: Set the Order By to Sales in Descending order. This ensures that the products with the highest 
                    sales receive the lowest rank numbers.


<img width="900" alt="rank3" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.25.10%20AM.png" />

<img width="900" alt="rank4" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.25.17%20AM.png" />

<img width="900" alt="rank5" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.25.33%20AM.png" />

<img width="900" alt="rank6" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/Screenshot%202025-09-28%20at%209.26.28%20AM.png" />



