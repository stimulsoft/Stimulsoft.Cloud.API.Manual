# Roles

**Stimulsoft Server** supports a Role-based Access Control. Role is an object that determines the level of user access to system resources. Members having the same role have the same rights of access to system objects. The most important property of the role is **StiRole.Permissions**. It is an object of the **StiRolePermissions** class that describes a set of permissions (**StiPermissions**) for system objects:


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

* **None** - Denies all;

* **Create** - Allows creating an item;

* **Delete** - Allows deleting an item;

* **Modify** - Allows modifying an item;

* **Run** - Allows running an item;

* **View** - Allows viewing an item;

* **ModifyView** - Allows modifying and viewing an item;

* **CreateDeleteModifyView** - Allows creating, deleting, modifying and viewing an item;

* **RunView** - Allows running and viewing an item;

* **All** - Allows any action with an item.


In order to use the **StiUserConnection** class you should create an instance of **StiServerConnection** and call one of its methods (**StiServerConnection****.Accounts.****Roles**).


The **StiRole** class provides access to information about the roles.

The role name or the key can obtain an instance of this class. For this use methods **GetByName()** (**GetByNameAsync()**) and **GetByKey()** (**GetByKeyAsync()**) respectively.

There is also the fastest way to get an instance of the current role by calling the Current property in the **StiServerConnection. Roles** class.
