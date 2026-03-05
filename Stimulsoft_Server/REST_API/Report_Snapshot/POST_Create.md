## POST Create

**Description**:

Creating a new report snapshot in a workspace of the logged-in user. FolderKey field may contain the key of the parent folder, making sure that the report snapshot in the tree. If FolderKey empty or not specified, the report snapshot is displayed in the root folder.


**Url Structure**:

http://reports.stimulsoft.com/1/reportsnapshots


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object, which describing the new report snapshot:


**POST-data in the JSON-object**

```
...
{
    'Ident': 'ReportSnapshotItem',
    'Name': 'NewReportSnapshot',
    'Description': 'This is a new report snapshot'
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: aea7a6197b8c481eaf6077178f69f2bd" -d "{'Ident': 'ReportSnapshotItem', 'Name': 'NewReportSnapshot', 'Description': 'This is a new report snapshot'}" http://reports.stimulsoft.com/1/reportsnapshots


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "ItemSave",
    "ResultSuccess": true
}
...
```
