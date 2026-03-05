# Report Snapshot

ReportSnapshot object describes report snapshots - special data elements what contains the rendered report. Since ReportSnapshot are one type of item, then getting a list of report snapshots and detailed information about the report snapshots, as well as creating and deleting of report snapshots may to produce the same as any other items (use the Items command). However, the report snapshots have several unique action, so to work with report snapshots use the following command.


**Name**

**Description**

**GET List**

Getting a list of report snapshots in a workspace of the logged-in user. The list is returned to the specified folder.

**GET Info**

Getting information about the report snapshots in a workspace of the logged-in user.

**POST Create**

Creating a new report snapshot in a workspace of the logged-in user.

FolderKey field may contain the key of the parent folder, making sure that the report snapshot in the tree. If FolderKey empty or not specified, the report snapshot is displayed in the root folder.

**DELETE**

Removing a report snapshot from the current workspace. However, the use of this command does not guarantee the immediate removal of the report snapshot from a tree, because the command only creates an internal task of server to delete the report snapshot and the actual deletion may be delayed for some time.


The command is used to export data from report snapshot.

Data from a snapshot can be exported to one of a supported formats by one of two ways:


You must create a FileItem of specific type, which you want to export data. Then run the export command specifying the key of the FileItem in the custom header x-sti-DestinationItemKey;

You can export data directly, specifying in the POST-data a JSON-object containing object ExportSet - a list of options to export, individual for each data type.


**Export**

Export data from a ReportSnapshot to a FileItem.
