## GET List

**Description**:

Getting a list of roles.


**Url Structure**:

http://reports.stimulsoft.com/1/roles


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. You may use header x-sti-WorkspaceKey, containing key workspace that you are requesting a list of roles.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" http://reports.stimulsoft.com/1/roles


**Returns**:

The JSON object containing the collection ResultUsers, which is a list of the roles of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response

          ...
          {
            "Ident": "RoleFetchAll",
            "ResultRoles": [
              {
                "Name": "Supervisor",
                "Created": "\/Date(1425645969540)\/",
                "Modified": "\/Date(1425645969540)\/",
                "Permissions": {
                  "ItemCalendars": "CreateDeleteModifyView",
                  "ItemCloudStorages": "CreateDeleteModifyView",
                  "ItemContactLists": "CreateDeleteModifyView",
                  "ItemDashboards": "All",
                  "ItemDataSources": "CreateDeleteModifyView",
                  "ItemFiles": "CreateDeleteModifyView",
                  "ItemFolders": "CreateDeleteModifyView",
                  "ItemReportSnapshots": "All",
                  "ItemReportTemplates": "All",
                  "ItemSchedulers": "All"
                },
                "IsSupervisor": true,
                "IsAdministrator": true,
                "IsSystem": true,
                "Key": "Supervisor"
              },
              {
                "Name": "Administrator",
                "Created": "\/Date(1425645969540)\/",
                "Modified": "\/Date(1425645969540)\/",
                "Permissions": {
                  "ItemCalendars": "CreateDeleteModifyView",
                  "ItemCloudStorages": "CreateDeleteModifyView",
                  "ItemContactLists": "CreateDeleteModifyView",
                  "ItemDashboards": "All",
                  "ItemDataSources": "CreateDeleteModifyView",
                  "ItemFiles": "CreateDeleteModifyView",
                  "ItemFolders": "CreateDeleteModifyView",
                  "ItemReportSnapshots": "All",
                  "ItemReportTemplates": "All",
                  "ItemSchedulers": "All"
                },
                "IsAdministrator": true,
                "IsSystem": true,
                "Key": "Administrator"
              },
              {
                "Name": "Manager",
                "Created": "\/Date(1425645969540)\/",
                "Modified": "\/Date(1425645969540)\/",
                "Permissions": {
                  "ItemCalendars": "CreateDeleteModifyView",
                  "ItemCloudStorages": "CreateDeleteModifyView",
                  "ItemContactLists": "CreateDeleteModifyView",
                  "ItemDashboards": "All",
                  "ItemDataSources": "CreateDeleteModifyView",
                  "ItemFiles": "CreateDeleteModifyView",
                  "ItemFolders": "CreateDeleteModifyView",
                  "ItemReportSnapshots": "All",
                  "ItemReportTemplates": "All",
                  "ItemSchedulers": "View"
                },
                "IsSystem": true,
                "Key": "Manager"
              },
              {
                "Name": "User",
                "Created": "\/Date(1425645969540)\/",
                "Modified": "\/Date(1425645969540)\/",
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
              }
            ],
            "ResultSuccess": true
          }
          ...**
