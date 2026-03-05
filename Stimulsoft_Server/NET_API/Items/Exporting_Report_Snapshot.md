# Exporting Report Snapshot

The result of the construction of the report from **StiReportTemplateItem** is **StiReportSnapshotItem**. Export data from it can be done by methods **StiReportSnapshotItem.Export()** and **StiReportSnapshotItem.ExportAsync()**. The data is stored in the item **StiFileItem**. It should be created in advance with a specific type the constructor, as described in the previous chapter. Optional parameter method **StiReportSnapshotItem.Export()**  is an object **StiTextExportSet**, which describes many options of visualization in the report to export. This example demonstrates exporting the report snapshot to the Excel Document:


**.NET API**

```
...
public void ExportSnapshotToExcel()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    var reportSnapshotItem = connection.Items.Root.NewReportSnapshot("report-snapshot");
    reportSnapshotItem.Save();
    reportSnapshotItem.UploadFromFile(@"C:\report-snapshot.mdc");
    
    var fileItemExcel = connection.Items.Root.NewFile("ExcelDocument", StiFileType.Excel);
    fileItemExcel.Save();
    
    reportSnapshotItem.Export(fileItemExcel, 
    new StiTextExportSet
    {
        BorderType = Report.Export.StiTxtBorderType.UnicodeDouble, 
        CutLongLines = true, 
        KillSpaceGraphLines = true
    });
}
...
```

An example of an asynchronous method. Exporting a report snapshot to the XML file:


**.NET API**

```
...
public async void ExportSnapshotToXmlAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    var reportSnapshotItem = connection.Items.Root.NewReportSnapshot("report-snapshot");
    await reportSnapshotItem.SaveAsync();
    await reportSnapshotItem.UploadFromFileAsync(@"C:\report-snapshot.mdc");
    
    var fileItemXml = connection.Items.Root.NewFile("XmlFile", StiFileType.Xml);
    await fileItemXml.SaveAsync();
    
    await reportSnapshotItem.ExportAsync(fileItemXml);
}
...
```
