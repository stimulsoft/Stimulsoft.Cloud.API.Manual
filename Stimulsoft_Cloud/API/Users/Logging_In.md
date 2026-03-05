# Logging In

Log in registered user the class method **Login()** (**LoginAsync()**):


**.NET API**

```
...
public void LogIn()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");connection.Accounts.Users.Login();
} 
...
```

Or asynchronous method:


**.NET API**

```
...
public async void LogInAsync()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
}
...
```
