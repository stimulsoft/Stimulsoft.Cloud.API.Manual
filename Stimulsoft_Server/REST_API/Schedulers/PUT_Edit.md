## PUT Edit

**Description**:

Changing scheduler in a workspace of the logged-in user. This command does not allow change of the unique scheduler key, which is used as an identifier (field Key), and the type (field Ident = 'SchedulerItem'). Changing field FolderKey can move a scheduler to another folder in the tree (the root, if you specify a null value).


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers/schedulerkey


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The schedulerkey parameter in the URI is the key of scheduler and indicates the scheduler whose data you want to change. In POST-data must specify the JSON-object describing the changed scheduler data:


**POST-data in the JSON-object**

```
...
{
    'Description': 'Edited Description'
}
...
```

**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12" -d "{'Description': 'Edited Description'}"

http://reports.stimulsoft.com/1/schedulers/6a447a392c454325ba436629b827644b


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "ItemSave",
    "ResultSuccess": true
}
...
```
