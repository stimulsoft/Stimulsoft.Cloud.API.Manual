# Getting Item

To get an existing item is necessary to know the key that is passed to the method as a parameter. Use methods **StiItem.GetByKey()** and **StiItem.GetByKeyAsync()**:


**.NET API**

```
...
public void GetCalendarItem()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();

    var item = connection.Items.GetByKey("CalendarItemKey");
    if (item != null)
    {
        var calendarItem = item as StiCalendarItem;
        if (calendarItem != null)
        {
            var calendarItemDescription = calendarItem.Description;
        }
    }
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void GetCalendarItemAsync()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();

    var item = await connection.Items.GetByKeyAsync("CalendarItemKey");
    if (item != null)
    {
        var calendarItem = item as StiCalendarItem;
        if (calendarItem != null)
        {
            var calendarItemDescription = calendarItem.Description;
        }
    }
}
...
```
