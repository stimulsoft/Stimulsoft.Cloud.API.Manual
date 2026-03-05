## PUT Edit

**Description**:

Changing roles of users in a workspace of the logged-in user. This command does not allow a change of the unique role name (field Key).


**Url Structure**:

http://reports.stimulsoft.com/1/roles/rolename


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The rolename parameter in the URI is the key of role and indicates the role whose data you want to change. In POST-data must specify the JSON-object describing the changing role:


**POST-data in the JSON-object**

```
...
{
    'Name': 'TestRole',
    'Permissions': 
    {
        'ItemCalendars': 'All',
        'ItemReportTemplates': 'View'
    }
}
...
```


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "{'Name':'TestRole','Permissions':{'ItemCalendars':'All','ItemReportTemplates':'View'}}" http://reports.stimulsoft.com/1/roles/TestRole


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
