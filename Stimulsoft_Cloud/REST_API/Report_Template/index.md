# Report Template

ReportTemplate object describes report templates - special data elements what contains the structure of the report. To build this report you need to execute command Run. As a result was obtained an element of type StiReportSnapshot – rendered report with data. Since report templates are one type of item, then getting a list of report templates and detailed information about the report templates, as well as creating and deleting of report templates may to produce the same as any other items (use the Items command). However, the report templates have several unique action, so to work with report templates use the following command.


| **Name** | **Description** |
| --- | --- |
| **GET List** | Getting a list of report templates in a cloud of the logged-in user. The list is returned to the specified folder. |
| **GET Info** | Getting information about the report templates in a cloud of the logged-in user. |
| **POST Create** | Creating a new report template in a cloud of the logged-in user. FolderKey field may contain the key of the parent folder, making sure that the report template in the tree. If FolderKey empty or not specified, the report template is displayed in the root folder. |
| **DELETE** | Removing a report template from the cloud. However, the use of this command does not guarantee the immediate removal of the report template from a tree, because the command only creates an internal task of service to delete the report template and the actual deletion may be delayed for some time. |
| **POST Duplicate** | Creating a new copy of the report template in a cloud of the logged-in user. |
