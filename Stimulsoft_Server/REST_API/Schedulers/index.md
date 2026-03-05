# Scheduler

**Schedulers** object describes schedulers - special data elements designed to run different tasks on schedule. This provides the possibility of automation of complex data processing. To get the list of schedulers, information about the status, and launch new tasks in the current workspace, use the command **Schedulers** with different methods. Since schedulers are one type of item, then getting a list of schedulers and detailed information about the scheduler, as well as creating, modifying, and deleting of schedulers may to produce the same as any other items (use the Items command). However, the scheduler have several unique action, so to work with schedulers use the following command.


**Name**

**Description**

[GET List](GET_List.md)

Getting a list of schedulers in a workspace of the logged-in user. The list is returned to the specified folder.

**GET Info**

Getting information about the scheduler in a workspace of the logged-in user.

**POST Create**

Creating a new scheduler in a workspace of the logged-in user. To successfully run the command you must fill the field Scheduler, which is an embedded object and describes the frequency of execution of actions, and contain a collection Actions, which describes a chain of actions.

FolderKey field may contain the key of the parent folder, making sure that the scheduler in the tree. If FolderKey empty or not specified, the scheduler is displayed in the root folder.

**PUT Edit**

Changing scheduler in a workspace of the logged-in user. This command does not allow change of the unique scheduler key, which is used as an identifier (field Key), and the type (field Ident = 'SchedulerItem'). Changing field FolderKey can move a scheduler to another folder in the tree (the root, if you specify a null value).

**DELETE**

Removing a scheduler from the current workspace. However, the use of this command does not guarantee the immediate removal of the scheduler from a tree, because the command only creates an internal task of server to delete the scheduler and the actual deletion may be delayed for some time.


The scheduler can have two states - running (track events and time, and depending on this, the scheduler can run) and stopped (not tracked any external state). The state of the scheduler described by two values - Started or Stopped.

**GET Info (Status)**

Getting status of the scheduler.

**PUT Edit (Status)**

Setting status of the scheduler.


The actions described in the scheduler are performed according to a schedule or event. To run the command immediately, use the command Run.

**Run**

Manual start of actions the scheduler.
