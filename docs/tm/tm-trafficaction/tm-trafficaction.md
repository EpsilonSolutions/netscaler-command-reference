#tm trafficAction

The following operations can be performed on "tm trafficAction":


[add](#add-tm-trafficaction) | [rm](#rm-tm-trafficaction) | [set](#set-tm-trafficaction) | [unset](#unset-tm-trafficaction) | [show](#show-tm-trafficaction)

##add tm trafficAction

Creates a traffic action to set traffic characteristics at run time. You can create a traffic action for an application that is installed in the internal network (for example, an action that defines the destination IP address and destination port, and sets the amount of time a user can stay logged on to the application, such as 15 minutes).


##Synopsys

add tm trafficAction &lt;name> [-appTimeout &lt;mins>] [-SSO ( ON | OFF )  [-formSSOAction &lt;string>]] [-persistentCookie ( ON | OFF )] [-InitiateLogout ( ON | OFF )] [-kcdAccount &lt;string>] [-samlSSOProfile &lt;string>] [-forcedTimeout &lt;forcedTimeout>  -forcedTimeoutVal &lt;mins> ] [-userExpression &lt;string>] [-passwdExpression &lt;string>]


##Arguments

<b>name</b>
Name for the traffic action. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after a traffic action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>appTimeout</b>
Time interval, in minutes, of user inactivity after which the connection is closed.
Minimum value: 1
Maximum value: 715827

<b>SSO</b>
Use single sign-on for the resource that the user is accessing now.
Possible values: ON, OFF

<b>formSSOAction</b>
Name of the configured form-based single sign-on profile.

<b>persistentCookie</b>
Use persistent cookies for the traffic session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends.
Possible values: ON, OFF

<b>InitiateLogout</b>
Initiate logout for the traffic management (TM) session if the policy evaluates to true. The session is then terminated after two minutes.
Possible values: ON, OFF

<b>kcdAccount</b>
Kerberos constrained delegation account name
Default value: "None"

<b>samlSSOProfile</b>
Profile to be used for doing SAML SSO to remote relying party

<b>forcedTimeout</b>
Setting to start, stop or reset TM session force timer
Possible values: START, STOP, RESET

<b>forcedTimeoutVal</b>
Time interval, in minutes, for which force timer should be set.

<b>userExpression</b>
expression that will be evaluated to obtain username for SingleSignOn
Maximum value: 256

<b>passwdExpression</b>
expression that will be evaluated to obtain password for SingleSignOn
Maximum value: 256



##rm tm trafficAction

Removes an existing traffic action.


##Synopsys

rm tm trafficAction &lt;name>


##Arguments

<b>name</b>
Name of the traffic action to remove.



##set tm trafficAction

Modifies the specified parameters of an existing traffic action.


##Synopsys

set tm trafficAction &lt;name> [-appTimeout &lt;mins>] [-SSO ( ON | OFF )] [-formSSOAction &lt;string>] [-persistentCookie ( ON | OFF )] [-InitiateLogout ( ON | OFF )] [-kcdAccount &lt;string>] [-samlSSOProfile &lt;string>] [-forcedTimeout &lt;forcedTimeout>] [-forcedTimeoutVal &lt;mins>] [-userExpression &lt;string>] [-passwdExpression &lt;string>]


##Arguments

<b>name</b>
Name of the traffic action to modify.

<b>appTimeout</b>
Time interval, in minutes, of user inactivity after which the connection is closed.
Minimum value: 1
Maximum value: 715827

<b>SSO</b>
Use single sign-on for the resource that the user is accessing now.
Possible values: ON, OFF

<b>formSSOAction</b>
Name of the configured form-based single sign-on profile.

<b>persistentCookie</b>
Use persistent cookies for the traffic session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends.
Possible values: ON, OFF

<b>InitiateLogout</b>
Initiate logout for the traffic management (TM) session if the policy evaluates to true. The session is then terminated after two minutes.
Possible values: ON, OFF

<b>kcdAccount</b>
Kerberos contrained delegation account name
Default value: "None"

<b>samlSSOProfile</b>
Profile to be used for doing SAML SSO to remote relying party

<b>forcedTimeout</b>
Setting to start, stop or reset TM session force timer
Possible values: START, STOP, RESET

<b>forcedTimeoutVal</b>
Time interval, in minutes, for which force timer should be set.

<b>userExpression</b>
expression that will be evaluated to obtain username for SingleSignOn
Maximum value: 256

<b>passwdExpression</b>
expression that will be evaluated to obtain password for SingleSignOn
Maximum value: 256



##unset tm trafficAction

Use this command to remove tm trafficAction settings.Refer to the set tm trafficAction command for meanings of the arguments.


##Synopsys

unset tm trafficAction &lt;name> [-persistentCookie] [-kcdAccount] [-forcedTimeout] [-userExpression] [-passwdExpression]


##show tm trafficAction

Displays information about all configured traffic management (TM) traffic actions, or displays detailed information about the specified TM traffic action.


##Synopsys

show tm trafficAction [&lt;name>]


##Arguments

<b>name</b>
Name of the traffic action for which to display detailed information.



##Outputs

<b>appTimeout</b>
The application timeout

<b>SSO</b>
Whether or not Single Sign On is enabled.

<b>formSSOAction</b>
Name of the configured form-based single sign-on profile.

<b>stateflag</b>

<b>persistentCookie</b>
Use persistent cookies for the traffic session. A persistent cookie remains on the user device and is sent with each HTTP request. The cookie becomes stale if the session ends.

<b>InitiateLogout</b>
Whether Logout is initiated with this action

<b>kcdAccount</b>
Kerberos contrained delegation account name

<b>samlSSOProfile</b>
Profile to be used for doing SAML SSO to remote relying party

<b>forcedTimeout</b>
Setting to start, stop or reset TM session force timer

<b>forcedTimeoutVal</b>
Time interval, in minutes, for which force timer should be set.

<b>userExpression</b>
expression that will be evaluated to obtain username for SingleSignOn

<b>passwdExpression</b>
expression that will be evaluated to obtain password for SingleSignOn

<b>devno</b>

<b>count</b>



