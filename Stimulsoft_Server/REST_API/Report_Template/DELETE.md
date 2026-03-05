## DELETE

**Description**:

Removing a report template from the current workspace. However, the use of this command does not guarantee the immediate removal of the report template from a tree, because the command only creates an internal task of server to delete the report template and the actual deletion may be delayed for some time.


**Url Structure**:

http://reports.stimulsoft.com/1/reporttemplates/reporttemplatekey


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-AllowMoveToRecycleBin allows deleting an item to the recycle bin, by default it is set to true. To remove an item with referenced resources set x-sti-AllowMoveToRecycleBin to false. The reporttemplatekey parameter in the URI is the key of report template and indicates the report template whose data you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: 1add6a4f1c5e481c80e964b613ee6089" -H "x-sti-AllowMoveToRecycleBin: false" http://reports.stimulsoft.com/1/schedulers/0a8b68eb3e334fb798a8a4db3a9ee109


**Returns**:

The success of the command execution is checked by the content of the field ResultSuccess. ResultTaskKey field contains unique key of internal server tasks, created to remove the report template.


**Sample JSON response**

```
...
{
    "Ident": "ItemDelete",
    "ResultTaskKey": "2728300b164f4a358c6df65ee7ab9304",
    "ResultSuccess": true 
}
...
```
