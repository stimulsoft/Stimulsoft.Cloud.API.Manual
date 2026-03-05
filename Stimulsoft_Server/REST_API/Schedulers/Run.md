## Run

The actions described in the scheduler are performed according to a schedule or event. To run the command immediately, use the command Run.


**Description**:

Manual start of actions the scheduler.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers/schedulerkey/run


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The schedulerkey parameter in the URI is the key of scheduler and indicates the scheduler whose you want to run.


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12" -d "" http://reports.stimulsoft.com/1/schedulers/871a9f8275214f4cbc1a563c9ce28e5c/run


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully. ResultTaskKey field contains unique key of internal server tasks, set up to run the scheduler’s actions.


**Sample JSON response**

```
...
{
    "Ident": "SchedulerRun",
    "ResultTaskKey": "412d7812d60d449db380ef3ccb51e80d",
    "ResultSuccess": true
}
...
```
