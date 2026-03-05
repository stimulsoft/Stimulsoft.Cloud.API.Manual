## GET Info

**Description**:

Getting information about the report templates in a cloud of the logged-in user.


**Url Structure**:

https://cloud.stimulsoft.com/1/reporttemplates/reporttemplatekey


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The reporttemplatekey parameter in the URI is the key of the report templates and indicates the report templates whose data you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: 1add6a4f1c5e481c80e964b613ee6089" https://cloud.stimulsoft.com/1/reporttemplates/83a5f6d43351499fa9a2d40822f5772b


**Returns**:

The JSON object containing the field ResultItem, which is the required report template of the cloud. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemGet",
    "ResultItem": 
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
    },
    "ResultLastVersionKey": "4ae62efae4d74b6aab74567980e36b19",
    "ResultSuccess": true
}
...
```
