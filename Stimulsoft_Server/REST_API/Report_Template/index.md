# Report Template

ReportTemplate object describes report templates - special data elements what contains the structure of the report. To build this report you need to execute command Run. As a result was obtained an element of type StiReportSnapshot – rendered report with data. Since report templates are one type of item, then getting a list of report templates and detailed information about the report templates, as well as creating and deleting of report templates may to produce the same as any other items (use the Items command). However, the report templates have several unique action, so to work with report templates use the following command.


**Name**

**Description**

**GET List**

Getting a list of report templates in a workspace of the logged-in user. The list is returned to the specified folder.

**GET Info**

Getting information about the report templates in a workspace of the logged-in user.

**POST Create**

Creating a new report template in a workspace of the logged-in user.

FolderKey field may contain the key of the parent folder, making sure that the report template in the tree. If FolderKey empty or not specified, the report template is displayed in the root folder.

**DELETE**

Removing a report template from the current workspace. However, the use of this command does not guarantee the immediate removal of the report template from a tree, because the command only creates an internal task of server to delete the report template and the actual deletion may be delayed for some time.


The command is used to render report. To work correctly, you must fist create two items – a report template what will be run, and the destination item where data will be stored. The source item is the current StiReportTemplate object. The destination item is the object of type [StiFileItem](../Files/index.md) or [StiReportSnapshotItem](../Report_Snapshot/index.md). If the destination item is the **StiFileItem**, then report is converted to the format specified when creating file item (field 'FileType'). If the destination item is the **StiReportSnapshotItem**, then rendered report will be saved in the report snapshot item.

**Run**

Manual starting of actions of the scheduler.

**POST Duplicate**

Creating a new copy of the report template in a workspace of the logged-in user.
