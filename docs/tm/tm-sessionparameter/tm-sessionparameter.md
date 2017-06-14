#tm sessionParameter

The following operations can be performed on "tm sessionParameter":


[set](#set-tm-sessionparameter) | [unset](#unset-tm-sessionparameter) | [show](#show-tm-sessionparameter)

##set tm sessionParameter

Sets global parameters for the traffic management (TM) session. Parameters defined when adding a traffic session action override these parameters.


##Synopsys

set tm sessionParameter [-sessTimeout &lt;mins>] [-defaultAuthorizationAction ( ALLOW | DENY )] [-SSO ( ON | OFF )] [-ssoCredential ( PRIMARY | SECONDARY )] [-ssoDomain &lt;string>] [-kcdAccount &lt;string>] [-httpOnlyCookie ( YES | NO )] [-persistentCookie ( ON | OFF )] [-persistentCookieValidity &lt;positive_integer>] [-homePage &lt;URL>]


##Arguments

<b>sessTimeout</b>
Session timeout, in minutes. If there is no traffic during the timeout period, the user is disconnected and must reauthenticate to access the intranet resources.
Default value: 30
Minimum value: 1

<b>defaultAuthorizationAction</b>
Allow or deny access to content for which there is no specific authorization policy.
Possible values: ALLOW, DENY
Default value: NS_ALLOW

<b>SSO</b>
Log users on to all web applications automatically after they authenticate, or pass users to the web application logon page to authenticate for each application.
Possible values: ON, OFF
Default value: OFF

<b>ssoCredential</b>
Use primary or secondary authentication credentials for single sign-on.
Possible values: PRIMARY, SECONDARY
Default value: VPN_SESS_ACT_USE_PRIMARY_CREDENTIALS

<b>ssoDomain</b>
Domain to use for single sign-on.

<b>kcdAccount</b>
Kerberos constrained delegation account name

<b>httpOnlyCookie</b>
Allow only an HTTP session cookie, in which case the cookie cannot be accessed by scripts.
Possible values: YES, NO
Default value: VPN_SESS_ACT_HTTPONLYCOOKIE_ALLOW

<b>persistentCookie</b>
Use persistent SSO cookies for the traffic session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends.
Possible values: ON, OFF
Default value: OFF

<b>persistentCookieValidity</b>
Integer specifying the number of minutes for which the persistent cookie remains valid. Can be set only if the persistence cookie setting is enabled.
Minimum value: 1

<b>homePage</b>
Web address of the home page that a user is displayed when authentication vserver is bookmarked and used to login.
Default value: "None"



##unset tm sessionParameter

Resets the attributes of the specified traffic session parameters. Attributes for which a default value is available revert to their default values. Refer to the set tm sessionParameter command for descriptions of the parameters..Refer to the set tm sessionParameter command for meanings of the arguments.


##Synopsys

unset tm sessionParameter [-sessTimeout] [-SSO] [-ssoDomain] [-kcdAccount] [-persistentCookie] [-homePage] [-defaultAuthorizationAction] [-ssoCredential] [-httpOnlyCookie] [-persistentCookieValidity]


##show tm sessionParameter

Displays information about traffic session parameters.


##Synopsys

show tm sessionParameter


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>name</b>

<b>sessTimeout</b>
The session timeout, in minutes.

<b>defaultAuthorizationAction</b>
The Authentication Action, e.g. allow or deny.

<b>SSO</b>
Whether or not Single Sign-On is used for this session.

<b>ssoCredential</b>
Use primary or secondary authentication credentials for single sign-on.

<b>ssoDomain</b>
Domain to use for single sign-on.

<b>kcdAccount</b>
Kerberos constrained delegation account name

<b>httpOnlyCookie</b>
Allow only an HTTP session cookie, in which case the cookie cannot be accessed by scripts.

<b>homePage</b>
Web address of the home page that a user is displayed when authentication vserver is bookmarked and used to login.

<b>persistentCookie</b>
Use persistent SSO cookies for the traffic session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends.

<b>persistentCookieValidity</b>
Integer specifying the number of minutes for which the persistent cookie remains valid. Can be set only if the persistence cookie setting is enabled.



