## GET Info

**Description**:

Getting information about the element in a cloud of the logged-in user.


**Url Structure**:

https://cloud.stimulsoft.com/1/items/itemkey


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The itemkey parameter in the URI is the key of the element and indicates the element whose data you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: da5053abac4544e9856e05bbda14f46a" https://cloud.stimulsoft.com/1/items/d2283e85e9724859bcd024c3f7b982ea


**Returns**:

The JSON-object containing the field ResultItem, which is the required element of the cloud. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
  "Ident": "ItemGet",
  "ResultItem": {
    "Ident": "FileItem",
    "FileType": "Xml",
    "AttachedItems": [
      "fa3514a207504deea0c065032d5d438f"
    ],
    "IsDataSource": true,
    "FolderKey": "d1a339068a474eaab65628f2fbef33a6",
    
    "Name": "Demo.xml",
    "Description": "",
    "Created": "\/Date(1427455735000)\/",
    "Modified": "\/Date(1427986596000)\/",
    "IsMoveable": true,
    "Key": "d2283e85e9724859bcd024c3f7b982ea"
  },
  "ResultLastVersionKey": "ab832999641b458eacd8969a408e303e",
  "ResultSuccess": true
}
...
```
