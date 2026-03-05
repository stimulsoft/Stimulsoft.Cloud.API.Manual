## GET_Info (Status)

**Description**:

Getting status of the scheduler.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers/schedulerkey/status


**Method**:

GET


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The schedulerkey parameter in the URI is the key of scheduler and indicates the scheduler whose state you want to get.


**CURL example**:

curl -X GET -H "x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12" http://reports.stimulsoft.com/1/schedulers/6a447a392c454325ba436629b827644b/status


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully. ResultStatus field contains the current state of the scheduler.


**Sample JSON response**

```
...
{
    "Ident": "SchedulerGetStatus",
    "ResultStatus": "Started",
    "ResultSuccess": true
}
...
```
