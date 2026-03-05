## GET Info

**Description**:

Getting information about the user in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/users/username


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The username parameter in the URI is the key user or its name and indicates the user whose data you want to get. Instead of the user name or key, you can specify the keyword "current" which replaces the identifier of the current user.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" http://reports.stimulsoft.com/1/users/j51@d51.com


**Returns**:

The JSON object containing the field ResultUsers, in which there is data on the user in the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "UserGet",
    "ResultUser": {
        "RoleKey": "User",
        "WorkspaceKey": "c25a38229d484ce589b983ed680f681e",
        "FirstName": "John51",
        "LastName": "Doe51",
        "UserName": "j51@d51.com",
        "Created": "\/Date(1424765701477)\/",
        "Modified": "\/Date(1424765701777)\/",
        "Key": "029f450a853b4248bdc278c382512f90"
    },
    "ResultSuccess": true
}
...
```
