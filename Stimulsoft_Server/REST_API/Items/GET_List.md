## GET List

**Description**:

Getting a list of elements in a workspace of the logged-in user. The list is returned to the specified folder.


**Url Structure**:

http://reports.stimulsoft.com/1/items


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. Custom header x-sti-ItemKey used to identify the parent folder, which list of elements needs to be retrieved. If this header is not present, it will get a list of elements of the root folder. To filter element types used header x-sti-FilterIdent. It may contain one of the values ​​in the table above Ident. If this header is absent, all elements from the requested collection will be returned. It is also possible to use the header x-sti-AllowDeleted, which is responsible for displaying the elements placed in the recycle bin (not removed completely).


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -H "x-sti-ItemKey: 7800e3265d06418a9ac4feb977fd4040" -H "x-sti-AllowDeleted: true" http://reports.stimulsoft.com/1/items


**Returns**:

The JSON object containing the collection ResultItems, which contains a list of items in the specified folder of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
  "Ident": "ItemFetchAll",
  "ResultItems": [
    {
      "Ident": "FolderItem",
      "FolderKey": "7800e3265d06418a9ac4feb977fd4040",
      "WorkspaceKey": "c25a38229d484ce589b983ed680f681e",
      "Name": "InternalFolder",
      "Description": "This is a second level folder",
      "Created": "\/Date(1425024762360)\/",
      "Modified": "\/Date(1425024762360)\/",
      "IsMoveable": true,
      "Key": "ac9485530c2e42cf9edef840a4816c4f"
    },
    {
      "Ident": "ReportTemplateItem",
      "StateKey": "2",
      "FolderKey": "7800e3265d06418a9ac4feb977fd4040",
      "WorkspaceKey": "c25a38229d484ce589b983ed680f681e",
      "Name": "SecondEmptyReport",
      "Description": "This is a internal report",
      "Created": "\/Date(1425025029473)\/",
      "Modified": "\/Date(1425042737867)\/",
      "IsMoveable": true,
      "Key": "649f1ff97b21448d963c4747279e86d9"
    }
  ],
  "ResultSuccess": true
}
...
```
