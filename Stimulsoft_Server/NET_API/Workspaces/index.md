# Workspaces

For separation of data from different working groups Stimulsoft Server uses the concept of workspaces. Some users work in one workspace and their data are available to other users. Users working in different workspaces do not have access to each other.


In order to use the **StiWorkspaceConnection** class you should create an instance of **StiServerConnection** and call one of its methods (**StiServerConnection.****Accounts.****Workspaces**).


The StiWorkspace class provides access to information about the roles.

The workspace key can obtain an instance of this class. Use for this methods **GetByKey()** (**GetByKeyAsync()**).

There is also the fastest way to get an instance of the current workspace by calling the **Current** property in the **StiServerConnection****.Accounts.****Workspaces** class.
