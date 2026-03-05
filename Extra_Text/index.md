## Extra_Text

**REST_API.USERS.Reset password**


**Description**:

Initialization of reset password. To the address of the user (specified in his profile) sent an email with a link to reset your password containing a secret code.


**E-mail sample**:


![](../images/topics/Extra_Text_1.png)


**Url Structure**:

http://cloud.stimulsoft.com/1/users/username/resetpassword


**Method**:

PUT


**Parameters**:

A custom header x-sti-SessionKey contains the session key of the current user. The username parameter in the URI is the key user or its name and indicates the user whose data you want to get. Instead of the user name or key, you can specify the keyword "current" which replaces the identifier of the current user.


**CURL example**:

curl -X PUT -H "x-sti-SessionKey: ea8cc765d54241e18347a043e187ada3" -d "" http://cloud.stimulsoft.com/1/users/j@d.com/resetpassword


**Returns**:

The JSON object containing the field ResultSuccess which indicates that the command is executed successfully.


Sample **JSON** response:


```
...
{
  "Ident": "UserResetPassword",
  "ResultSuccess": true
}
...
```
