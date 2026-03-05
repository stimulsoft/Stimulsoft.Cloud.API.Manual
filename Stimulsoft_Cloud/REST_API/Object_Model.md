# Object Model

The input data for each command are custom HTTP-headers prefixed with "x-sti-" and described in the table below:


**Custom header**

**Description**

x-sti-sessionkey

The current session key is issued after successful authentication, used in almost all commands

x-sti-versionkey

Key of the last chunk of the uploaded file

x-sti-username

Username for authentication

x-sti-password

Password to login

x-sti-newpassword

The new user's password, used to change the password and reset password

x-sti-currentpassword

User's current password, used to change the password

x-sti-index

Index of the element to which you want to fetch, used to limit the data fetch

x-sti-count

Number of items that need to get, used to limit the data fetch

x-sti-allowdeleted

Determines whether the elements in the fetch display deleted, default is false

x-sti-itemkey

The key of element, which is the work, used to limit the data fetch

x-sti-filterident

Filtering of the elements by identifiers, used to limit the data fetch

x-sti-status

Task scheduler status, used to manage the schedulers

x-sti-allowmovetorecyclebin

Allows deleting an item to the recycle bin, by default it is set to true

x-sti-destinationitemkey

Allows indicates an item that will be stored data

Other information transmitted in the body of the request in the JSON format. Permitted to transfer the input parameters in the request body as a simple JSON-object with fields whose names match the custom headers, but lack the prefix “x-sti-“. Parameter names are not case sensitive, regardless of how they transfer (custom headers or POST-data). As the output data is used JSON-object for all commands. Even in the case of error or successful completion of an object returned, indicating success of query processing server.

Error example:


**Sample JSON response**

```
...
{
    "Ident": "UserFetchAll",
    "ResultNotice": {
        "Ident": "IsNotSpecified",
        "Arguments": [
        "SessionKey"
        ]
    }
}
...
```

Another error example:


**Sample JSON response**

```
...
{
    "Ident": "UserSave",
    "ResultNotice": {
        "Ident": "AccessDenied",
        "CustomMessage": "You should specify the CurrentPassword argument when you want to change the user password!"
    }
}
...
```

Example of successful command execution, not returning data:


**Sample JSON response**

```
...
{
    "Ident": "UserLogout",
    "ResultSuccess": true
}
...
```

Obviously, if the command does not return HTTP error and successfully passed the server to perform, any response with JSON-object will have an HTTP-status "200 OK". In this case, success of command execution needs to be checked on a condition of the field ResultSuccess and availability of data in the field ResultNotice. If ResultNotice field is not empty, then the command has problems that are described nested object contained in this field.
