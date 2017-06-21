#authentication radiusAction

The following operations can be performed on "authentication radiusAction":


[add](#add-authentication-radiusaction) | [rm](#rm-authentication-radiusaction) | [set](#set-authentication-radiusaction) | [unset](#unset-authentication-radiusaction) | [show](#show-authentication-radiusaction)

##add authentication radiusAction

Creates an action (profile) for a RADIUS server. The profile contains all configuration data necessary to communicate with that RADIUS server.


##Synopsys

add authentication radiusAction &lt;name> {-serverIP &lt;ip_addr|ipv6_addr|*> | {-serverName &lt;string>}} [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-radKey } [-radNASip ( ENABLED | DISABLED )] [-radNASid &lt;string>] [-radVendorID &lt;positive_integer>] [-radAttributeType &lt;positive_integer>] [-radGroupsPrefix &lt;string>] [-radGroupSeparator &lt;string>] [-passEncoding &lt;passEncoding>] [-ipVendorID &lt;positive_integer>] [-ipAttributeType &lt;positive_integer>] [-accounting ( ON | OFF )] [-pwdVendorID &lt;positive_integer>  [-pwdAttributeType &lt;positive_integer>]] [-defaultAuthenticationGroup &lt;string>] [-callingstationid ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the RADIUS action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the RADIUS action is added.

<b>serverIP</b>
IP address assigned to the RADIUS server.

<b>serverName</b>
RADIUS server name as a FQDN.  Mutually exclusive with RADIUS IP address.

<b>serverPort</b>
Port number on which the RADIUS server listens for connections.
Minimum value: 1

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the RADIUS server.
Default value: 3
Minimum value: 1

<b>radKey</b>
Key shared between the RADIUS server and the NetScaler appliance. 
Required to allow the NetScaler appliance to communicate with the RADIUS server.

<b>radNASip</b>
If enabled, the NetScaler appliance IP address (NSIP) is sent to the RADIUS server as the  Network Access Server IP (NASIP) address. 
The RADIUS protocol defines the meaning and use of the NASIP address.
Possible values: ENABLED, DISABLED

<b>radNASid</b>
If configured, this string is sent to the RADIUS server as the Network Access Server ID (NASID).

<b>radVendorID</b>
RADIUS vendor ID attribute, used for RADIUS group extraction.
Minimum value: 1

<b>radAttributeType</b>
RADIUS attribute type, used for RADIUS group extraction.
Minimum value: 1

<b>radGroupsPrefix</b>
RADIUS groups prefix string. 
This groups prefix precedes the group names within a RADIUS attribute for RADIUS group extraction.

<b>radGroupSeparator</b>
RADIUS group separator string
The group separator delimits group names within a RADIUS attribute for RADIUS group extraction.

<b>passEncoding</b>
Encoding type for passwords in RADIUS packets that the NetScaler appliance sends to the RADIUS server.
Possible values: pap, chap, mschapv1, mschapv2
Default value: pap

<b>ipVendorID</b>
Vendor ID of the intranet IP attribute in the RADIUS response.
NOTE: A value of 0 indicates that the attribute is not vendor encoded.
Minimum value: 0

<b>ipAttributeType</b>
Remote IP address attribute type in a RADIUS response.
Minimum value: 1

<b>accounting</b>
Whether the RADIUS server is currently accepting accounting messages.
Possible values: ON, OFF

<b>pwdVendorID</b>
Vendor ID of the attribute, in the RADIUS response, used to extract the user password.
Minimum value: 1

<b>pwdAttributeType</b>
Vendor-specific password attribute type in a RADIUS response.
Minimum value: 1

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>callingstationid</b>
Send Calling-Station-ID of the client to the RADIUS server. IP Address of the client is sent as its Calling-Station-ID.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##rm authentication radiusAction

Removes a RADIUS profile (action). An action cannot be removed as long as it is bound to a policy.


##Synopsys

rm authentication radiusAction &lt;name>


##Arguments

<b>name</b>
Name of the action to be removed.



##set authentication radiusAction

Configures a RADIUS server profile (action). The profile contains all configuration data needed to communicate with that RADIUS server.


##Synopsys

set authentication radiusAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverName &lt;string>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-radKey } [-radNASip ( ENABLED | DISABLED )] [-radNASid &lt;string>] [-radVendorID &lt;positive_integer>] [-radAttributeType &lt;positive_integer>] [-radGroupsPrefix &lt;string>] [-radGroupSeparator &lt;string>] [-passEncoding &lt;passEncoding>] [-ipVendorID &lt;positive_integer>] [-ipAttributeType &lt;positive_integer>] [-accounting ( ON | OFF )] [-pwdVendorID &lt;positive_integer>] [-pwdAttributeType &lt;positive_integer>] [-defaultAuthenticationGroup &lt;string>] [-callingstationid ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the RADIUS profile.

<b>serverIP</b>
IP address assigned to the RADIUS server.

<b>serverName</b>
RADIUS server name as a FQDN.  Mutually exclusive with RADIUS IP address.

<b>serverPort</b>
Port number on which the RADIUS server listens for connections.
Minimum value: 1

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the RADIUS server.
Default value: 3
Minimum value: 1

<b>radKey</b>
Key shared between the RADIUS server and the NetScaler appliance. 
Required to allow the NetScaler appliance to communicate with the RADIUS server.

<b>radNASip</b>
If enabled, the NetScaler appliance IP address (NSIP) is sent to the RADIUS server as the  Network Access Server IP (NASIP) address. 
The RADIUS protocol defines the meaning and use of the NASIP address.
Possible values: ENABLED, DISABLED

<b>radNASid</b>
If configured, this string is sent to the RADIUS server as the Network Access Server ID (NASID).

<b>radVendorID</b>
RADIUS vendor ID attribute, used for RADIUS group extraction.
Minimum value: 1

<b>radAttributeType</b>
RADIUS attribute type, used for RADIUS group extraction.
Minimum value: 1

<b>radGroupsPrefix</b>
RADIUS groups prefix string. 
This groups prefix precedes the group names within a RADIUS attribute for RADIUS group extraction.

<b>radGroupSeparator</b>
RADIUS group separator string
The group separator delimits group names within a RADIUS attribute for RADIUS group extraction.

<b>passEncoding</b>
Encoding type for passwords in RADIUS packets that the NetScaler appliance sends to the RADIUS server.
Possible values: pap, chap, mschapv1, mschapv2
Default value: pap

<b>ipVendorID</b>
Vendor ID of the intranet IP attribute in the RADIUS response.
NOTE: A value of 0 indicates that the attribute is not vendor encoded.
Minimum value: 0

<b>ipAttributeType</b>
Remote IP address attribute type in a RADIUS response.
Minimum value: 1

<b>accounting</b>
Whether the RADIUS server is currently accepting accounting messages.
Possible values: ON, OFF

<b>pwdVendorID</b>
Vendor ID of the attribute, in the RADIUS response, used to extract the user password.
Minimum value: 1

<b>pwdAttributeType</b>
Vendor-specific password attribute type in a RADIUS response.
Minimum value: 1

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>callingstationid</b>
Send Calling-Station-ID of the client to the RADIUS server. IP Address of the client is sent as its Calling-Station-ID.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset authentication radiusAction

Use this command to remove authentication radiusAction settings.Refer to the set authentication radiusAction command for meanings of the arguments.


##Synopsys

unset authentication radiusAction &lt;name> [-serverPort] [-authTimeout] [-radNASip] [-radNASid] [-radVendorID] [-radAttributeType] [-radGroupsPrefix] [-radGroupSeparator] [-passEncoding] [-ipVendorID] [-ipAttributeType] [-accounting] [-pwdVendorID] [-pwdAttributeType] [-defaultAuthenticationGroup] [-callingstationid]


##show authentication radiusAction

Displays the current configuration settings for the specified RADIUS profile (action).


##Synopsys

show authentication radiusAction [&lt;name>]


##Arguments

<b>name</b>
Name of the RADIUS profile.



##Outputs

<b>serverIP</b>
IP address assigned to the RADIUS server.

<b>serverName</b>
RADIUS server name as a FQDN.  Mutually exclusive with RADIUS IP address.

<b>serverPort</b>
Port number on which the RADIUS server listens for connections.

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the RADIUS server.

<b>radKey</b>
Key shared between the RADIUS server and the NetScaler appliance. 
Required to allow the NetScaler appliance to communicate with the RADIUS server.

<b>radNASip</b>
If enabled, the NetScaler appliance IP address (NSIP) is sent to the RADIUS server as the  Network Access Server IP (NASIP) address. 
The RADIUS protocol defines the meaning and use of the NASIP address.

<b>IPAddress</b>
IP address.

<b>radNASid</b>
If configured, this string is sent to the RADIUS server as the Network Access Server ID (NASID).

<b>radVendorID</b>
RADIUS vendor ID attribute, used for RADIUS group extraction.

<b>radAttributeType</b>
RADIUS attribute type, used for RADIUS group extraction.

<b>radGroupsPrefix</b>
RADIUS groups prefix string. 
This groups prefix precedes the group names within a RADIUS attribute for RADIUS group extraction.

<b>radGroupSeparator</b>
RADIUS group separator string
The group separator delimits group names within a RADIUS attribute for RADIUS group extraction.

<b>passEncoding</b>
Encoding type for passwords in RADIUS packets that the NetScaler appliance sends to the RADIUS server.

<b>ipVendorID</b>
Vendor ID of the intranet IP attribute in the RADIUS response.
NOTE: A value of 0 indicates that the attribute is not vendor encoded.

<b>ipAttributeType</b>
Remote IP address attribute type in a RADIUS response.

<b>accounting</b>
Whether the RADIUS server is currently accepting accounting messages.

<b>Success</b>

<b>Failure</b>

<b>stateflag</b>

<b>pwdVendorID</b>
Vendor ID of the attribute, in the RADIUS response, used to extract the user password.

<b>pwdAttributeType</b>
Vendor-specific password attribute type in a RADIUS response.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>callingstationid</b>
Send Calling-Station-ID of the client to the RADIUS server. IP Address of the client is sent as its Calling-Station-ID.

<b>devno</b>

<b>count</b>



