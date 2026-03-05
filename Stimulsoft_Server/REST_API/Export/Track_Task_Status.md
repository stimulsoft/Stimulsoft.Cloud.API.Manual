# Track Task Status

**Description**:

Getting the status of a task that is running in the background.


**Url Structure**:

http://reports.stimulsoft.com/1/task/{taskKey}


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The URL contains the task key for tracking its status.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: 1add6a4f1c5e481c80e964b613ee6089" http://reports.stimulsoft.com/1/task/{taskKey}


**Returns**:

The JSON object containing the collection ResultStatus, which contains a list of the task information. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "TaskStatus",
    "ResultStatus": {
        "Ident": "Task",
        "Name": "ReportRunAndTransfer",
        "Created": "2023-09-08T09:24:56.283Z",
        "Started": "2023-09-08T09:24:56.34Z",
        "Status": "Running",
        "IsMonitorTask": false,
        "IsWaiting": false,
        "IsRunning": true,
        "IsProcessed": false,
        "IsFinished": false,
        "IsStopped": false,
        "IsError": false
    },
    "ResultSuccess": true
    }
...
```
