## DELETE

**Description**:

Removing a report snapshot from the current workspace. However, the use of this command does not guarantee the immediate removal of the report snapshot from a tree, because the command only creates an internal task of server to delete the report snapshot and the actual deletion may be delayed for some time.


**Url Structure**:

http://reports.stimulsoft.com/1/reportsnapshots/reportsnapshotkey


Method:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-AllowMoveToRecycleBin allows deleting an item to the recycle bin, by default it is set to true. To remove an item with referenced resources set x-sti-AllowMoveToRecycleBin to false. The reportsnapshotkey parameter in the URI is the key of report snapshot and indicates the report snapshot whose data you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: aea7a6197b8c481eaf6077178f69f2bd" -H "x-sti-AllowMoveToRecycleBin: false" http://reports.stimulsoft.com/1/reportsnapshots/0b796ffe64d8454c9d8aa8eb38323e0d


**Returns**:

The success of the command execution is checked by the content of the field ResultSuccess. ResultTaskKey field contains unique key of internal server tasks, created to remove the report snapshot.


**Sample JSON response**

```
...
{
    "Ident": "ItemDelete",
    "ResultTaskKey": "82d1fe4a5c0c4f0b9207daceb6a7ffa6",
    "ResultSuccess": true
}
...
```
