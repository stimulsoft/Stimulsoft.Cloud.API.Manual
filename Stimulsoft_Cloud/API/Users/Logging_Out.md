# Logging Out

After all actions the user must log out. To do this, you can use the class methods **Logout()** or **LogoutAsync()**.


**.NET API**

```
...
public void Logout()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    connection.Accounts.Users.Login();
    
    //Enter your code
    
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
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
    
    //Enter your code
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
