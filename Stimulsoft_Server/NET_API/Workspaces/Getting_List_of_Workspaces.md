# Getting List of Workspaces

To find or process information about workspaces of the system, there is a method that allows you to get a list of all objects **StiWorkspace**, to which the current user can access. Use the method **FetchAll()** (**FetchAllAsync()**).


**.NET API**

```
...
public void ProcessWorkspacesInfo()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
        
    var workspace = connection.Accounts.Workspaces.FetchAll();
    
    //find workspace of the company with the name Northwind
    var northwindWorkspace = workspace.First(a => a.Company == "Northwind");
    
    connection.Accounts.Users.Logout();
}
...
```

An asynchronous example:


**.NET API**

```
...
public async void ProcessWorkspacesInfoAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    var workspace = connection.Accounts.Workspaces.FetchAll();
    
    //find workspaces created to 01.01.2015
    var newWorkspaces = workspace.First(a => a.Created <= new DateTime(2015, 01, 01));
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
