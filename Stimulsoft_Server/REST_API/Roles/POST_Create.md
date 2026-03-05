## POST Create

**Description**:

Creating a new role in a workspace of the logged-in user. This command ignores the initialization key of role (field Key) and puts this value automatically.


**Url Structure**:

http://reports.stimulsoft.com/1/roles


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object describing the new role:


**POST-data in the JSON-object**

```
...
{
    'Name': 'TestRole',
    'Created': '\/Date(1424872039434)\/',
    'Modified': '\/Date(1424872039434)\/',
    'Permissions': 
    {
        'ItemCalendars': 'All',
        'ItemCloudStorages': 'View',
        'ItemContactLists': 'View',
        'ItemDashboards': 'View',
        'ItemDataSources': 'View',
        'ItemFiles': 'View',
        'ItemFolders': 'View',
        'ItemReportSnapshots': 'RunView',
        'ItemReportTemplates': 'RunView'
  }
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "{'Name':'TestRole','Created':'\/Date(1424872039434)\/','Modified':'\/Date(1424872039434)\/','Permissions'

{'ItemCalendars':'All','ItemCloudStorages':'View','ItemContactLists':'View','ItemDashboards':'View','ItemDataSources':'View','ItemFiles':'View','ItemFolders':'View','ItemReportSnapshots':'RunView','ItemReportTemplates':'RunView'}}" http://reports.stimulsoft.com/1/roles


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "RoleSave",
    "ResultSuccess": true
}
...
```
