## POST Create

**Description**:

Creating a new report template in a cloud of the logged-in user. FolderKey field may contain the key of the parent folder, making sure that the report template in the tree. If FolderKey empty or not specified, the report template is displayed in the root folder.


**Url Structure**:

https://cloud.stimulsoft.com/1/reporttemplates


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object, which describing the new report template:


**POST-data in the JSON-object**

```
...
{
    'Ident': 'ReportTemplateItem',
    'Name': 'NewReportTemplate',
    'Description': 'This is a new report template'
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: 1add6a4f1c5e481c80e964b613ee6089" -d "{'Ident': 'ReportTemplateItem', 'Name': 'NewReportTemplate', 'Description': 'This is a new report template'}" https://cloud.stimulsoft.com/1/reporttemplates


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
