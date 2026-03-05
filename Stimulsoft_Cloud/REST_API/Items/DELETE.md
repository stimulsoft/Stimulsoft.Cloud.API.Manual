## DELETE

**Description**:

Removing an element from the cloud. However, the use of this command does not guarantee the immediate removal of the element from a tree, because the command only creates an internal task of service to delete the item and the actual deletion may be delayed for some time.


**Url Structure**:

https://cloud.stimulsoft.com/1/items/itemkey


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-AllowMoveToRecycleBin allows deleting an item to the recycle bin, by default it is set to true. To remove an item with referenced resources set x-sti-AllowMoveToRecycleBin to false. The itemkey parameter in the URI is the key of item and indicates the item whose data you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -H "x-sti-AllowMoveToRecycleBin: false" https://cloud.stimulsoft.com/1/items/ca3bfa74c8114b3a83fd08c04ab31f99


**Returns**:

The success of the command execution is checked by the content of the field ResultSuccess. ResultTaskKey field contains unique key of internal server tasks, created to remove the item.


**Sample JSON response**

```
...
{
  "Ident": "ItemDelete",
  "ResultTaskKey": "3c1df5fa46a14a17af32a5259834e254",
  "ResultSuccess": true
}
...
```
