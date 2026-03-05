# Deleting Role

Remove the role by calling **DeleteByKey()** (**DeleteByKeyAsync()**). Second way is creating an object of the type **StiRole**, and then calling its method **StiRole.Delete()** (**StiRole.DeleteAsync()**):


**.NET API**

```
...
public void DeleteRole()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    connection.Accounts.Roles.DeleteByKey("RoleKey");

    connection.Accounts.Users.Logout();
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void DeleteRoleAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var managerRole = connection.Accounts.Roles.ManagerRole;

    await managerRole.DeleteAsync();

    await connection.Accounts.Users.LogoutAsync();
}
...
```
