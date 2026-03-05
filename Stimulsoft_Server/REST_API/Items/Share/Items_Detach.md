## Items Detach

**Description**:

Detaching one item from another. Keys of the attached elements are in the AttachedItems collection.


**Url Structure**:

http://reports.stimulsoft.com/1/items/itemkey/detach


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-DestinationItemKey contains the detached element. The itemkey parameter in the URI is the key of item and indicates the element to which must be attached an element.


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: da5053abac4544e9856e05bbda14f46a" -H "x-sti-destinationitemkey: fa3514a207504deea0c065032d5d438f" -d "" http://reports.stimulsoft.com/1/items/d2283e85e9724859bcd024c3f7b982ea/detach


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
