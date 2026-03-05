## PUT Append

**Description**:

Upload a new chunk of file in a workspace of the logged-in user. Сhunk size must be less than 90Kb and encoded in Base64-form.


**Url Structure**:

http://reports.stimulsoft.com/1/files/filekey


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. A custom heder x-sti-VersionKey contain the version key of previous chunk (obtained in the previous step). The filekey parameter in the URI is the key of file item and indicates the file whose data you want to upload. In POST-data must specify the JSON-object describing the resources data with only one field. Data must be Base64-encoded:


**POST-data in the JSON-object**

```
...
{
    'Resource': 'IGFwcGVuZGVkIHN0cmluZw=='
}
... 
```

**CURL example**:

curl -X PUT -H "x-sti-SessionKey: 2aa74b48f7c542b9a17cbcfa5d43122d" -H "x-sti-VersionKey: 74cc142d844a496797d78b7e34b49687" -d "{'Resource': 'IGFwcGVuZGVkIHN0cmluZw=='}" http://reports.stimulsoft.com/1/files/bad8820fd26e4ab7b04dcc5afa932148


**Returns**:

The JSON object containing the collection ResultCommands which contain once item with field ResultVersionKey. Value of this field need to upload next chunk. Data will be added to the end of file.


**Sample JSON response**

```
...
{
    "Ident": "CommandListRun",
    "ResultCommands": [
    {
        "Ident": "ItemResourceSave",
        "ResultVersionKey": "74cc142d844a496797d78b7e34b49687",
        "ResultSuccess": true
    }
    ],
    "ResultSuccess": true
}
...
```
