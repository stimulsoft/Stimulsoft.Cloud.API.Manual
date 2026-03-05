## GET Info

**Description**:

Getting information about the role in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/roles/rolename


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The rolename parameter in the URI is the key of role and indicates the role whose data you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "" http://reports.stimulsoft.com/1/roles/User


**Returns**:

The JSON object containing the field ResultRole, which is the desired role of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
  "Ident": "RoleGet",
  "ResultRole": {
    "Name": "User",
    "Created": "\/Date(1425646886701)\/",
    "Modified": "\/Date(1425646886701)\/",
    "Permissions": {
      "ItemCalendars": "View",
      "ItemCloudStorages": "View",
      "ItemContactLists": "View",
      "ItemDashboards": "RunView",
      "ItemDataSources": "View",
      "ItemFiles": "View",
      "ItemFolders": "View",
      "ItemReportSnapshots": "RunView",
      "ItemReportTemplates": "RunView"
    },
    "IsSystem": true,
    "Key": "User"
  },
  "ResultSuccess": true
}
...
```
