## GET List

**Description**:

Getting a list of report snapshots in a workspace of the logged-in user. The list is returned to the specified folder.


**Url Structure**:

http://reports.stimulsoft.com/1/reportsnapshots


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. Custom header x-sti-ItemKey used to identify the parent folder, which list of report snapshots needs to be retrieved. If this header is not present, it will get a list of report snapshots of the root folder.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: aea7a6197b8c481eaf6077178f69f2bd" http://reports.stimulsoft.com/1/reportsnapshots


**Returns**:

The JSON object containing the collection ResultItems, which contains a list of report snapshots in the specified folder of the current workspace. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "ItemFetchAll",
    "ResultItems": [
    {
        "Ident": "ReportSnapshotItem",
        "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
        "Name": "ReportSnapshot",
        "Created": "\/Date(1428933145000)\/",
        "Modified": "\/Date(1428933145000)\/",
        "IsMoveable": true,
        "Key": "4625a71ef47d46c3b5db7b5185a89e5b"
    },
    {
        "Ident": "ReportSnapshotItem",
        "WorkspaceKey": "1b11a087888f4a968ecbbaf74423647c",
        "Name": "ReportSnapshot1",
        "Description": "",
        "Created": "\/Date(1428928320000)\/",
        "Modified": "\/Date(1428933138000)\/",
        "IsMoveable": true,
        "Key": "6289e011469c4ed492c061fb142ee983"
    }
    ],
    "ResultSuccess": true
}
...
```
