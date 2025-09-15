
# **SQL SERVER LINKED SERVICE**


- Create a New Linked Service:
  - Under the "Connections" section, click on Linked services, then click the + New button.

- Select the Connector:
  - Search for and select the SQL Server connector from the list. Click Continue.

- Configure Connection Details:
  - A configuration blade will open. Fill in the following details:
    - Name: Give your linked service a meaningful name.
    - Connect via Integration Runtime: Select the Integration Runtime you've set up (Self-Hosted for on-premises, or the default AutoResolve for Azure).
    - Server Name: The name or network address of your SQL Server instance.
    - Database Name: The name of the specific database you want to connect to.
    - Authentication Type: Select your desired authentication method (SQL, Windows, or Managed Identity).
    - Credentials: Enter the username and password if you choose SQL Authentication.

- Test the Connection:
  - Click Test connection to verify that ADF can successfully connect to your database with the provided information. This step is crucial for troubleshooting any issues with credentials or network connectivity.

- Create the Linked Service:
  - Once the connection test is successful, click Create to save your new linked service.

<img width="900" alt="sqllspass" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.30.00%20PM.png" />

<img width="900" alt="sqllspass1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.29.39%20PM.png" />
