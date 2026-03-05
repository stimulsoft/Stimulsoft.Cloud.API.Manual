## DELETE

**Description**:

Removing a role from the current workspace. Removing a last role with administrator privileges isn't allowed.


**Url Structure**:

http://reports.stimulsoft.com/1/roles/rolename


**Method**:

DELETE


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The rolename parameter in the URI is the key of role and indicates the role whose data you want to delete.


**CURL example**:

curl -X DELETE -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" http://reports.stimulsoft.com/1/roles/TestRoleOne


**Returns**:

The JSON-object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "RoleDelete",
    "ResultSuccess": true
}
...
```
