# Items

The basis of the **Stimulsoft Server** functionality is operations on items. The item is an object that can be visually observed in the object tree on the left side of the interface of the client application. All items are inherited from the root abstract class **StiItem** and, there is one of the following classes depending on the functionality provided:


* **StiCalendarItem** - used to create a scheduler;

* **StiContactListItem** - used for sending reports via e-mail;

* **StiDataSourceItem** - used to connect external data sources;

* **StiFileItem** - used to connect external data sources;

* **StiFolderItem** - provides a hierarchical tree structure elements;

* **StiReportSnapshotItem** - rendered data report;

* **StiReportTemplateItem** - report template for building;

* **StiSchedulerItem** - used to automate actions.
