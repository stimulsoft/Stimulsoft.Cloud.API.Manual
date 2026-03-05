# Creating New User

Creating new users goes through the creation of a new object **StiUser** and it is storing through the methods **Save()** or **SaveAsync()**:


**.NET API**

```
...
public void CreateNewUser()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var newUser = connection.Accounts.Users.New();
    newUser.UserName = "UserName@example.com";
    newUser.Password = "UserPassword";
    newUser.Save();
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void CreateNewUserAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var newUser = connection.Accounts.Users.New();
    newUser.UserName = "UserName@example.com";
    newUser.Password = "UserPassword";
    await newUser.SaveAsync();
}
...
```

In addition you can create a user through **Roles** using the method **NewUser()**:


**.NET API**

```
...
public void NewUserFromRole()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    var managerRole = connection.Accounts.Roles.ManagerRole;
    var newUser = managerRole.NewUser("NewUserName@example.com", "Password");
    
    connection.Accounts.Users.Logout();
}
...
```
