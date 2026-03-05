## Run

The command is used to render report. To work correctly, you must fist create two items – a report template what will be run, and the destination item where data will be stored. The source item is the current StiReportTemplate object. The destination item is the object of type StiFileItem or StiReportSnapshotItem. If the destination item is the StiFileItem, then report is converted to the format specified when creating file item (field 'FileType'). If the destination item is the StiReportSnapshotItem, then rendered report will be saved in the report snapshot item.


**Description**:

Manual starting of actions of the scheduler.


**Url Structure**:

http://reports.stimulsoft.com/1/reporttemplates/reporttemplatekey/run


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-DestinationItemKey contains the destination item key (an item with ident FileItem and ReportSnapshotItem). The reporttemplatekey parameter in the URI is the key of report template and indicates the report template whose you want to run.


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: 1add6a4f1c5e481c80e964b613ee6089" -H "x-sti-DestinationItemKey: cb64359ede7243d4a19ab0e19c42e9e1" -d "" http://reports.stimulsoft.com/1/reporttemplates/83a5f6d43351499fa9a2d40822f5772b/run


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully. ResultTaskKey field contains unique key of internal server tasks, set up to run the rendering of report template.


**Sample JSON response**

```
...
{
    "Ident": "ReportRun",
    "ResultTaskKey": "c375e1f4cd5645bab669bd124488329d",
    "ResultSuccess": true
}
...
```

To run the report with parameters, use the JSON data object as in the example below:

curl -X PUT -d "{'Parameters': [{'Ident': 'Single', 'Name':'param', 'Type': 'string', 'Value': 'testvalue'}]}" -H "x-sti-SessionKey: 8a8d4554fb564422a7232107a8ab29f3" http://reports.stimulsoft.com/1/reporttemplates/55617f45d7c641dc9b806f6859c995d1/run


In the POST data you must specify the JSON object that describes the parameters of the report template:


**POST-data in the JSON-object**

```
...
{
'Parameters': [
    {
        'Ident': 'Single',
        'Name': 'param',
        'Type': 'string',
        'Value': 'testvalue'
    }
]
}
...
```

Ident parameter may have values - '**Single**', '**Range**' and '**List**'.


**Sample JSON response

          ...
          {
          "Ident": "ReportRun",
          "Parameters": [
          {
          "Ident": "Single",
          "Name": "param",
          "Type": "string",
          "Value": "testvalue"
          }
          ],
          "ReportTemplateItemKey": "55617f45d7c641dc9b806f6859c995d1",
          "UserKey": "f215f398a01740638ef02e8e9437b40c",
          "TaskKey": "806019df4aec44e1aeeeb09a169e20f7",
          "ResultTaskKey": "806019df4aec44e1aeeeb09a169e20f7",
          "SessionKey": "8a8d4554fb564422a7232107a8ab29f3",
          "ResultSuccess": true
          }
          ...**
