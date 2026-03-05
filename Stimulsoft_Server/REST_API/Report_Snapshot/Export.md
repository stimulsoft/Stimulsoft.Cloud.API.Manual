## Export

The command is used to export data from report snapshot. Data from a snapshot can be exported to one of a supported formats by one of two ways:

* You must create a **FileItem** of specific type, which you want to export data. Then run the export command specifying the key of the **FileItem** in the custom header x-sti-DestinationItemKey;

* You can export data directly, specifying in the POST-data a JSON-object containing object **ExportSet** - a list of options to export, individual for each data type.


**Description**:

Export data from a ReportSnapshot to a FileItem.


**Url Structure**:

http://reports.stimulsoft.com/1/reportsnapshots/reportsnapshotkey/export


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-DestinationItemKey contains the destination item key (an item with ident “FileItem”). The reportsnapshotkey parameter in the URI is the key of report snapshot and indicates the report snapshot whose you want to export. In POST-data must specify the JSON-object, which describing the ExportSet-object (example for simple export to a PDF-file):


**POST-data in the JSON-object**

```
...
{
    'ExportSet': 
    {
        'Ident': 'Pdf',
        'PageRange': { },
        'EmbeddedFonts': false,
        'DitheringType': 'None',
        'PdfACompliance': true
    }
}
...
```

More detail about ExportSet-object see the appendix.


**CURL example**:

1 way:

curl -X PUT -H "x-sti-SessionKey: aea7a6197b8c481eaf6077178f69f2bd" -H "x-sti-DestinationItemKey: f393774c11664bc29f1a0b6c64b67617" -d "" http://reports.stimulsoft.com/1/reportsnapshots/6289e011469c4ed492c061fb142ee983/export


2 way:

curl -X PUT -H "x-sti-SessionKey: aea7a6197b8c481eaf6077178f69f2bd" -d "{'ExportSet':{'Ident':'Pdf','PageRange':{},'EmbeddedFonts':false,'DitheringType':'None','PdfACompliance':true}}" http://reports.stimulsoft.com/1/reportsnapshots/6289e011469c4ed492c061fb142ee983/export


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully. ResultTaskKey field contains unique key of internal server tasks, set up to run the export data from report snapshot.


**Sample JSON response**

```
...
{
    "Ident": "ReportExport",
    "ResultTaskKey": "ba493223bc884ad19a6dab8b04b84c1d",
    "ResultSuccess": true
}
...
```
