## PUT Edit (Status)

**Description**:

Setting status of the scheduler.


**Url Structure**:

http://reports.stimulsoft.com/1/schedulers/schedulerkey/status


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom header x-sti-Status contains the required state of scheduler (Started or Stopped). The schedulerkey parameter in the URI is the key of scheduler and indicates the scheduler whose state you want to set.


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ed46247f12fc44cf92f284ff5c8ffc12" -H "x-sti-Status: Started" -d "" http://reports.stimulsoft.com/1/schedulers/6a447a392c454325ba436629b827644b/status


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


**Sample JSON response**

```
...
{
    "Ident": "SchedulerSetStatus",
    "ResultSuccess": true
}
...
```
