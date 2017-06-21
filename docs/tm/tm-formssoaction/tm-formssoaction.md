#tm formSSOAction

The following operations can be performed on "tm formSSOAction":


[add](#add-tm-formssoaction) | [rm](#rm-tm-formssoaction) | [set](#set-tm-formssoaction) | [unset](#unset-tm-formssoaction) | [show](#show-tm-formssoaction)

##add tm formSSOAction

Creates a form-based single sign-on traffic profile (action.) Form-based single sign-on allows users to access web applications that require an HTML form-based logon without having to type their password again for each new application.


##Synopsys

add tm formSSOAction &lt;name> -actionURL &lt;URL> -userField &lt;string> -passwdField &lt;string> -ssoSuccessRule &lt;expression> [-nameValuePair &lt;string>] [-responsesize &lt;positive_integer>] [-nvtype ( STATIC | DYNAMIC )] [-submitMethod ( GET | POST )]


##Arguments

<b>name</b>
Name for the new form-based single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>actionURL</b>
URL to which the completed form is submitted.

<b>userField</b>
Name of the form field in which the user types in the user ID.

<b>passwdField</b>
Name of the form field in which the user types in the password.

<b>ssoSuccessRule</b>
Expression, that checks to see if single sign-on is successful.

<b>nameValuePair</b>
Name-value pair attributes to send to the server in addition to sending the username and password. Value names are separated by an ampersand (&) (for example, name1=value1=value2).

<b>responsesize</b>
Number of bytes, in the response, to parse for extracting the forms.
Default value: 8096
Minimum value: 0

<b>nvtype</b>
Type of processing of the name-value pair. If you specify STATIC, the values configured by the administrator are used. For DYNAMIC, the response is parsed, and the form is extracted and then submitted.
Possible values: STATIC, DYNAMIC
Default value: DYNAMIC

<b>submitMethod</b>
HTTP method used by the single sign-on form to send the logon credentials to the logon server. Applies only to STATIC name-value type.
Possible values: GET, POST
Default value: GET



##rm tm formSSOAction

Deletes an existing form-based single sign-on traffic profile (action.)


##Synopsys

rm tm formSSOAction &lt;name>


##Arguments

<b>name</b>
Name of the form-based single sign-on profile to delete.



##set tm formSSOAction

Modifies the specified attributes of a form-based single sign-on traffic profile (action.)


##Synopsys

set tm formSSOAction &lt;name> [-actionURL &lt;URL>] [-userField &lt;string>] [-passwdField &lt;string>] [-ssoSuccessRule &lt;expression>] [-responsesize &lt;positive_integer>] [-nameValuePair &lt;string>] [-nvtype ( STATIC | DYNAMIC )] [-submitMethod ( GET | POST )]


##Arguments

<b>name</b>
Name of the form-based single sign-on profile (action) to modify.

<b>actionURL</b>
URL to which the completed form is submitted.

<b>userField</b>
Name of the form field in which the user types in the user ID.

<b>passwdField</b>
Name of the form field in which the user types in the password.

<b>ssoSuccessRule</b>
Expression, that checks to see if single sign-on is successful.

<b>responsesize</b>
Number of bytes, in the response, to parse for extracting the forms.
Default value: 8096
Minimum value: 0

<b>nameValuePair</b>
Name-value pair attributes to send to the server in addition to sending the username and password. Value names are separated by an ampersand (&) (for example, name1=value1=value2).

<b>nvtype</b>
Type of processing of the name-value pair. If you specify STATIC, the values configured by the administrator are used. For DYNAMIC, the response is parsed, and the form is extracted and then submitted.
Possible values: STATIC, DYNAMIC
Default value: DYNAMIC

<b>submitMethod</b>
HTTP method used by the single sign-on form to send the logon credentials to the logon server. Applies only to STATIC name-value type.
Possible values: GET, POST
Default value: GET



##unset tm formSSOAction

Use this command to remove tm formSSOAction settings.Refer to the set tm formSSOAction command for meanings of the arguments.


##Synopsys

unset tm formSSOAction &lt;name> [-responsesize] [-nameValuePair] [-nvtype] [-submitMethod]


##show tm formSSOAction

Displays information about all configured form-based single sign-on actions, or displays detailed information about the specified action.


##Synopsys

show tm formSSOAction [&lt;name>]


##Arguments

<b>name</b>
Name of the SSO action for which to display detailed information.



##Outputs

<b>actionURL</b>
URL to which the completed form is submitted.

<b>userField</b>
Username field.

<b>passwdField</b>
Password field.

<b>responsesize</b>
Number of bytes, in the response, to parse for extracting the forms.

<b>nameValuePair</b>
Form attributes and their values to be submitted.

<b>nvtype</b>
Bypass Form extraction

<b>ssoSuccessRule</b>
Rule to be evaluated to check whether sso succeeded or not.

<b>submitMethod</b>
Form Submit method.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



