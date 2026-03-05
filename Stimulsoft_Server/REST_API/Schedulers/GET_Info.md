## GET Info

**Description**:

Getting information about the scheduler in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers/schedulerkey


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The schedulerkey parameter in the URI is the key of the scheduler and indicates the scheduler whose data you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" http://reports.stimulsoft.com/1/items/7800e3265d06418a9ac4feb977fd4040


**Returns**:

The JSON object containing the field ResultItem, which is the required scheduler of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemGet",
    "ResultItem": {
        "Ident": "SchedulerItem",
        "Scheduler": {
            "Ident": "Hourly",
            "RunAtMinute": 50,
            "Status": "Started",
            "TimeZone": "Greenwich Standard Time",
            "NotifyUsers": [],
            "NextTime": "\/Date(1425300600000)\/",
            "Actions": [
            {
                "Ident": "RunReportAction",
                "ReportTemplateItemKey": "c68ec75e239b4d1a8f2032fd2d204629",
                "ResultType": "ReportSnapshot",
                "FileItemName": "",
                "AttachmentDelivery": "Link"
            }
            ]
        },
        "StateKey": "2",
        "WorkspaceKey": "3c153c20e49f46219575ea4f9074888e",
        "Name": "HourlyScheduler",
        "Description": "Edited Description",
        "Created": "\/Date(1425295716657)\/",
        "Modified": "\/Date(1425299145087)\/",
        "IsMoveable": true,
        "Key": "6a447a392c454325ba436629b827644b"
    },
    "ResultSuccess": true
}
...
```
