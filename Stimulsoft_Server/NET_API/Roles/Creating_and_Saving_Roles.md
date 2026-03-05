# Creating and Saving Roles

To create a new role, you need to log in with a user name that has permission to work with roles, and create an object of the type **StiRole**, and then call its method **StiRole.Save()** (**StiRole.SaveAsync()**):


**.NET API**

```
...
public void CreateNewRole()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var role = connection.Accounts.Roles.New("UserRole");
    role.Permissions = connection.Accounts.Roles.ManagerRole.Permissions;
    role.Permissions.SystemMonitoring = StiPermissions.RunView;
    role.Save();

    connection.Accounts.Users.Logout();
}
...
```

Asynchronous example:


**.NET API**

```
...
public async void CreateNewRoleAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var role = connection.Accounts.Roles.New("CustomRole");
    role.Permissions.SystemUpdate = StiPermissions.All;
    role.Permissions.ItemSchedulers = StiPermissions.CreateDeleteModifyView;
    await role.SaveAsync();

    await connection.Accounts.Users.LogoutAsync();
}
...
```
