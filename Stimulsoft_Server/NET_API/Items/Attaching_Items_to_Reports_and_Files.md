# Attaching Items to Reports and Files

The elements of type **StiFileItem** and **StiReportTemplateItem** can attach resource elements  (**StiFileItem**, **StiReportSnapshotItem**, **StiReportTemplateItem**). This is done using the method **AttachItem**(**StiResourceItem** **resourceItem**). Detaching the elements is performed using the method **DetachItem(StiResourceItem resourceItem)**. This example shows a file attachment into a report template:


**.NET API**

```
...
public void AttachItemToReportTemplate()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    // Report Template
    var reportTemplateItem = connection.Items.Root.NewReportTemplate("report-template");
    reportTemplateItem.Save();
    reportTemplateItem.UploadFromFile(@"C:\report.mrt");
    
    // Attached File
    var attachedFile = connection.Items.Root.NewFile("attach", StiFileType.Image);
    attachedFile.Save();
    attachedFile.UploadFromFile(@"C:\image.png");
    
    // Attach file to report template
    reportTemplateItem.AttachItem(attachedFile);
    
    // Detach file from report template
    reportTemplateItem.DetachItem(attachedFile);
}
...
```

Asynchronous method for a XSD-file attachment into a XML-file:


**.NET API**

```
...
public async void AttachXsdToXmlAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    // Xml File
    var xmlFile = connection.Items.Root.NewFile("data.xml", StiFileType.Xml);
    await xmlFile.SaveAsync();
    await xmlFile.UploadFromFileAsync(@"C:\data.xml");
    
    // Xsd File
    var xsdFile = connection.Items.Root.NewFile("data.xsd", StiFileType.Xsd);
    await xsdFile.SaveAsync();
    await xsdFile.UploadFromFileAsync(@"C:\data.xsd");
    
    // Attach Xsd to Xml
    await xmlFile.AttachItem(xsdFile);
    
    // Detach item
    await xmlFile.DetachItem(xsdFile);
}
...
```
