## PUT Edit

**Description**:

Changing element in a workspace of the logged-in user. This command does not allow change of the unique item key, which is used as an identifier (field Key), and the type (field Ident). Changing field FolderKey can move an item to another folder in the tree (the root, if you specify a null value).


**Url Structure**:

http://reports.stimulsoft.com/1/items/itemkey


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The itemkey parameter in the URI is the key of item and indicates the element whose data you want to change. In POST-data must specify the JSON-object describing the changed item data:


**POST-data in the JSON-object**

```
...
{
    'Name': 'SecondEmptyReport',
    'Description': 'This is a edited report',
    'FolderKey': ''
}
...
```

**CURL example:**

curl -X PUT -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "{'Name':'SecondEmptyReport','Description':'This is a edited report', 'FolderKey':''}" http://reports.stimulsoft.com/1/items/ca3bfa74c8114b3a83fd08c04ab31f99


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
