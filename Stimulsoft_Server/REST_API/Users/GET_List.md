# GET List

**Description**:

Getting a list of users in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/users


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. You may use header x-sti-WorkspaceKey, containing key workspace that you are requesting a list of users.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: 55397673d1604f3a9aabf57c4ebaf856" http://reports.stimulsoft.com/1/users


**Returns**:

The JSON object containing the field ResultSessionKey, which is a list of members of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "UserFetchAll",
    "ResultUsers": [
    {
        "RoleKey": "Administrator",
        "WorkspaceKey": "c25a38229d484ce589b983ed680f681e",
        "FirstName": "John",
        "LastName": "Doe",
        "UserName": "j@d.com",
        "Created": "\/Date(1424679345637)\/",
        "Modified": "\/Date(1424679345637)\/",
        "LastLogin": "\/Date(1424698541377)\/",
        "Key": "ddb025415b68494ca8a9aee27ad73bc1"
    },
    {
        "RoleKey": "User",
        "WorkspaceKey": "c25a38229d484ce589b983ed680f681e",
        "FirstName": "John5",
        "LastName": "Doe5",
        "UserName": "j5@d5.com",
        "Created": "\/Date(1424699430000)\/",
        "Modified": "\/Date(1424699430367)\/",
        "Key": "e7c2b7d3160f418b9286fbb24e7b0dd9"
    }
    ],
    "ResultSuccess": true
}
...
```
