## GET List

**Description**:

Getting a list of schedulers in a workspace of the logged-in user. The list is returned to the specified folder.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. Custom header x-sti-ItemKey used to identify the parent folder, which list of schedulers needs to be retrieved. If this header is not present, it will get a list of schedulers of the root folder.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12" http://reports.stimulsoft.com/1/schedulers


**Returns**:

The JSON object containing the collection ResultItems, which contains a list of schedulers in the specified folder of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemFetchAll",
    "ResultItems": [
    {
        "Ident": "SchedulerItem",
        "Scheduler": {
            "Ident": "Hourly",
            "RunAtMinute": 50,
            "Status": "Started",
            "TimeZone": "Belarus Standard Time",
            "NotifyUsers": [],
            "LastTime": "\/Date(1425290450582)\/",
            "NextTime": "\/Date(1425293400000)\/",
            "Actions": [
            {
                "Ident": "RunReportAction",
                "ReportTemplateItemKey": "335f165d59f6426ba427477dc44c6758",
                "ResultType": "ReportSnapshot",
                "FileItemName": "",
            }
            ]
        },
        "StateKey": "1",
        "WorkspaceKey": "3c153c20e49f46219575ea4f9074888e",
        "Name": "HourlyScheduler",
        "Description": "",
        "Created": "\/Date(1425047855537)\/",
        "Modified": "\/Date(1425047855537)\/",
        "IsMoveable": true,
        "Key": "871a9f8275214f4cbc1a563c9ce28e5c"
    }
    ],
    "ResultSuccess": true 
}
...
```
