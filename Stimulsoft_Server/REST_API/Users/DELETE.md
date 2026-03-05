## DELETE

**Description**:

Removing a user from the current workspace. Removing a last user with administrator privileges isn't allowed.


**Url Structure**:

http://reports.stimulsoft.com/1/users/username


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The username parameter in the URI is the key of user or its name and indicates the user whose data you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" http://reports.stimulsoft.com/1/users/j5@d5.com


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "UserDelete",
    "ResultSuccess": true
}
...
```
