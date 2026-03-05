# Scheduling Actions

**Stimulsoft Server** supports flexible system schedulers that allow the automation of various actions and events schedule. The object StiSchedulerItem inherited from **StiItem** is used to work with the scheduler. After creating an instance of this object, you must add actions using the method **StiSchedulerItem.AddRunReportAction()**. The parameters of this overloaded method take several sets of objects that define the functionality of the scheduler. The minimum set of parameters is as follows:


* **AddRunReportAction**

(StiReportTemplateItem reportTemplateItem, StiReportSnapshotItem reportSnapshotItem) – at work scheduler builds a report template **reportTemplateItem** and stores it to a snapshot reportSnapshotItem;

* **AddRunReportAction**

(StiReportTemplateItem reportTemplateItem, StiFileItem fileItem) – at work scheduler builds a report template **reportTemplateItem** and export it to a file fileItem.

* **AddRunReportAction**

(StiReportTemplateItem reportTemplateItem, StiContactListItem contactListItem, StiFileType fileType) – at work scheduler builds a report template **reportTemplateItem**, export it to a file of fileType type and sends the results by e-mail to contacts from contactListItem.


To start the scheduler immediately, the **StiSchedulerItem.Run()** (**StiSchedulerItem.RunAsync()**) method is used. This example creates a scheduler to render the report as a snapshot:


**.NET API**

```
...
public void CreateSchedulerAndRunReportToSnapshot()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    // Create folder
    var folderItem = connection.Items.Root.NewFolder("folder");
    folderItem.Save();
    
    // Create report template
    var reportTemplateItem = folderItem.NewReportTemplate("report-template");
    reportTemplateItem.Save();
    reportTemplateItem.UploadFromFile(@"c:\ReportTemplate.mrt");
    
    // Create report snapshot
    var reportSnapshotItem = folderItem.NewReportSnapshot("report-snapshot");
    reportSnapshotItem.Save();
    
    // Create scheduler
    var schedulerItem = folderItem.NewScheduler("scheduler", StiSchedulerIdent.Once);
    schedulerItem.AddRunReportAction(reportTemplateItem, reportSnapshotItem);
    schedulerItem.Save();
    
    // Run scheduler
    schedulerItem.Run();
    
    connection.Accounts.Users.Logout();
}
...
```

This asynchronous method creates a scheduler which renders the template to the PDF file:


**.NET API**

```
...
public async void CreateSchedulerAndRunReportToFileAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    // Create folder
    var folderItem = connection.Items.Root.NewFolder("folder");
    await folderItem.SaveAsync();
    
    // Create report template
    var reportTemplateItem = folderItem.NewReportTemplate("report-template");
    await reportTemplateItem.SaveAsync();
    await reportTemplateItem.UploadFromFileAsync(@"c:\ReportTemplate.mrt");
    
    // Create file
    var fileItem = folderItem.NewFile("file", StiFileType.Pdf);
    await fileItem.SaveAsync();
    
    // Create scheduler
    var schedulerItem = folderItem.NewScheduler("scheduler", StiSchedulerIdent.Once);
    schedulerItem.AddRunReportAction(reportTemplateItem, fileItem);
    await schedulerItem.SaveAsync();
    
    // Run scheduler
    await schedulerItem.RunAsync();
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```

This example creates a scheduler which renders the template to the PDF file and sends it to the email addresses listed in the contact element:


**.NET API**

```
...
public async void CreateSchedulerAndRunReportToContactsAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    // Create folder
    var folderItem = connection.Items.Root.NewFolder("folder");
    await folderItem.SaveAsync();
    
    // Create report template
    var reportTemplateItem = folderItem.NewReportTemplate("report-template");
    await reportTemplateItem.SaveAsync();
    await reportTemplateItem.UploadFromFileAsync(@"c:\ReportTemplate.mrt");
    
    // Create contact list
    var contactListItem = folderItem.NewContactList("contacts", "smith@example.com, jones@example.com");
    contactListItem.Save();
    
    // Create scheduler
    var schedulerItem = folderItem.NewScheduler("scheduler", StiSchedulerIdent.Once);
    schedulerItem.AddRunReportAction(reportTemplateItem, contactListItem, StiFileType.Pdf);
    await schedulerItem.SaveAsync();
    
    // Run scheduler
    await schedulerItem.RunAsync();
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```

The scheduler can have two states (describes the objects **StiSchedulerStatus**) – running (track events and time, and depending on this, the scheduler can run) and stopped (not tracked any external state). The state of the scheduler is described by two values – Started or Stopped. To set the scheduler status the **StiSchedulerItem.SetStatus()** (**StiSchedulerItem.SetStatusAsync()**) method is used. This example gets the status of the scheduler:


**.NET API**

```
...
public void CreateSchedulerAndGetState()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    var schedulerItem = connection.Items.Root.NewScheduler("scheduler", StiSchedulerIdent.Hourly).Save();
    
    var status = schedulerItem.GetStatus();
    
    Debug.WriteLine(status == StiSchedulerStatus.Stopped ? "Scheduler Stopped" : "Scheduler Started");
    
    connection.Accounts.Users.Logout();
}
...
```

This example sets a scheduler status asynchronously:


**.NET API**

```
...
public async void CreateSchedulerAndSetStateAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    var schedulerItem = connection.Items.Root.NewScheduler("scheduler", StiSchedulerIdent.Hourly).SaveAsync();
    
    await schedulerItem.Result.SetStatusAsync(StiSchedulerStatus.Stopped);
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
