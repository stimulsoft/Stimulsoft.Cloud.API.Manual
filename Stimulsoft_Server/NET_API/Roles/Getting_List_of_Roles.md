# Getting List of Roles

To find or process information about roles of the system, there is a method that allows you to get a list of all objects **StiRole**, to which the current user can access. Use the method **FetchAll()** (**FetchAllAsync()**).


**.NET API**

```
...
public void ProcessUsersInfo()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    var roles = connection.Accounts.Roles.FetchAll();

    //find role with full access to system monitoring
    var monitoringAdministrator = roles.First(a => a.Permissions.SystemMonitoring == StiPermissions.All);

    connection.Accounts.Users.Logout();
}
...
```

Asynchronous example:


**.NET API**

```
...
public async void ProcessUsersInfoAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var roles = await connection.Accounts.Roles.FetchAllAsync();

    //is exist role with name "ReportAdministrator"
    var isReportAdministrator = roles.Any(a => a.Name == "ReportAdministrator");

    await connection.Accounts.Users.LogoutAsync();
}
...
```
