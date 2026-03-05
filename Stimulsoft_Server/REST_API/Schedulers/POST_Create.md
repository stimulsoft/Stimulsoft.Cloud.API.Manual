## POST Create

**Description**:

Creating a new scheduler in a workspace of the logged-in user. To successfully run the command you must fill the field Scheduler, which is an embedded object and describes the frequency of execution of actions, and contain a collection Actions, which describes a chain of actions. FolderKey field may contain the key of the parent folder, making sure that the scheduler in the tree. If FolderKey empty or not specified, the scheduler is displayed in the root folder.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object, which describing the new scheduler:


**POST-data in the JSON-object**

```
...
{
    'Ident': 'SchedulerItem',
    'Scheduler': 
    {
        'Ident': 'Hourly',
        'RunAtMinute': 30,
        'Status': 'Started',
        'TimeZone': 'Greenwich Standard Time',
        'NotifyUsers': [
        ],
        'Actions': [
        {
            'Ident': 'RunReportAction',
            'ReportTemplateItemKey': 'c68ec75e239b4d1a8f2032fd2d204629',
            'ResultType': 'ReportSnapshot',
            'FileItemName': '',
            'AttachmentDelivery': 'Link'
        }
        ]
    },
    'Name': 'NewHourlyScheduler',
    'Description': 'Created Hourly Scheduler'
}
...
```

**CURL example**:

curl-XPOST-H"x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12"- d "{'Ident':'SchedulerItem','Scheduler': {'Ident':'Hourly','RunAtMinute':30,'Status':'Started','TimeZone':'Greenwich Standard Time',

'NotifyUsers':[],'Actions':[{'Ident':'RunReportAction','ReportTemplateItemKey':'c68ec75e239b4d1a8f2032fd2d204629','ResultType':'ReportSnapshot','FileItemName':'','AttachmentDelivery':'Link'}]},'Name':'NewHourlyScheduler','Description':'Created Hourly Scheduler'}"

http://reports.stimulsoft.com/1/schedulers


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
