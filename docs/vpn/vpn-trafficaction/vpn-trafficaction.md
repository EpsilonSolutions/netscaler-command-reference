#vpn trafficAction

The following operations can be performed on "vpn trafficAction":


[add](#add-vpn-trafficaction) | [rm](#rm-vpn-trafficaction) | [set](#set-vpn-trafficaction) | [unset](#unset-vpn-trafficaction) | [show](#show-vpn-trafficaction)

##add vpn trafficAction

Creates an action to be applied by a policy that matches the traffic being processed.


##Synopsys

add vpn trafficAction &lt;name> &lt;qual> [-appTimeout &lt;mins>] [(-SSO ( ON | OFF )  [-formSSOAction &lt;string>]) | -wanscaler ( ON | OFF )] [-fta ( ON | OFF )] [-kcdAccount &lt;string>] [-samlSSOProfile &lt;string>] [-proxy &lt;string>]


##Arguments

<b>name</b>
Name for the traffic action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after a traffic action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>qual</b>
Protocol, either HTTP or TCP, to be used with the action. If you specify TCP, single sign-on cannot be configured.
Possible values: http, tcp

<b>appTimeout</b>
Maximum amount of time, in minutes, a user can stay logged on to the web application.
Minimum value: 1
Maximum value: 715827

<b>SSO</b>
Provide single sign-on to the web application.
Possible values: ON, OFF

<b>formSSOAction</b>
Name of the form-based single sign-on profile. Form-based single sign-on allows users to log on one time to all protected applications in your network, instead of requiring them to log on separately to access each one.

<b>fta</b>
Specify file type association, which is a list of file extensions that users are allowed to open.
Possible values: ON, OFF

<b>wanscaler</b>
Use the Repeater Plug-in to optimize network traffic.
Possible values: ON, OFF

<b>kcdAccount</b>
Kerberos constrained delegation account name
Default value: "None"

<b>samlSSOProfile</b>
Profile to be used for doing SAML SSO to remote relying party

<b>proxy</b>
IP address and Port of the proxy server to be used for HTTP access for this request.



##rm vpn trafficAction

Removes a previously created traffic policy action.


##Synopsys

rm vpn trafficAction &lt;name>


##Arguments

<b>name</b>
Name of the traffic policy action to remove.



##set vpn trafficAction

Modifies a traffic policy action to be applied by the policy if the rule criteria are met.


##Synopsys

set vpn trafficAction &lt;name> [-appTimeout &lt;mins>] [-SSO ( ON | OFF ) | -wanscaler ( ON | OFF )] [-formSSOAction &lt;string>] [-fta ( ON | OFF )] [-kcdAccount &lt;string>] [-samlSSOProfile &lt;string>] [-proxy &lt;string>]


##Arguments

<b>name</b>
Name of the traffic policy action to modify.

<b>appTimeout</b>
Maximum amount of time, in minutes, a user can stay logged on to the web application.
Minimum value: 1
Maximum value: 715827

<b>SSO</b>
Provide single sign-on to the web application.
Possible values: ON, OFF

<b>formSSOAction</b>
Name of the form-based single sign-on profile. Form-based single sign-on allows users to log on one time to all protected applications in your network, instead of requiring them to log on separately to access each one.

<b>fta</b>
Specify file type association, which is a list of file extensions that users are allowed to open.
Possible values: ON, OFF

<b>wanscaler</b>
Use the Repeater Plug-in to optimize network traffic.
Possible values: ON, OFF

<b>kcdAccount</b>
Kerberos constrained delegation account name
Default value: "None"

<b>samlSSOProfile</b>
Profile to be used for doing SAML SSO to remote relying party

<b>proxy</b>
IP address and Port of the proxy server to be used for HTTP access for this request.



##unset vpn trafficAction

Use this command to remove vpn trafficAction settings.Refer to the set vpn trafficAction command for meanings of the arguments.


##Synopsys

unset vpn trafficAction &lt;name> [-wanscaler] [-kcdAccount] [-proxy]


##show vpn trafficAction

Displays information about all the configured traffic actions, or displays detailed information about the specified traffic action.


##Synopsys

show vpn trafficAction [&lt;name>]


##Arguments

<b>name</b>
Name of the traffic policy action for which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>qual</b>
The protocol that is set with the action; for example, http or tcp.

<b>appTimeout</b>
The application timeout

<b>SSO</b>
Whether or not Single Sign On is enabled.

<b>formSSOAction</b>
Name of the form-based single sign-on profile. Form-based single sign-on allows users to log on one time to all protected applications in your network, instead of requiring them to log on separately to access each one.

<b>fta</b>
Whether or not file-type association is enabled.

<b>wanscaler</b>
Use the Repeater Plug-in to optimize network traffic.

<b>kcdAccount</b>
Kerberos constrained delegation account name

<b>samlSSOProfile</b>
Profile to be used for doing SAML SSO to remote relying party

<b>proxy</b>
IP address and Port of the proxy server to be used for HTTP access for this request.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



