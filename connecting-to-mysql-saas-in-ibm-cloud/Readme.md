# Using IBVM RPA Connect to MySQL (mysqlConnect) when connecting to IBM Cloud My Databases for MySQL.

For a given project I needed an IBM RPA script to connect to MySQL SaaS hosted in IBM Cloud (My Databases for MySQL).

## 1. Create the MySQL service

## 2. Download and Install the [MYSQL ODBC Driver](https://dev.mysql.com/downloads/connector/odbc/)

`TIP: download the ZIP/ TAR version, the msi will ask you to install Visual Studio first ... what is pretty annoying.`

To install the Zipped version: 
- just unzip it anywhere, 
- open `cmd` as Administrator, 
- go to the unzipped folder and 
- run the `Install.bat`.

` You must restart your system after the installation`

To ensure everything is ok:
- Open the ODBC Data Sources Desktop application (*),
- Click the Add button. The drivers "MySQL ODBC ..." should be listed among others. 
- Close the app, you don't need anything else to use ODBC for RPA. 

`(*) On the Start page, type ODBC Data Sources. `

## 3. Write the connection string and happy scripting ! **

Find the connection information in My Databases for SQL service instance in ** "Service Credentials" **, you will need:
* Host
* Port
* Databasename

The user name is ?????

IBM RPA [mysqlConnect documentation](https://www.ibm.com/docs/en/rpa/21.0?topic=connection-connect-mysql) gives us a clue about what connection string we are supposed to use. 
They provided a code sample containing ``` "server=localhost;User Id=root;database=NameDataBase; password=YourPassword" ```

`TIP: You must add a Port parameter, so the right string is`

```
"server=YOURSERVICEHOST;Port=YOURSERVICEPORT;User=YOURUSER;database=YOURDATABASENAME;password=YOURUSERPASSWORD"
```

`TIP: I was not so confident using just the sample so ... I googled around and found this`[AMAZING connectionstrings.com site](https://www.connectionstrings.com/mysql/) `(already in my bookmarks)`
