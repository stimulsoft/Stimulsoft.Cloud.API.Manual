# Deleting Item

Remove element by calling **Delete()** (**DeleteAsync()**):


**.NET API**

```
...
public void DeleteItem()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var item = connection.Items.GetByKey("CalendarItemKey");
    if (item != null)
    {
        //Delete item with skipping undeletable items
        item.Delete(true, true);
    }
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void DeleteItemAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var item = await connection.Items.GetByKeyAsync("CalendarItemKey");
    if (item != null)
    {
        //Delete item without moving it into the recycle bin
        await item.DeleteAsync(false);
    }
}
...
```
