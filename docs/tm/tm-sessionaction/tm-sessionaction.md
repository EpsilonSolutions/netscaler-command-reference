#tm sessionAction

The following operations can be performed on "tm sessionAction":


[add](#add-tm-sessionaction) | [rm](#rm-tm-sessionaction) | [set](#set-tm-sessionaction) | [unset](#unset-tm-sessionaction) | [show](#show-tm-sessionaction)

##add tm sessionAction

Creates a session action (profile) that allows you to override global settings for any of the session parameters.


##Synopsys

add tm sessionAction &lt;name> [-sessTimeout &lt;mins>] [-defaultAuthorizationAction ( ALLOW | DENY )] [-SSO ( ON | OFF )] [-ssoCredential ( PRIMARY | SECONDARY )] [-ssoDomain &lt;string>] [-httpOnlyCookie ( YES | NO )] [-kcdAccount &lt;string>] [-persistentCookie ( ON | OFF )] [-persistentCookieValidity &lt;mins>] [-homePage &lt;URL>]


##Arguments

<b>name</b>
Name for the session action. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after a session action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>sessTimeout</b>
Session timeout, in minutes. If there is no traffic during the timeout period, the user is disconnected and must reauthenticate to access intranet resources.
Minimum value: 1

<b>defaultAuthorizationAction</b>
Allow or deny access to content for which there is no specific authorization policy.
Possible values: ALLOW, DENY

<b>SSO</b>
Use single sign-on (SSO) to log users on to all web applications automatically after they authenticate, or pass users to the web application logon page to authenticate to each application individually.
Possible values: ON, OFF
Default value: OFF

<b>ssoCredential</b>
Use the primary or secondary authentication credentials for single sign-on (SSO).
Possible values: PRIMARY, SECONDARY

<b>ssoDomain</b>
Domain to use for single sign-on (SSO).

<b>httpOnlyCookie</b>
Allow only an HTTP session cookie, in which case the cookie cannot be accessed by scripts.
Possible values: YES, NO

<b>kcdAccount</b>
Kerberos constrained delegation account name

<b>persistentCookie</b>
Enable or disable persistent SSO cookies for the traffic management (TM) session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends. This setting is overwritten if a traffic action sets persistent cookie to OFF. 
Note: If persistent cookie is enabled, make sure you set the persistent cookie validity.
Possible values: ON, OFF

<b>persistentCookieValidity</b>
Integer specifying the number of minutes for which the persistent cookie remains valid. Can be set only if the persistent cookie setting is enabled.
Minimum value: 1

<b>homePage</b>
Web address of the home page that a user is displayed when authentication vserver is bookmarked and used to login.



##rm tm sessionAction

Deletes an existing session action.


##Synopsys

rm tm sessionAction &lt;name>


##Arguments

<b>name</b>
Name of the session action to delete.



##set tm sessionAction

Modifies the specified parameters of an existing session action.


##Synopsys

set tm sessionAction &lt;name> [-sessTimeout &lt;mins>] [-defaultAuthorizationAction ( ALLOW | DENY )] [-SSO ( ON | OFF )] [-ssoCredential ( PRIMARY | SECONDARY )] [-ssoDomain &lt;string>] [-kcdAccount &lt;string>] [-httpOnlyCookie ( YES | NO )] [-persistentCookie ( ON | OFF )] [-persistentCookieValidity &lt;positive_integer>] [-homePage &lt;URL>]


##Arguments

<b>name</b>
Name of the session action to modify.

<b>sessTimeout</b>
Session timeout, in minutes. If there is no traffic during the timeout period, the user is disconnected and must reauthenticate to access intranet resources.
Minimum value: 1

<b>defaultAuthorizationAction</b>
Allow or deny access to content for which there is no specific authorization policy.
Possible values: ALLOW, DENY

<b>SSO</b>
Use single sign-on (SSO) to log users on to all web applications automatically after they authenticate, or pass users to the web application logon page to authenticate to each application individually.
Possible values: ON, OFF
Default value: OFF

<b>ssoCredential</b>
Use the primary or secondary authentication credentials for single sign-on (SSO).
Possible values: PRIMARY, SECONDARY

<b>ssoDomain</b>
Domain to use for single sign-on (SSO).

<b>kcdAccount</b>
Kerberos constrained delegation account name

<b>httpOnlyCookie</b>
Allow only an HTTP session cookie, in which case the cookie cannot be accessed by scripts.
Possible values: YES, NO

<b>persistentCookie</b>
Enable or disable persistent SSO cookies for the traffic management (TM) session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends. This setting is overwritten if a traffic action sets persistent cookie to OFF. 
Note: If persistent cookie is enabled, make sure you set the persistent cookie validity.
Possible values: ON, OFF

<b>persistentCookieValidity</b>
Integer specifying the number of minutes for which the persistent cookie remains valid. Can be set only if the persistent cookie setting is enabled.
Minimum value: 1

<b>homePage</b>
Web address of the home page that a user is displayed when authentication vserver is bookmarked and used to login.



##unset tm sessionAction

Use this command to remove tm sessionAction settings.Refer to the set tm sessionAction command for meanings of the arguments.


##Synopsys

unset tm sessionAction &lt;name> [-sessTimeout] [-defaultAuthorizationAction] [-SSO] [-ssoCredential] [-ssoDomain] [-kcdAccount] [-httpOnlyCookie] [-persistentCookie] [-persistentCookieValidity] [-homePage]


##show tm sessionAction

Displays information about all configured traffic management (TM) session actions, or detailed information about the specified TM session action.


##Synopsys

show tm sessionAction [&lt;name>]


##Arguments

<b>name</b>
Name of the existing traffic management (TM) session action for which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>sessTimeout</b>
The session timeout, in minutes, set by the action.

<b>defaultAuthorizationAction</b>
The Authorization Action, e.g. allow or deny

<b>stateflag</b>

<b>SSO</b>
Whether or not Single Sign-On is used for this session.

<b>ssoCredential</b>
Use the primary or secondary authentication credentials for single sign-on (SSO).

<b>ssoDomain</b>
Domain to use for single sign-on (SSO).

<b>kcdAccount</b>
Kerberos constrained delegation account name

<b>httpOnlyCookie</b>
Allow only an HTTP session cookie, in which case the cookie cannot be accessed by scripts.

<b>persistentCookie</b>
Enable or disable persistent SSO cookies for the traffic management (TM) session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends. This setting is overwritten if a traffic action sets persistent cookie to OFF. 
Note: If persistent cookie is enabled, make sure you set the persistent cookie validity.

<b>persistentCookieValidity</b>
Integer specifying the number of minutes for which the persistent cookie remains valid. Can be set only if the persistent cookie setting is enabled.

<b>homePage</b>
Web address of the home page that a user is displayed when authentication vserver is bookmarked and used to login.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>



