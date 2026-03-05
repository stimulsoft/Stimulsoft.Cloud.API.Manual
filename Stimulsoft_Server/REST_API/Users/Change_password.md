## Change password

**Description**:

Change user password.


**Url Structure**:

http://reports.stimulsoft.com/1/users/username/changepassword


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The username parameter in the URI is the key user or its name and indicates the user whose data you want to get. Instead of the user name or key, you can specify the keyword "current" which replaces the identifier of the current user. In POST-data must specify the JSON-object describing the current and new passwords:


**POST-data in the JSON-object**

```
...
{
    'CurrentPassword': '111111',
    'NewPassword': '222222'
}
...
```


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "{ 'CurrentPassword': '111111', 'NewPassword': '222222' }" http://reports.stimulsoft.com/1/users/current/changepassword


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "UserChangePassword",
    "ResultSuccess": true
}
...
```
