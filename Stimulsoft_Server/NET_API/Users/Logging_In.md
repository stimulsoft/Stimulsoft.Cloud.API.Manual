# Logging In

Log in registered user the class method **Login()** (**LoginAsync()**):


**.NET API**

```
...
public void LogIn()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
} 
...
```

Or asynchronous method:


**.NET API**

```
...
public async void LogInAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
}
...
```
