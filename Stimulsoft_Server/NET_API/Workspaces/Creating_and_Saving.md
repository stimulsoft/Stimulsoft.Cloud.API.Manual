# Creating and Saving

To create a new workspace, you need to log in with a user name that has permission to work with workspace, and create an object of the type **StiWorkspace**, and then call its method **StiWorkspace.Save()** (**StiWorkspace.SaveAsync()**):


**.NET API**

```
...
public void CreateNewWorkspace()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    var workspace = connection.Accounts.Workspaces.New("Company");
    var workspaceKey = workspace.Key;
    workspace.Save();
    
    connection.Accounts.Users.Logout();
}
...
```

An asynchronous example:


**.NET API**

```
...
public async void CreateNewWorkspaceAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    var workspace = connection.Accounts.Workspaces.New("Company");
    var workspaceKey = workspace.Key;
    await workspace.SaveAsync();
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
