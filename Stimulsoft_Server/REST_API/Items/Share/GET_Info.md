## GET Info

**Description**:

Getting information about access parameters of specified item in the workspace of the logged-in user


**Url Structure**:

http://reports.stimulsoft.com/1/items/itemkey/share


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The itemkey parameter in the URI is the key of item and indicates the item whose data on the parameters of public access you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: a690257860fe456aae4c852d41c12378" http://reports.stimulsoft.com/1/items/d6f94af9dbb945499349f2a36a3741dd/share


**Returns**:

JSON-object containing the field with the description of the parameters of public access element. ResultShareLevel describes the level of public access (Private, Registered and Public). ResultShareExpires contains the expiration date of public access (can be omitted). ResultUrl contains a link for public access. The success of the command execution is checked against the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemGetShareInfo",
    "ResultShareLevel": "Private",
    "ResultShareExpires": "\/Date(1427801160000+0300)\/",
    "ResultUrl": "http://reports.stimulsoft.com/s/1",
    "ResultSuccess": true
}
...
```
