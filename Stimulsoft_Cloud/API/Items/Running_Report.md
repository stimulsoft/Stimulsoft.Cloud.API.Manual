# Running Report

The result of creating Report Template in the tree is a new element type **StiReportTemplateItem**. This object describes the report without data. Designing items of the report is made through the Navigator interface, but managing the construction is possible by means of appropriate methods **StiReportTemplateItem.Run()** and **StiReportTemplateItem.RunAsync()**. The parameter specifies the item **StiReportTemplateItem** or **StiFileItem** where you saved the rendered report. The object must be created before saving. The item **StiFileItem** can be one of the possible types of enumeration **StiFileType** (ReportSnapshot, PDF, XPS, PowerPoint, HTML, Text, RichText, Word, OpenDocumentWriter, Excel, OpenDocumentCalc, Data, Image, XML, XSD, CSV, DBF). One of these values are specified in the method **StiCloudConnection.Items.Root.NewFile()** as a parameter. The following example creates a report template, loads data into it and runs the report, after which the result is stored in the report snapshot:


**.NET API**

```
...
public void RunReportToShapshot()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
    
    var reportTemplateItem = connection.Items.Root.NewReportTemplate("report-template");
    reportTemplateItem.Save();
    reportTemplateItem.UploadFromFile(@"C:\report.mrt");
    
    var reportSnapshotItem = connection.Items.Root.NewReportSnapshot("report-snapshot");
    reportSnapshotItem.Save();
    reportTemplateItem.Run(reportSnapshotItem);
}
...
```

Asynchronous method creates a report template, converts data and runs the report, after which the result is stored in the PDF file:


**.NET API**

```
...
public async void RunReportToPdfFileAsync()
{
    var connection = new StiCloudConnection("UserName@example.com", "Password");
    await connection.Accounts.Users.LoginAsync();
    
    var reportTemplateItem = connection.Items.Root.NewReportTemplate("report-template");
    await reportTemplateItem.SaveAsync();
    await reportTemplateItem.UploadFromFileAsync(@"C:\report.mrt");
    
    var pdfReportItem = connection.Items.Root.NewFile("report.pdf", StiFileType.Pdf);
    await pdfReportItem.SaveAsync();
    await reportTemplateItem.RunAsync(pdfReportItem);
}
...
```
