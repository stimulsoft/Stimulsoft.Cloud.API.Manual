## POST Create

**Description**:

Creating a new file in a workspace of the logged-in user. This command creates an element of type StiFileItem and allows you to load the resource file (no more than 90Kb) encoded in base64. If the resource file size exceeds 90Kb, it is necessary to split the file into chunks (not exceeding 90 Kb), encode them to Base64 and send first chunk with this command, and all the other chunks upload using the command described below. FolderKey field may contain the key of the parent folder, making sure that the file in the tree. If FolderKey empty or not specified, the file is displayed in the root folder.


**Url Structure**:

http://reports.stimulsoft.com/1/files


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object, which describing the new file with Base64-encoded resource data:


**POST-data in the JSON-object**

```
...
{
    'Ident': 'FileItem',
    'Name': 'Test',
    'Description': 'This is a TEST',
    'FileType': 'Excel',
    'Resource': 'dGVzdCBzdHJpbmcgZGF0YQ=='
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: 2aa74b48f7c542b9a17cbcfa5d43122d" -d "{'Ident':'FileItem','Name':'Test','Description':'This is a TEST', 'FileType': 'Excel', 'Resource': 'dGVzdCBzdHJpbmcgZGF0YQ=='}" http://reports.stimulsoft.com/1/files


**Returns**:

The JSON object containing the collection ResultCommands with two items. The first has Ident ItemSave and describes the created element StiFileItem. The field Key contain the key of created file item. The second element of root colletion has Ident ItemResourceSave and contain the field ResultVersionKey. The value of this field (version key) need to download pieces of the file. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "CommandListRun",
    "ResultCommands": [
    {
        "Ident": "ItemSave",
        "Items": [
        {
            "Ident": "FileItem",
            "FileType": "Excel",
            "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
            "Name": "Test",
            "Description": "This is a TEST",
            "Created": "\/Date(1427464242386)\/",
            "Modified": "\/Date(1427464242386)\/",
            "IsMoveable": true,
            "Key": "bad8820fd26e4ab7b04dcc5afa932148"
        }
        ],
        "SessionKey": "2aa74b48f7c542b9a17cbcfa5d43122d",
        "ResultSuccess": true
    },
    {
        "Ident": "ItemResourceSave",
        "ResultVersionKey": "74cc142d844a496797d78b7e34b49687",
        "ResultSuccess": true
    }
    ],
    "ResultSuccess": true 
}
...
```
