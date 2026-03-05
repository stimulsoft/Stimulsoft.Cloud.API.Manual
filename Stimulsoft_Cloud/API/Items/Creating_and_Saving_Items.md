# Creating and Saving Items

Position in the hierarchical tree structure of elements defined by the connection element and folders. Therefore, to create the item, you must first create an object of type **StiFolderItem**, specifying its position in the tree, and then use one of the methods to create an item of a particular type. The root element of the tree is represented by an instance of the class **StiFolderItem: StiCloudConnection.Items.Root**. After defining properties of the new item is necessary to perform his method **StiItem.Save()** or **StiItem.SaveAsync()**. The following example shows how to create a folder in the root of the tree of elements and add the calendar (describes Monday) to this folder:


**.NET API**

```
...
public void CreateNewCalendarItem()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
            
    var folderItem = connection.Items.Root.NewFolder("folder");
    folderItem.Save();

    var calendarItem = folderItem.NewCalendar("NewCalendar");
    calendarItem.Dates.Add(new StiCalendarDate("Monday", StiDaysOfWeek.Monday));
    calendarItem.Save();
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void CreateNewCalendarItemAsync()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();

    var folderItem = connection.Items.Root.NewFolder("folder");
    await folderItem.SaveAsync();

    var calendarItem = folderItem.NewCalendar("NewCalendar");
    calendarItem.Dates.Add(new StiCalendarDate("Monday", StiDaysOfWeek.Monday));
    await calendarItem.SaveAsync();
}
...
```
