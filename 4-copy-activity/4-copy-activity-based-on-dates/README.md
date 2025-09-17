## **COPY ACTIVITY BASED ON DATES**

Here is the example of the copy activity of files from 
source folder to sink folder based on the date present in the filename:


1. Create a dataset for the source folder with an empty filename.
2. Click on filename placeholder, Add dynamic content will appear.
3. Click on it opens up an window with parameters and function.
4. Add a parameter with the filename (for example name can be anything) var.
5. Lets consider order_20250917.csv as filename then use the below expression 
   `@concat('order_', formatDateTime(utcNow(), 'ddMMyyyy'), '.csv')` to get filename.
   
<img width="900" alt="filenamewithdate" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-17%20at%209.41.07%20PM.png" />
