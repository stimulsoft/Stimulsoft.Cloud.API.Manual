## DELETE Reset

**Description**:

Resetting access parameters of specified item in the workspace of the logged-in user to default. These are ShareLevel, established in Private (no public access), ShareMode set in Download, as well as the absence of ShareExpires (period of validity of link of public access).


**Url Structure**:

http://reports.stimulsoft.com/1/items/itemkey/share


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The itemkey parameter in the URI is the key of item and indicates the item whose data of the parameters of public access you want to set to default.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: a690257860fe456aae4c852d41c12378" http://reports.stimulsoft.com/1/items/d6f94af9dbb945499349f2a36a3741dd/share


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "ItemSetShareInfo",
    "ResultSuccess": true
}
...
```
