## DELETE

**Description**:

Removing a scheduler from the current workspace. However, the use of this command does not guarantee the immediate removal of the scheduler from a tree, because the command only creates an internal task of server to delete the scheduler and the actual deletion may be delayed for some time.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers/schedulerkey


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-AllowMoveToRecycleBin allows deleting an item to the recycle bin, by default it is set to true. To remove an item with referenced resources set x-sti-AllowMoveToRecycleBin to false. The schedulerkey parameter in the URI is the key of scheduler and indicates the scheduler whose data you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12" -H "x-sti-AllowMoveToRecycleBin: false" http://reports.stimulsoft.com/1/schedulers/92046b1ae6e049a68791311f4a4256ce


**Returns**:

The success of the command execution is checked by the content of the field ResultSuccess. ResultTaskKey field contains unique key of internal server tasks, created to remove the scheduler.


**Sample JSON response**

```
...
{
    "Ident": "ItemDelete",
    "ResultTaskKey": "775713fd9614415b9578bcf60c65f7c9",
    "ResultSuccess": true
}
...
```
