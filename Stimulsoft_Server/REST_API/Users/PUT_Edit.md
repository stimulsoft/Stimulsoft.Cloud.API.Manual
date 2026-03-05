## PUT Edit

**Description**:

Changing user data in a workspace of the logged-in user. This command does not allow change of the unique user name, which is used as an identifier, and a password - for this purpose there is other command.


**Url Structure**:

http://reports.stimulsoft.com/1/users/username


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The username parameter in the URI is the key user or its name and indicates the user whose data you want to edit. Instead of the user name or key, you can specify the keyword "current" which replaces the identifier of the current user. In POST-data must specify the JSON-object describing the changed user data:


**POST-data in the JSON-object**

```
...
{
    'FirstName': 'John00',
    'LastName': 'Doe00'
}
...
```

**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "{ 'FirstName': 'John00', 'LastName': 'Doe00', 'RoleKey': 'Manager' }" http://reports.stimulsoft.com/1/users/j5@d5.com


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "UserSave",
    "ResultSuccess": true
}
...
```
