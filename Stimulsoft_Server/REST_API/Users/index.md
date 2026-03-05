# Users

For obtaining the list of users, data modification, as well as to create new users in the current workspace and delete users, use the command Users with different methods.


**Name**

**Description**

[GET List](GET_List.md)

Getting a list of users in a workspace of the logged-in user.

[GET Info](GET_Info.md)

Getting information about the user in a workspace of the logged-in user.

**POST Create**

Creating a new user in a workspace of the logged-in user.

**PUT Edit**

Changing user data in a workspace of the logged-in user. This command does not allow change of the unique user name, which is used as an identifier, and a password - for this purpose there is other command.

**DELETE**

Removing a user from the current workspace. Removing a last user with administrator privileges isn't allowed.

Managing user passwords requires a special approach to security, so to change and reset the password using a number of separate commands. Changing the password requires an existing password. Reset password occurs in two stages - a password reset request and execution of the procedure. Password reset request executed with the command resetpassword, at the same time to the email address specified in the user data sent to e-mail with a link, activating the second stage - the actual password reset. To activate the second stage through REST-interface, you must run command resetpassword with the indication a secret one-time code (specified in the link sent in an email message), valid for two hours. Next to the postal address of the user sent another message indicating a new password:


**Name**

**Description**

**Change password**

Change user password.

**Reset password**

Activating of password reset. At this stage, checked the security code, and if it is correct, the password is reset to the new specified in the parameters. To activate the procedure requires new password and the secret code obtained at the first stage. Executing this command does not require a session key.
