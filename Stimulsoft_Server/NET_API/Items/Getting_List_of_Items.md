# Getting List of Items

To find or process items, there is a method that allows you to get a list of all objects **StiItem**, to which the current user can access. Use the method **FetchAll()** (**FetchAllAsync()**).


**.NET API**

```
...
public void ProcessItems()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    var items = connection.Items.Root.FetchChilds();

    //find folder with name "Folder1"
    var folder1 = items.First(a => a.Name == "Folder1");
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void ProcessItemsAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    var items = await connection.Items.Root.FetchChildsAsync();

    //is exist any folder
    var isFolder = items.Any(a => a.IsFolder);
}
...
```
