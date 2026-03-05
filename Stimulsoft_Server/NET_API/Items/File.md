# File

For working with uploaded files, Stimulsoft Server has a special type of a **StiItem** - **StiFileItem**, which has some specific features and capabilities. **StiFileItem** is an element that provides storing files, uploaded by users. Some files contain data that can be used in the reports as a data source – these are XLS documents, CSV tables, DBF databases, JSON strings etc. Getting the structured data from these files is possible using the **StiFileItem.GetData** (**StiFileItem.GetDataAsync**) method. At creation of a StiFileItem you must specify the type of data which the loaded file contains. Allowed values listed in enumeration **StiFileType**:

  * Unknown - Unsupported file type

  * ReportSnapshot - Rendered report

  * Pdf – PDF file

  * Xps – XPS file

  * Html – HTML file

  * Text – Text file

  * RichText – RichText file format (RTF)

  * Word – MS Word document file

  * Excel – MS Excel document file

  * PowerPoint – MS PowerPoint presentation file

  * OpenDocumentWriter – OpenDocument file for Writer

  * OpenDocumentCalc – OpenDocument file for Calc

  * Data - One of multiple data format

  * Image - One of multiple image format

  * Xml – XML file

  * Xsd – XSD file

  * Csv – CSV file

  * Dbf – DBF file

  * Sylk – SYLK file

  * Dif – DIF file

  * Json - Data in the JSON format


These examples create an element of the **StiFileItem** type, load a file into it and receive the data as a table from it:


**.NET API**

```
...
public void FileItemGetData()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    connection.Accounts.Users.Login("UserName@example.com", "Password");
    
    const string excelFileName = @"C:\sample.xls";
    
    var fileItem = connection.Items.Root.NewFile("ExcelFile", StiFileType.Excel).Save();
    fileItem.UploadFromFile(excelFileName);
    
    var table1 = fileItem.GetData("Sheet1");
    var rowsCount = table1.Rows.Count;
    
    connection.Accounts.Users.Logout();
}
...
```

An asynchronous method:


**.NET API**

```
...
public async void FileItemGetDataAsync()
{
    var connection = new Stimulsoft.Server.Connect.StiServerConnection("localhost:40010");
    await connection.Accounts.Users.LoginAsync("UserName@example.com", "Password");
    
    const string excelFileName = @"C:\sample.xls";
    
    var fileItem = await connection.Items.Root.NewFile("ExcelFile", StiFileType.Excel).SaveAsync();
    await fileItem.UploadFromFileAsync(excelFileName);
    
    var table1 = await fileItem.GetDataAsync("Sheet1");
    var firstCellData = table1.Rows[0].ItemArray[0];
    
    await connection.Accounts.Users.LogoutAsync();
}
...
```
