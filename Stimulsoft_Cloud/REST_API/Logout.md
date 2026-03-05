# Logout

**Description**:

Log out of the current user.


**Url Structure**:

https://cloud.stimulsoft.com/1/logout


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: 1638c5f0e7d347dabb7651f194768a7e" https://cloud.stimulsoft.com/1/logout


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "UserLogout",
    "ResultSuccess": true
}
...
```
