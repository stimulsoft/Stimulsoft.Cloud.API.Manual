## GET Download

**Description**:

Getting information about the file (including Base64-encoded resource) in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/files/filekey


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The filekey parameter in the URI is the key of the file item and indicates the file whose data you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: 2aa74b48f7c542b9a17cbcfa5d43122d" http://reports.stimulsoft.com/1/files/53efd43b18b7455e88d6013369473772


**Returns**:

The JSON object containing the collection ResultCommands with two items. The first has Ident ItemGet and describes the element StiFileItem, the second has Ident ItemResourceGet and describes the resource (file contents). ResultResource field contains data from a file in Base64-form. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "CommandListRun",
    "ResultCommands": [
    {
        "Ident": "ItemGet",
        "ItemKey": "53efd43b18b7455e88d6013369473772",
        "ResultItem": 
        {
            "Ident": "FileItem",
            "FileType": "Csv",
            "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
            "Name": "Small.csv",
            "Description": "",
            "Created": "\/Date(1427458480000)\/",
            "Modified": "\/Date(1427458480000)\/",
            "IsMoveable": true,
            "Key": "53efd43b18b7455e88d6013369473772"
        },
        "ResultLastVersionKey": "3af1a24040fe4fe18916376d405720d2",
        "SessionKey": "2aa74b48f7c542b9a17cbcfa5d43122d",
        "ResultSuccess": true
    },
    {
    "Ident": "ItemResourceGet",
    "ItemKey": "53efd43b18b7455e88d6013369473772",
    "ResultResource": "aWQ7UGVyc29uO1R5cGU7QVNFDQoxO3Rlc3RfMDE7TTsxDQoyO3Rlc3RfMDI7RjszDQozO3Rlc3RfMDM7Rjs0DQo0O3Rlc3RfMDQ7TTs0DQo1O3Rlc3RfMDU7RjsxDQo2O3Rlc3RfMDY7TTszDQo3O3Rlc3RfMDc7TTsyDQo4O3Rl
    c3RfMDg7Rjs0DQo5O3Rlc3RfMDk7RjsxDQoxMDt0ZXN0XzEwO007NA0KMTE7dGVzdF8xMTtNOzQNCjEyO3Rlc3RfMTI7TTszDQoxMzt0ZXN0XzEzO0Y7MQ0KMTQ7dGVzdF8xNDtGOzQNCjE1O3Rlc3RfMTU7RjsyDQoxNjt0ZXN0X
    zE2O0Y7Mw0KMTc7dGVzdF8xNztGOzENCjE4O3Rlc3RfMTg7TTs0DQoxOTt0ZXN0XzE5O007MQ0KMjA7dGVzdF8yMDtGOzINCg==",
    "SessionKey": "2aa74b48f7c542b9a17cbcfa5d43122d",
    "ResultSuccess": true
    }
    ],
    "ResultSuccess": true
}
...
```
