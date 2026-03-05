# Getting Role Info

In order to obtain information about the role, use the methods **GetByKey()** or **GetByKeyAsync()** that return an object **StiRole**. However, a more convenient way, without requiring the key is the use of one of the objects **StiServerConnection****.Accounts.****Roles.AdministratorRole**, **StiServerConnection****.Accounts.****Roles.ManagerRole**, **StiServerConnection****.Accounts.****Roles.UserRole**. Before calling this methods you must log in as a user whose rights are allowed to have access to the necessary information.


**.NET API**

```
...
public void GetRoleInfo()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var userRole = connection.Accounts.Roles.GetByKey("RoleKey");
    var roleDescription = userRole.Description;

    var currentRole = connection.Accounts.Roles.Current;
    var currentRoleName = currentRole.Name;

    connection.Accounts.Users.Logout();
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void GetRoleInfoAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var managerRole = connection.Accounts.Roles.ManagerRole;
    var managerCreatedDate = managerRole.Created;
    var managerPermissions = managerRole.Permissions;

    var currentRole = connection.Accounts.Roles.Current;
    var currentRoleName = currentRole.Name;

    await connection.Accounts.Users.LogoutAsync();
}
...
```
