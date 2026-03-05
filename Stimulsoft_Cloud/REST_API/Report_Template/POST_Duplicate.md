## POST Create

**Description**:

Creating a new copy of the report template in a cloud of the logged-in user.


**Url Structure**:

https://cloud.stimulsoft.com/1/reporttemplates


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The reporttemplatekey parameter in the URI is the key of report template and indicates the report template whose data you want to copy.


**CURL example**:

curl -X POST -H "x-sti-SessionKey: 3fd143cd876048a188a6a3d69da0f535" -d "" http://cloud.stimulsoft.com/1/reporttemplates/7e4e950c0eb54241995efe1b48fedb6e/duplicate


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


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
                    "Ident": "ReportTemplateItem",
                    "RefreshFrequency": "Always",
                    "CacheMode": "Off",
                    "StateKey": "1",
                    "ShareLevel": "Private",
                    "WorkspaceKey": "b150683855854affbc98b142d4c61cea",
                    "Name": "ChartStyle_Copy",
                    "Created": "\/Date(1644323381839)\/",
                    "Modified": "\/Date(1644323381839)\/",
                    "Visible": true,
                    "Deleted": false,
                    "IsFolder": false,
                    "IsMoveable": true,
                    "Key": "bb4af6d48c304d558060334988af1291"
                }
            ],
            "ResultSuccess": true
        },
        {
            "Ident": "ItemResourceSave",
            "Type": "Insert",
            "ResultVersionKey": "789221129c624a25b2a46f553c0c66d6",
            "ResultSuccess": true
        }
    ],
    "ResultSuccess": true
}

...
```
