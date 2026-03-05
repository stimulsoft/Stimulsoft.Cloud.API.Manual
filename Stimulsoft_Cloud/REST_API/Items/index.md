# Items

Items object describes the data items supported by the system. This is an abstract class that combines different types of elements. At creation of an element its type is specified in the Ident field and never changes:


**Object**

**Description**

**Ident**

StiFolderItem

Folder, provides hierarchy of structure of elements

FolderItem

StiReportTemplateItem

Report template

ReportTemplateItem

To get the list of elements, modify the data, and to create new elements in the current workspace and removing existing elements, use command Items with various methods. Each element has a unique key, which uniquely identifies it in the list of elements. Data hierarchy as a tree is realized by an element type StiFolderItem, key element it is specified in the field of FolderKey as designation of the parental folder of an element. The identifier of this element is specified in the FolderKey of other elements and provides identification of the parent folder of an element. If this field is empty or not initialized to any value, then the element belongs to the root folder.


**Name**

**Description**

[GET List](Get_List.md)

Getting a list of elements in a cloud of the logged-in user. The list is returned to the specified folder.

**GET Info**

Getting information about the element in a cloud of the logged-in user.

**POST Create**

Creating a new element in a cloud of the logged-in user. To successfully run the command you must fill in the fields Ident (assigned a value in accordance with the required type of item has one of the values listed in the table above), and Name. FolderKey field may contain the key of the parent folder, making sure that the element in the tree. If FolderKey empty or not specified, the item is displayed in the root folder.

**PUT Edit**

Changing element in a cloud of the logged-in user. This command does not allow change of the unique item key, which is used as an identifier (field Key), and the type (field Ident). Changing field FolderKey can move an item to another folder in the tree (the root, if you specify a null value).

**DELETE**

Removing an element from the current cloud. However, the use of this command does not guarantee the immediate removal of the element from a tree, because the command only creates an internal task of service to delete the item and the actual deletion may be delayed for some time.
