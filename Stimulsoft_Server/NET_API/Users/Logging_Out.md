# Logging Out

After all actions the user must log out. To do this, you can use the class methods **Logout()** or **LogoutAsync()**.


**.NET API**

```
...
public void Logout()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    connection.Accounts.Users.Logout();
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void LogoutAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    await connection.Accounts.Users.LogoutAsync();
}
...
```
