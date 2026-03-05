# Resource Item

Some element types (**StiFileItem**, **StiReportSnapshotItem**, **StiReportTemplateItem**) include resources. Using the methods **UploadFromFile()**, **UploadFromFileAsync()**, **UploadFromArray()**, **UploadFromArrayAsync()**, **DownloadToFile()**, **DownloadToFileAsync()**, **DownloadToArray()**, **DownloadToArrayAsync()**. You can manipulate the data contained in these resources. For example, creating a file on the server with the loading data into it looks like this:


**.NET API**

```
...
public void CreateNewFile()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var content = File.ReadAllBytes(@"C:\testfile.xml");

    var newFile = connection.Items.Root.NewFile("TestFile.xml");
    newFile.Save();

    newFile.UploadFromArray(content);
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void CreateNewTemplateAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var newTemplate = connection.Items.Root.NewReportTemplate("Master-Detail");
    await newTemplate.SaveAsync();

    await newTemplate.UploadFromFileAsync(@"C:\master-detail.mrt");
}
...
```

Loading item from the server and saving it to a file on the local computer as follows:


**.NET API**

```
...
public void DownloadFile()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");

    var newFile = connection.Items.GetByKey("FileItemKey");
    if (newFile is StiFileItem)
    {
        var data = (newFile as StiFileItem).DownloadToArray();
        File.WriteAllBytes(@"c:\newfile", data);
    }
}
...
```

Asynchronous method:


**.NET API**

```
...
public async void DownloadFileAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");

    var report = await connection.Items.GetByKeyAsync("ReportTemplateItemKey");
    if (report is StiReportTemplateItem)
    {
        await (report as StiReportTemplateItem).DownloadToFileAsync(@"C:\Master-Detail.mrt");
    }
}
...
```
