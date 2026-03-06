# REST API

REST API allows you quick and easy access to the main functions of **Stimulsoft Cloud** and automates user actions of the system in your application. Access points to the REST-services should be on your domain and be accessible via HTTP/HTTPS. For example, we will use the online version of Stimulsoft Cloud with the URL [https://cloud.stimulsoft.com](https://reports.stimulsoft.com). A relative path begins with the prefix /1/ which means the first version of REST API.


| **EndPoint** | **HTTP Verb** | **Action** |
| --- | --- | --- |
| /1/login | GET | [Login registered user](Login.md) |
| /1/logout | DELETE | [User logout](Logout.md) |
| /1/signup | POST | [New user registration](SignUp.md) |
| /1/users | GET | [Getting a list of users](Users/Get_List.md) |
| /1/users | POST | [Creating a new user](Users/Post_Create.md) |
| /1/users/&lt;UserId&gt; | GET | [Getting information about the user <UserId>](Users/Get_Info.md) |
| /1/users/&lt;UserId&gt; | PUT | [Changing user information <UserId>](Users/Put_Edit.md) |
| /1/users/&lt;UserId&gt; | DELETE | [Removing a user <UserId>](Users/Delete.md) |
| /1/users/current | GET | [Getting information about the current user](Users/Get_Info.md) |
| /1/users/current | PUT | [Changing the current user information](Users/Put_Edit.md) |
| /1/users/&lt;UserId&gt;/changepassword | PUT | [Change user password](Users/Change_password.md) |
| /1/users/current/changepassword | PUT | [Changing the password of the current user](Users/Change_password.md) |
| /1/users/&lt;UserId&gt;/resetpassword | PUT | [Initialize reset the user's <UserId>  password](Users/Reset_password.md) |
| /1/users/current/resetpassword | PUT | [Initialize the current user password reset](Users/Reset_password.md) |
| /1/resetpassword/secretcode | PUT | [Confirm password reset by a secret code](Users/Reset_password.md) |
| /1/items | GET | [Getting a list of items](Items/Get_List.md) |
| /1/items/&lt;ItemId&gt; | GET | [Getting information about the element <ItemId>](Items/GET_Info.md) |
| /1/items | POST | [Create a new item](Items/POST_Create.md) |
| /1/items/&lt;ItemId&gt; | PUT | [Changing information about the element <ItemId>](Items/PUT_Edit.md) |
| /1/items/&lt;ItemId&gt; | DELETE | [Deleting an element <ItemId>](Items/DELETE.md) |
| /1/items/&lt;ItemId&gt;/share | GET | [Getting information about public access to the element <ItemId>](Items/Share/GET_Info.md) |
| /1/items/&lt;ItemId&gt;/share | PUT | [Changing data on public access to the element <ItemId>](Items/Share/PUT_Edit.md) |
| /1/items/&lt;ItemId&gt;/share | DELETE | [Removing an element <ItemId> from public access](Items/Share/DELETE_Reset.md) |
| /1/reporttemplates | GET | [Getting a list of report templates](Report_Template/GET_List.md) |
| /1/reporttemplates/&lt;ReportTemplateId&gt;/ | GET | [Getting information about the report template <ReportTemplateId>](Report_Template/GET_Info.md) |
| /1/reporttemplates | POST | [Creating a new report template](Report_Template/POST_Create.md) |
| /1/reporttemplates/&lt;ReportTemplateId&gt;/ | DELETE | [Removing a report template <ReportTemplateId>](Report_Template/DELETE.md) |
| /1/reporttemplates/&lt;ReportTemplateId&gt;/duplicate | POST | [Creating a new copy of the report template in a cloud of the logged-in user.](Report_Template/POST_Duplicate.md) |
