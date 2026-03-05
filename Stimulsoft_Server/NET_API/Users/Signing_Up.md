# Signing Up

To create a new user, you must use the method **SignUp()** or asynchronous version **SignUpAsync()**:


**.NET API**

```
...
public void SignUp()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.SignUp("UserName", "Password");
} 
...
```

Or asynchronous method:


**.NET API**

```
...
public async void SignUpAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.SignUpAsync("UserName", "Password");
}
...
```

This call will create a new user in your instance of Stimulsoft Server. Before it does this, it also checks to make sure that both the username and email are unique. The password (up to 6 characters) is stored on the server as a hash and never sent to the client in the form of a plaintext.

In addition, we have two overridden methods for the signup action with additional info (first name and last name):


**.NET API**

```
...
public void Signup()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.SignUp("UserName@example.com", "Password", "FirstName", "LastName");
}

public async void SignupAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.SignUpAsync("UserName@example.com", "Password", "FirstName", "LastName");
}
...
```

You must to use an email address as the username.
