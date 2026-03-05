# Deleting User

Remove element by calling **Delete()** (**DeleteAsync()**) the object class **StiUser** or by calling one of the methods **DeleteByKey()**, **DeleteByKeyAsync()**, **DeleteByName()**, **DeleteByNameAsync()** from collection **StiServerConnection****.Accounts.****Users**:


**.NET API**

```
...
public void DeleteItem()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var user = connection.Accounts.Users.GetByKey("UserKey");
    if (user != null)
    {
        user.Delete();
    }

    connection.Accounts.Users.Logout();
}
...
```

Asynchronous example:


**.NET API**

```
...
public async void DeleteItemAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    await connection.Accounts.Users.DeleteByNameAsync("JohnSmith@example.com");

    await connection.Accounts.Users.LogoutAsync();
}
...
```
