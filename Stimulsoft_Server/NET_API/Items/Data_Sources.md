# Data Sources

For working with data sources, Stimulsoft Server has a special type of a **StiItem** – **StiDataSourceItem**, which has some specific features and capabilities. **StiDataSourceItem** is an element that provides a connection to a database and retrieves the necessary data for displaying in the report. There are several methods to connect a specific database:

  * **SetFirebird** – connects to an existing DataSource adapter Firebird SQL;

  * **SetMsSQL** – connects to an existing DataSource adapter MS SQL Server;

  * **SetMySQL** – connects to an existing DataSource adapter MySQL Server;

  * **SetODBC** – connects to an existing DataSource adapter Open Database Connectivity (ODBC);

  * **SetOracle** – connects to an existing DataSource adapter Oracle Database;

  * **SetPostgreSQL** – connects to an existing DataSource adapter Postgre SQL;

  * **SetSQLCE** – connects to an existing DataSource adapter Microsoft SQL Server Compact;

  * **SetSQLite** – connects to an existing DataSource adapter SQLite DB;


As an argument to any of these methods, you must specify the connection string in the format supported by the specified database. There is the **StiDataQueryItem** class for receiving data set from a database. It describes the SQL query for the selected database. Creating an instance of this class can be done by using the **StiDataSourceItem.NewQuery** method. It allows you to create an SQL query to retrieve a dataset from the database. The parameters of this method are the name of the query and the text of the query in a format supported by the selected database.


**StiDataQueryItem.Run** or **StiDataQueryItem.RunAsync** methods is used to run the SQL query. As optional parameters restrictions on the size of the final sample are used: index of the first element and the number of elements of the dataset to be retrieved. The execution method is an instance of the system DataTable class with a set of requested data.


This example shows how to create a data source and run a query to obtain the number of records in a table «Items»:


**.NET API**

```
...
public void RunDataSourceQueryCount()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    const string connectionString = "Server=localhost;Database=testbase;Uid=root;Pwd=123;Connection Timeout=30;";
    var dataSource = connection.Items.Root.NewDataSource("test");
    dataSource.SetMySQL(connectionString);
    dataSource.Save();
    
    var dataQueryCount = dataSource.NewQuery("test query", "select count(*) from items").Save();
    var tableCount = dataQueryCount.Run();
    var count = (long)tableCount.Rows[0].ItemArray[0];
}
...
```

This asynchronous method creates a DataSource and runs a query to retrieve the first 500 elements of the table «Items»:


**.NET API**

```
...
public async void RunDataSourceQuerySelectAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    const string connectionString = "Server=localhost;Database=testbase;Uid=root;Pwd=123;Connection Timeout=30;";
    var dataSource = connection.Items.Root.NewDataSource("test").SetMySQL(connectionString).Save();
    
    var dataQuery = dataSource.NewQuery("test query", "select * from items").Save();
    var tableBeforeResult = await dataQuery.RunAsync(0, 500);
}
...
```
