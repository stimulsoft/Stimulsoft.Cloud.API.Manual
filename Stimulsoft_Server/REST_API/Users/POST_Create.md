## POST Create

**Description**:

Creating a new user in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/users


**Method**:

POST


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. In POST-data must specify the JSON-object describing the new user:


**POST-data in the JSON-object**

```
...
{
    'FirstName': 'John5',
    'LastName': 'Doe5',
    'UserName': 'j5@d5.com',
    'Password': '111111'
}
...
```

**CURL example**:

curl -X POST -H "x-sti-SessionKey: 55397673d1604f3a9aabf57c4ebaf856" -d "{ 'FirstName': 'John5', 'LastName': 'Doe5', 'UserName': 'j5@d5.com', 'Password': '111111' }" http://reports.stimulsoft.com/1/users


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
