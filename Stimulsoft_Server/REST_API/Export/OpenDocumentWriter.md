# Open Document Writer

There are two stages in the export of a report template:

* [A file item is created for a future report](#createdestinationfileitem);

* [Export a report template to the destination file item](#exportreporttemplatetodestinationfileitem).

### Create Destination File Item


**Url Structure**:

http://reports.stimulsoft.com/1/files


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object, which describing the new file item:


**POST-data in the JSON-object**

```
...
{
    'Ident': 'FileItem',
    'Name': 'ODW',
    'Description': 'This is a sample export to Open Document Writer',
    'FileType': 'OpenDocumentWriter'
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: 4ccbebaac38642b4a182d555aa09ee46" -d "{ 'Ident':'FileItem','Name':'ODW','Description':'This is a sample export to Open Document Writer', 'FileType': 'OpenDocumentWriter' }" http://reports.stimulsoft.com/1/files


**Returns**:

The JSON object containing the field ResultSessionKey, which is a list of members of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
  "Ident": "CommandListRun",
  "ContinueAfterError": false,
  "ResultCommands": [
    {
      "Ident": "ItemSave",
      "AllowSignalsReturn": false,
      "SaveEmptyResources": false,
      "ResultItems": [
        {
          "Ident": "FileItem",
          "FileType": "OpenDocumentWriter",
          "ShareLevel": "Private",
          "HasItems": false,
          "StateKey": "1",
          "WorkspaceKey": "8a87e146d96e4b2e9aa127b22d6d98df",
          "Name": "ODW",
          "Description": "This is a sample export to Open Document Writer",
          "Created": "\/Date(1588776549595)\/",
          "Modified": "\/Date(1588776549595)\/",
          "Visible": true,
          "Deleted": false,
          "IsMoveable": true,
          "Key": "6ad634d0764849b9801600ad8f7fe56b"
        }
      ],
      "ResultSuccess": true
    },
    {
      "Ident": "ItemResourceSave",
      "Type": "Insert",
      "ResultVersionKey": "236b612ef1ea4de6842e1cc4fd299e0e",
      "ResultSuccess": true
    }
  ],
  "ResultSuccess": true
}
...
```

### Export report template to Destination File Item


**Url Structure**:

http://reports.stimulsoft.com/1/reporttemplates/{ReportTemplateKey}/run


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-DestinationItemKey contains the unique key of the container element. When creating the container element, it is indicated as the value of the **Key** parameter in response.  In PUT-data must specify the JSON-object, which describing the new file item:


**PUT-data in the JSON-object**

```
...
{
    'FileItemName': 'ODW',
    'ExportSet': {
        'Ident': 'OpenDocumentWriter',
        'PageRange': {},
        'ImageQuality': '75'
        'ImageResolution': '200',
        'RemoveEmptySpaceAtBottom': 'false'
        ...
    }
}
...
```

**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ea46a3c2c2084439832ea4518d8a5af2" -H "x-sti-DestinationItemKey: 6ad634d0764849b9801600ad8f7fe56b" -d "{'FileItemName':'OpenDocumentWriter', 'ExportSet':{ 'Ident':'OpenDocumentWriter', 'PageRange': {}, 'ImageQuality': '100', 'ImageResolution':'200', 'RemoveEmptySpaceAtBottom': 'false' } }" http://reports.stimulsoft.com/1/reporttemplates/a8dde8679ecb43cbbba190786a2b44f3/run


**Returns**:

The JSON object contains the field "ResultTaskKey," which holds the key of the export task running in the background. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
  "Ident": "ReportRun",
  "AllowNotifications": false,
  "AllowSignals": false,
  "FileType": "ReportSnapshot",
  "ItemVisibility": true,
  "NotificationVisibility": false,
  "ResultTaskKey": "aff29fe55fb54c4d82951dddc7e6d6ef",
  "ResultSuccess": true
}
...
```
