## DELETE

**Description**:

Removing a file from the current workspace. However, the use of this command does not guarantee the immediate removal of the file from a tree, because the command only creates an internal task of server to delete the file and the actual deletion may be delayed for some time. This command remove file item and resources without using the recycle bin.


**Url Structure**:

http://reports.stimulsoft.com/1/files/filekey


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The filekey parameter in the URI is the key of file and indicates the file whose data and resources you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: 2aa74b48f7c542b9a17cbcfa5d43122d" http://reports.stimulsoft.com/1/files/bad8820fd26e4ab7b04dcc5afa932148


**Returns**:

The success of the command execution is checked by the content of the field ResultSuccess. ResultTaskKey field contains unique key of internal server tasks, created to remove the file item.


**Sample JSON response**

```
...
{
    "Ident": "ItemDelete",
    "ResultTaskKey": "8f70f36181c148c287c3a6721d9d3283",
    "ResultSuccess": true
}
...
```
