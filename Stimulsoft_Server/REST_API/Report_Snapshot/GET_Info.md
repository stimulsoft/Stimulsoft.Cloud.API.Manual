## GET Info

**Description**:

Getting information about the report snapshots in a workspace of the logged-in user.


**Url Structure**:

http://reports.stimulsoft.com/1/reportsnapshots/reportsnapshotkey


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The reportsnapshotkey parameter in the URI is the key of the report snapshots and indicates the report snapshots whose data you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: aea7a6197b8c481eaf6077178f69f2bd" http://reports.stimulsoft.com/1/reportsnapshots/6289e011469c4ed492c061fb142ee983


**Returns**:

The JSON object containing the field ResultItem, which is the required report snapshot of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemGet",
    "ResultItem": 
    {
        "Ident": "ReportSnapshotItem",
        "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
        "Name": "ReportSnapshot1",
        "Description": "",
        "Created": "\/Date(1428928320000)\/",
        "Modified": "\/Date(1428933138000)\/",
        "IsMoveable": true,
        "Key": "6289e011469c4ed492c061fb142ee983"
    },
    "ResultLastVersionKey": "3fce6a2f25c44ea2a23fce402054fb77",
    "ResultSuccess": true
}
...
```
