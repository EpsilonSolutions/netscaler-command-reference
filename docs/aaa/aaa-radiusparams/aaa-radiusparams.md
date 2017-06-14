#aaa radiusParams

The following operations can be performed on "aaa radiusParams":


[set](#set-aaa-radiusparams) | [unset](#unset-aaa-radiusparams) | [show](#show-aaa-radiusparams)

##set aaa radiusParams

Modifies the global configuration settings for the RADIUS server. The settings that you specify are used for all SSL-VPN virtual servers unless you use authentication policies to create a configuration for a specific SSL-VPN virtual server.


##Synopsys

set aaa radiusParams [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-radKey } [-radNASip ( ENABLED | DISABLED )] [-radNASid &lt;string>] [-radVendorID &lt;positive_integer>] [-radAttributeType &lt;positive_integer>] [-radGroupsPrefix &lt;string>] [-radGroupSeparator &lt;string>] [-passEncoding &lt;passEncoding>] [-ipVendorID &lt;positive_integer>] [-ipAttributeType &lt;positive_integer>] [-accounting ( ON | OFF )] [-pwdVendorID &lt;positive_integer>] [-pwdAttributeType &lt;positive_integer>] [-defaultAuthenticationGroup &lt;string>] [-callingstationid ( ENABLED | DISABLED )]


##Arguments

<b>serverIP</b>
IP address of your RADIUS server.

<b>serverPort</b>
Port number on which the RADIUS server listens for connections. Default value: 1812 Minimum value: 1

<b>authTimeout</b>
Maximum number of seconds that the NetScaler appliance waits for a response from the RADIUS server. Default value: 3 Minimum value: 1

<b>radKey</b>
The key shared between the RADIUS server and clients. Required for allowing the NetScaler appliance to communicate with the RADIUS server.

<b>radNASip</b>
Send the NetScaler IP (NSIP) address to the RADIUS server as the Network Access Server IP (NASIP) part of the Radius protocol. Possible values: ENABLED, DISABLED

<b>radNASid</b>
Send the Network Access Server ID (NASID) for your NetScaler appliance to the RADIUS server as the nasid part of the Radius protocol.

<b>radVendorID</b>
Vendor ID for RADIUS group extraction. Minimum value: 1

<b>radAttributeType</b>
Attribute type for RADIUS group extraction. Minimum value: 1

<b>radGroupsPrefix</b>
Prefix string that precedes group names within a RADIUS attribute for RADIUS group extraction.

<b>radGroupSeparator</b>
Group separator string that delimits group names within a RADIUS attribute for RADIUS group extraction.

<b>passEncoding</b>
Enable password encoding in RADIUS packets that the NetScaler appliance sends to the RADIUS server. Possible values: pap, chap, mschapv1, mschapv2 Default value: AAA_PAP

<b>ipVendorID</b>
Vendor ID attribute in the RADIUS response. If the attribute is not vendor-encoded, it is set to 0.

<b>ipAttributeType</b>
IP attribute type in the RADIUS response. Minimum value: 1

<b>accounting</b>
Configure the RADIUS server state to accept or refuse accounting messages. Possible values: ON, OFF

<b>pwdVendorID</b>
Vendor ID of the password in the RADIUS response. Used to extract the user password. Minimum value: 1

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups. Maximum value: 64

<b>callingstationid</b>
Send Calling-Station-ID of the client to the RADIUS server. IP Address of the client is sent as its Calling-Station-ID. Possible values: ENABLED, DISABLED Default value: DISABLED



##Example

To configure the default RADIUS parameters: set aaa radiusparams -serverip 192.30.1.2 -radkey sslvpn

##Related Commands

<ul><li><a href="../../../set-aaa-ldapp/set-aaa-ldapp">set aaa ldapparams</a></li><li><a href="../../../et-aaa-para/et-aaa-para">set aaa parameter</a></li></ul>



##unset aaa radiusParams

Use this command to remove aaa radiusParams settings.Refer to the set aaa radiusParams command for meanings of the arguments.


##Synopsys

unset aaa radiusParams [-serverIP] [-serverPort] [-authTimeout] [-radNASip] [-radNASid] [-radVendorID] [-radAttributeType] [-radGroupsPrefix] [-radGroupSeparator] [-passEncoding] [-ipVendorID] [-ipAttributeType] [-accounting] [-pwdVendorID] [-pwdAttributeType] [-defaultAuthenticationGroup] [-callingstationid]


##show aaa radiusParams

Displays the current RADIUS configuration on the NetScaler appliance.


##Synopsys

show aaa radiusParams


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>serverIP</b>
IP address of your RADIUS server.

<b>serverPort</b>
Port number on which the RADIUS server listens for connections.

<b>radKey</b>
The key shared between the client and the server.

<b>groupAuthName</b>
To associate AAA users with an AAA group, use the command "bind AAA group ... -username ...". You can bind different policies to each AAA group. Use the command "bind AAA group ... -policy ..."

<b>authTimeout</b>
Maximum number of seconds that the NetScaler appliance waits for a response from the RADIUS server.

<b>radNASip</b>
The option to send the NetScaler's IP address (NSIP) as the "nasip" (Network Access Server IP) part of the Radius protocol to the server.

<b>radNASid</b>
The nasid (Network Access Server ID). If configured, this string will be sent to the RADIUS server as the "nasid" as part of the Radius protocol.

<b>IPAddress</b>
IP Address.

<b>radVendorID</b>
Vendor ID for RADIUS group extraction.

<b>radAttributeType</b>
Attribute type for RADIUS group extraction.

<b>radGroupsPrefix</b>
Prefix string that precedes group names within a RADIUS attribute for RADIUS group extraction.

<b>radGroupSeparator</b>
Group separator string that delimits group names within a RADIUS attribute for RADIUS group extraction.

<b>passEncoding</b>
Enable password encoding in RADIUS packets that the NetScaler appliance sends to the RADIUS server.

<b>ipVendorID</b>
Vendor ID attribute in the RADIUS response. If the attribute is not vendor-encoded, it is set to 0.

<b>ipAttributeType</b>
IP attribute type in the RADIUS response.

<b>accounting</b>
The state of the Radius server that will receive accounting messages.

<b>pwdVendorID</b>
Vendor ID of the password in the RADIUS response. Used to extract the user password.

<b>pwdAttributeType</b>
Attribute type of the Vendor ID in the RADIUS response.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>callingstationid</b>
Send Calling-Station-ID of the client to the RADIUS server. IP Address of the client is sent as its Calling-Station-ID.



##Example

&gt; show aaa radiusparams Configured RADIUS parameters Server IP: 127.0.0.2 Port: 1812 key: secret Timeout: 10 Done &gt;

