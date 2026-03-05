# Getting User Info

In order to obtain information about the user, use the methods **GetByName()** or **GetByKey()** that return a **StiUser** object. This object contains full information about the user (key of user role, workspace and root folder, OAuth identifier and type of authorization method, first name, last name, user name (email), avatar image, some flags (enabled, activated) and time when this user was created, last modified and last logged). Before calling the method **GetByName()** or **GetByKey()** you must log in as a user whose rights are allowed to have access to the necessary information.


**.NET API**

```
...
public void GetUserInfo()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    connection.Accounts.Users.Login();

    var userJohn = connection.Accounts.Users.GetByName("John@example.com");
    var johnLastName = userJohn.LastName;
    var johnLogin = userJohn.LastLogin;

    var userScott = connection.Accounts.Users.GetByKey("ScottKey");
    var scottLastName = userScott.LastName;
    var scottLogin = userScott.LastLogin;
    
    var currentUser = connection.Accounts.Users.Current;
    var currentName = currentUser.UserName;
}
...
```

Or asynchronous method:


**.NET API**

```
...
public async void GetUserInfoAsync()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();

    var userJohn = await connection.Accounts.Users.GetByNameAsync("John@example.com");
    var johnLastName = userJohn.LastName;
    var johnLogin = userJohn.LastLogin;

    var userScott = await connection.Accounts.Users.GetByKeyAsync("ScottKey");
    var scottLastName = userScott.LastName;
    var scottLogin = userScott.LastLogin;
    
    var currentUser = connection.Accounts.Users.Current;
    var currentName = currentUser.UserName;
}
...
```
