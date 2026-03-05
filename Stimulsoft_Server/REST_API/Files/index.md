# Files

Files object describes files - special data elements designed to management of external data and uploading/downloading of user files used to generate reports (data to be imported, images, etc.). This provides the possibility of external resources processing. FileType property of FileItem describes the content type of the file and can have values from this table:


**Identifier**

**Description**

Unknown

Unsupported file type

ReportSnapshot

Rendered report

Pdf

PDF-file

Xps

XPS-file

Html

HTML-file

Text

Text file

RichText

RichText file format (RTF)

Word

MS Word document file

Excel

MS Excel document file

PowerPoint

MS PowerPoint presentation file

OpenDocumentWriter

OpenDocument-file for Writer

OpenDocumentCalc

OpenDocument-file for Calc

Data

One of multiple data format

Image

One of multiple image format

Xml

XML-file

Xsd

XSD-file

Csv

CSV-file

Dbf

DBF-file

Sylk

Sylk-file

Dif

Dif-file

Json

Data in JSON format

To get the list of files, download and upload resources use the command Files with different methods. Since files are one type of item, then getting a list of files and detailed information about the files, modifying and deleting of files may to produce the same as any other items (use the Items command). However, the files have several unique action, so to work with files use the following command.


**Name**

**Description**

**GET List**

Getting a list of files in a workspace of the logged-in user. The list is returned to the specified folder.

**GET Download**

Getting information about the file (including Base64-encoded resource) in a workspace of the logged-in user.

**POST Create**

Creating a new file in a workspace of the logged-in user.

This command creates an element of type StiFileItem and allows you to load the resource file (no more than 90Kb) encoded in base64. If the resource file size exceeds 90Kb, it is necessary to split the file into chunks (not exceeding 90 Kb), encode them to Base64 and send first chunk with this command, and all the other chunks upload using the command described below.

FolderKey field may contain the key of the parent folder, making sure that the file in the tree. If FolderKey empty or not specified, the file is displayed in the root folder.

**PUT Append**

Upload a new chunk of file in a workspace of the logged-in user. Сhunk size must be less than 90Kb and encoded in Base64-form.

**DELETE**

Removing a file from the current workspace. However, the use of this command does not guarantee the immediate removal of the file from a tree, because the command only creates an internal task of server to delete the file and the actual deletion may be delayed for some time.

This command remove file item and resources without using the recycle bin.
