# Getting List of Items

To find or process items, there is a method that allows you to get a list of all objects **StiItem**, to which the current user can access. Use the method **FetchAll()** (**FetchAllAsync()**).


**.NET API**

```
...
public void ProcessItems()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
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
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
    var items = await connection.Items.Root.FetchChildsAsync();

    //is exist any folder
    var isFolder = items.Any(a => a.IsFolder);
}
...
```
