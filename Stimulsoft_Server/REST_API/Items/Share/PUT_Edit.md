## PUT Edit

**Description**:

Changing information about access parameters of specified item in the workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/items/itemkey/share


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The itemkey parameter in the URI is the key of item and indicates the item whose data of the parameters of public access you want to change. In POST-data must specify the JSON-object, which describing the changes in sharing:


**POST-data in the JSON-object**

```
...
{
    'ShareLevel': 'Public'
}
...
```

**CURL example**:

curl -X PUT -H "x-sti-SessionKey: a690257860fe456aae4c852d41c12378" -d "{'ShareLevel':'Public'}" http://reports.stimulsoft.com/1/items/d6f94af9dbb945499349f2a36a3741dd/share


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
