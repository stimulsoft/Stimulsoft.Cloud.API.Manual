## POST Create

**Description**:

Creating a new element in a workspace of the logged-in user. To successfully run the command you must fill in the fields Ident (assigned a value in accordance with the required type of item has one of the values listed in the table above), and Name. FolderKey field may contain the key of the parent folder, making sure that the element in the tree. If FolderKey empty or not specified, the item is displayed in the root folder.


**Url Structure**:

http://reports.stimulsoft.com/1/items


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object, which describing the new element:


**POST-data in the JSON-object**

```
...
{
    'Ident': 'FolderItem',
    'Name': 'InternalFolder',
    'Description': 'This is a second level folder',
    'FolderKey': '7800e3265d06418a9ac4feb977fd4040'
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "{'Ident':'FolderItem','Name':'InternalFolder','Description':'This is a second level folder','FolderKey':'7800e3265d06418a9ac4feb977fd4040'}" http://reports.stimulsoft.com/1/items


**Returns**:

The JSON-object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
  "Ident": "ItemSave",
  "ResultSuccess": true
}
...
```
