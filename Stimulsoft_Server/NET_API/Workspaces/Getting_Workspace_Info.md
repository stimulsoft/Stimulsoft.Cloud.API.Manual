# Getting Workspace Info

In order to obtain information about the workspace, use the methods **GetByKey()** or **GetByKeyAsync()** that return the **StiWorkspace** object. Before calling these methods you must log in as a user whose rights are allowed to have access to the necessary information.


**.NET API**

```
...
public void GetWorkspaceInfo()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    var workspace = connection.Accounts.Workspaces.GetByKey("WorkspaceKey");
    var workspaceCompany = workspace.Company;
    
    var currentWorkspace = connection.Accounts.Workspaces.Current;
    var currentWorkspaceKey = currentWorkspace.Key;
    
    connection.Accounts.Users.Logout();
}
...
```

An asynchronous method:


**.NET API**

```
...
public async void GetWorkspaceInfoAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    var workspace = connection.Accounts.Workspaces.GetByKey("WorkspaceKey");
    var workspaceCompany = workspace.Company;
    
    var currentWorkspace = connection.Accounts.Workspaces.Current;
    var currentWorkspaceKey = currentWorkspace.Key;
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
