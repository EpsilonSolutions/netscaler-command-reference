#vpn formSSOAction

The following operations can be performed on "vpn formSSOAction":


[add](#add-vpn-formssoaction) | [rm](#rm-vpn-formssoaction) | [set](#set-vpn-formssoaction) | [unset](#unset-vpn-formssoaction) | [show](#show-vpn-formssoaction)

##add vpn formSSOAction

Creates a form-based single sign-on profile. Form based single sign-on allows users to log on one time to all protected applications in your network. Users can access web applications that require an HTML form-based logon without having to type their password again.


##Synopsys

add vpn formSSOAction &lt;name> -actionURL &lt;URL> -userField &lt;string> -passwdField &lt;string> -ssoSuccessRule &lt;expression> [-nameValuePair &lt;string>] [-responsesize &lt;positive_integer>] [-nvtype ( STATIC | DYNAMIC )] [-submitMethod ( GET | POST )]


##Arguments

<b>name</b>
Name for the form based single sign-on profile.

<b>actionURL</b>
Root-relative URL to which the completed form is submitted.

<b>userField</b>
Name of the form field in which the user types in the user ID.

<b>passwdField</b>
Name of the form field in which the user types in the password.

<b>ssoSuccessRule</b>
Use a frequently used expression or create a custom expression describing the action that the form-based single sign-on profile takes when invoked by a policy. Used for verifying successful single sign-on.

<b>nameValuePair</b>
Other name-value pair attributes to send to the server, in addition to sending the user name and password. Value names are separated by an ampersand (&), such as in name1=value1=value2.

<b>responsesize</b>
Maximum number of bytes to allow in the response size. Specifies the number of bytes in the response to be parsed for extracting the forms.
Default value: 8096

<b>nvtype</b>
How to process the name-value pair. Available settings function as follows:
* STATIC - The administrator-configured values are used.
* DYNAMIC - The response is parsed, the form is extracted, and then submitted.
Possible values: STATIC, DYNAMIC
Default value: NS_ACT_FSSO_NV_DYNAMIC

<b>submitMethod</b>
HTTP method (GET or POST) used by the single sign-on form to send the logon credentials to the logon server.
Possible values: GET, POST
Default value: NS_ACT_FSSO_SUBMIT_GET



##rm vpn formSSOAction

Removes a configured form-based single sign-on profile.


##Synopsys

rm vpn formSSOAction &lt;name>


##Arguments

<b>name</b>
Name of the form-based single sign-on profile to remove.



##set vpn formSSOAction

Modifies the parameters of an existing form-based single sign-on profile (or action).


##Synopsys

set vpn formSSOAction &lt;name> [-actionURL &lt;URL>] [-userField &lt;string>] [-passwdField &lt;string>] [-ssoSuccessRule &lt;expression>] [-responsesize &lt;positive_integer>] [-nameValuePair &lt;string>] [-nvtype ( STATIC | DYNAMIC )] [-submitMethod ( GET | POST )]


##Arguments

<b>name</b>
Name for the form based single sign-on profile.

<b>actionURL</b>
Root-relative URL to which the completed form is submitted.

<b>userField</b>
Name of the form field in which the user types in the user ID.

<b>passwdField</b>
Name of the form field in which the user types in the password.

<b>ssoSuccessRule</b>
Use a frequently used expression or create a custom expression describing the action that the form-based single sign-on profile takes when invoked by a policy. Used for verifying successful single sign-on.

<b>responsesize</b>
Maximum number of bytes to allow in the response size. Specifies the number of bytes in the response to be parsed for extracting the forms.
Default value: 8096

<b>nameValuePair</b>
Other name-value pair attributes to send to the server, in addition to sending the user name and password. Value names are separated by an ampersand (&), such as in name1=value1=value2.

<b>nvtype</b>
How to process the name-value pair. Available settings function as follows:
* STATIC - The administrator-configured values are used.
* DYNAMIC - The response is parsed, the form is extracted, and then submitted.
Possible values: STATIC, DYNAMIC
Default value: NS_ACT_FSSO_NV_DYNAMIC

<b>submitMethod</b>
HTTP method (GET or POST) used by the single sign-on form to send the logon credentials to the logon server.
Possible values: GET, POST
Default value: NS_ACT_FSSO_SUBMIT_GET



##unset vpn formSSOAction

Use this command to remove vpn formSSOAction settings.Refer to the set vpn formSSOAction command for meanings of the arguments.


##Synopsys

unset vpn formSSOAction &lt;name> [-responsesize] [-nameValuePair] [-nvtype] [-submitMethod]


##show vpn formSSOAction

Displays the attributes of a form-based single sign-on profile.


##Synopsys

show vpn formSSOAction [&lt;name>]


##Arguments

<b>name</b>
Name of the form-based single sign-on profile.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>actionURL</b>
Root-relative URL to which the completed form is submitted.

<b>userField</b>
Username field.

<b>passwdField</b>
Password field.

<b>responsesize</b>
Maximum number of bytes to allow in the response size. Specifies the number of bytes in the response to be parsed for extracting the forms.

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



