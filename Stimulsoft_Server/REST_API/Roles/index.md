# Roles

Object Role describes permissions for different data types supported by the system. The main characteristic of this object is set **Permissions**, which may contain a table of permissions:


**Permission**

**Description**

ItemCalendars

Permissions for Calendars

ItemCloudStorages

Permissions for Cloud Storages

ItemContactLists

Permissions for Contactlists

ItemDashboards

Permissions for Dashboards

ItemDataSources

Permissions for Datasources

ItemFiles

Permissions for Files

ItemFolders

Permissions for Folder

ItemReportSnapshots

Permissions for ReportSnapshots

ItemReportTemplates

Permissions for ReportTemplates

ItemSchedulers

Permissions for Schedulers

Each of these permissions have one of the values:


**Value**

**Description**

None

Deny all

Create

Allows to create an item

Delete

Allows to delete an item

Modify

Allows to modify an item

Run

Allows to run an item

View

Allows to view an item

DeleteModifyView

Allows delete, modify and view an item

ModifyView

Allows modify and view an item

CreateDeleteModifyView

Allows create, delete, modify and view an item

RunView

Allows run and view an item

All

Allow any action with an item

Permission example:


**Sample JSON response

          ...
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
          }
          ...**

To get the list of roles, data modification, and to create new roles in the current workspace and delete existing roles, use the command Roles with different methods. The default configuration of the system, there are four roles (fields marked with "IsSystem": true) - **Supervisor**, **Administrator**, **Manager** and **User** (a role name the same as the key). These roles can't be removed or changed. It is possible to modify only the roles created by the user.


**Name**

**Description**

**GET List**

Getting a list of roles.

**GET Info**

Getting information about the role in a workspace of the logged-in user.

**POST Create**

Creating a new role in a workspace of the logged-in user. This command ignores the initialization key of role (field Key) and puts this value automatically.

**PUT Edit**

Changing roles of users in a workspace of the logged-in user. This command does not allow a change of the unique role name (field Key).

**DELETE**

Removing a role from the current workspace. Removing a last role with administrator privileges isn't allowed.
