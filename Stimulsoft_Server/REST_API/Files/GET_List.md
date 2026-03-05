## GET List

**Description**:

Getting a list of files in a workspace of the logged-in user. The list is returned to the specified folder.


**Url Structure**:

http://reports.stimulsoft.com/1/files


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. Custom header x-sti-ItemKey used to identify the parent folder, which list of files needs to be retrieved. If this header is not present, it will get a list of files of the root folder.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: 2aa74b48f7c542b9a17cbcfa5d43122d" http://reports.stimulsoft.com/1/files


**Returns**:

The JSON object containing the collection ResultItems, which contains a list of files in the specified folder of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemFetchAll",
    "ResultItems": [
    {
        "Ident": "FileItem",
        "FileType": "Csv",
        "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
        "Name": "Small.csv",
        "Description": "",
        "Created": "\/Date(1427458480000)\/",
        "Modified": "\/Date(1427458480000)\/",
        "IsMoveable": true,
        "Key": "53efd43b18b7455e88d6013369473772"
    },
    {
        "Ident": "FileItem",
        "FileType": "Excel",
        "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
        "Name": "stat.xlsx",
        "Description": "",
        "Created": "\/Date(1427455740000)\/",
        "Modified": "\/Date(1427455740000)\/",
        "IsMoveable": true,
        "Key": "387df1f56670479897cd81716358f626"
    }
    ],
    "ResultSuccess": true
}
...
```
