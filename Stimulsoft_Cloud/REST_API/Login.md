# Login

**Description**:

Login with username and password.


**Url Structure**:

https://cloud.stimulsoft.com/1/login


**Method**:

GET


**Parameters**:

Two custom header: x-sti-UserName and x-sti-Password, containing the username and password, respectively.


**CURL example**:

curl -X GET -H "x-sti-UserName: a@a.com" -H "x-sti-Password: 111111" https://cloud.stimulsoft.com/1/login


**Returns**:

The JSON object containing the field ResultSessionKey, which will be further used for communication with the service. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "UserLogin",
    "ResultSessionKey": "1716cdf3dd2b480580824798a03f030d",
    "ResultWorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
    "ResultUserKey": "50a4f98ec1804a6498829b05554c5608",
    "ResultRole": {
        "Name": "Supervisor",
        "Created": "\/Date(1426675381267)\/",
        "Modified": "\/Date(1426675381267)\/",
        "Permissions": {
            
            "ItemFiles": "CreateDeleteModifyView",
            "ItemFolders": "CreateDeleteModifyView",
            "ItemReportTemplates": "All"
            
        },
        "IsSupervisor": true,
        "IsAdministrator": true,
        "IsSystem": true,
        "Key": "Supervisor"
    },
    "ResultSettings": {
        "Localization": "en",
        "Theme": {
            "Ident": "Office2013White",
            "Style": "Teal"
        },
        "Key": "50a4f98ec1804a6498829b05554c5608"
    },
    "ResultProductInfo": {
        "ProductName": "Stimulsoft Cloud"
    },
    "ResultSuccess": true
}
...
```
