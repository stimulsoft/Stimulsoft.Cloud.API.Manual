# Changing User Info

Passwords are stored in the system in the form of hashes and the **StiUser** object does not return hem. The method **ChangePassword()** (**ChangePasswordAsync()**)is used to change the password. Using parameters you must specify the current password and a new one:


**.NET API**

```
...
public void ChangeUserLastName()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    connection.Accounts.Users.Login();

    var userJohn = connection.Accounts.Users.GetByName("John@example.com");
    userJohn.LastName = "Smith";
    userJohn.Save();
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void ChangeUserLastNameAsync()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();

    var userJohn = await connection.Accounts.Users.GetByName("John@example.com");
    userJohn.LastName = "Smith";
    await userJohn.Save();
}
...
```
