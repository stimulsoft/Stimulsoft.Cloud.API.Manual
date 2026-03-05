## GET List

**Description**:

Getting a list of report templates in a workspace of the logged-in user. The list is returned to the specified folder.


**Url Structure**:

http://reports.stimulsoft.com/1/reporttemplates


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. Custom header x-sti-ItemKey used to identify the parent folder, which list of report templates needs to be retrieved. If this header is not present, it will get a list of report templates of the root folder.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: 1add6a4f1c5e481c80e964b613ee6089" http://reports.stimulsoft.com/1/reporttemplates


**Returns**:

The JSON object containing the collection ResultItems, which contains a list of report templates in the specified folder of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemFetchAll",
    "ResultItems": [
    {
        "Ident": "ReportTemplateItem",
        "StateKey": "e",
        "AttachedItems": [
        "53efd43b18b7455e88d6013369473772"
        ],
        "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
        "Name": "Report",
        "Description": "",
        "Created": "\/Date(1427718722000)\/",
        "Modified": "\/Date(1427795741000)\/",
        "IsMoveable": true,
        "Key": "83a5f6d43351499fa9a2d40822f5772b"
    }
    ],
    "ResultSuccess": true
}
...
```
