# Changing User Password

Passwords are stored in the system in the form of hashes and object **StiUser** not return hem. To change the password used method **ChangePassword()** (**ChangePasswordAsync()**). The parameters you must specify the current password and new:


**.NET API**

```
...
public void ChangeUserPassword()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var userJohn = connection.Accounts.Users.GetByName("John@example.com");
    userJohn.ChangePassword("JohnPassword", "NewPassword");
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void ChangeUserPasswordAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var userJohn = await connection.Accounts.Users.GetByNameAsync("John@example.com");
    await userJohn.ChangePasswordAsync("JohnPassword", "NewPassword");
}
...
```
