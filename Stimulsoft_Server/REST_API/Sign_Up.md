# Sign Up

**Description**:

Create a new user (in new workspace)


**Url Structure**:

http://reports.stimulsoft.com/1/signup


**Method**:

POST


**Parameters**:

In POST-data must specify the JSON-object describing a new user:


**POST-data in the JSON-object**

```
...
{
    'FirstName': 'John',
    'LastName': 'Doe',
    'UserName': 'j@d.com',
    'Password': '111111'
}
...
```

**CURL example**:

curl -X POST -d "{ 'FirstName': 'John', 'LastName': 'Doe', 'UserName': 'j@d.com', 'Password': '111111' }" http://reports.stimulsoft.com/1/signup


**Returns**:

The JSON object containing the field ResultUserKey with the key of the new user. The success of the command execution is checked by the content of the field ResultSuccess.


**Sample JSON response**

```
...
{
    "Ident": "UserSignUp",
    "ResultUserKey": "ddb025415b68494ca8a9aee27ad73bc1",
    "ResultSuccess": true
}
...
```
