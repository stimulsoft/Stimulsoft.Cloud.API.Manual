# Deleting Workspace

To delete a workspace, you must have supervisor rights. A workspace in which the supervisor is registered cannot be deleted. Remove the workspace by calling **DeleteByKey()** (**DeleteByKeyAsync()**). Second way is creating an object of the **StiWorkspace** type, and then calling its method **StiWorkspace.Delete()** (**StiWorkspace.DeleteAsync()**):


**.NET API**

```
...
public void DeleteWorkspace()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
        
    connection.Accounts.Workspaces.DeleteByKey("WorkspaceKey");
    
    connection.Accounts.Users.Logout();
}
...
```

An asynchronous method:


**.NET API**

```
...
public async void DeleteWorkspaceAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    var workspace = connection.Accounts.Workspaces.GetByKeyAsync("WorkspaceKey");
    
    await workspace.Result.DeleteAsync();
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
