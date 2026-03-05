# Getting List of Users

To find or process information about users of the system, there is a method that allows you to get a list of all objects **StiUser**, to which the current user can access. Use the method **FetchAll()** (**FetchAllAsync()**).


**.NET API**

```
...
public void ProcessUsersInfo()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    var users = connection.Accounts.Users.FetchAll();

    //find user with last name "Smith"
    var mrSmith = users.First(a => a.FirstName == "Smith");    
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void ProcessUsersInfoAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    var users = await connection.Accounts.Users.FetchAllAsync();

    //is exist user with name "John"
    var isJohnExists = users.Any(a => a.LastName == "John");
}
...
```
