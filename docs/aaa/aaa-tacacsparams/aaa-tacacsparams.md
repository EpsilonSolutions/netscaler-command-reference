#aaa tacacsParams

The following operations can be performed on "aaa tacacsParams":


[set](#set-aaa-tacacsparams) | [unset](#unset-aaa-tacacsparams) | [show](#show-aaa-tacacsparams)

##set aaa tacacsParams

Modifies the global configuration settings for the TACACS+ server. The settings that you specify are used for all SSL-VPN virtual servers unless you use authentication policies to create a configuration for a specific SSL-VPN virtual server.


##Synopsys

set aaa tacacsParams [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-tacacsSecret } [-authorization ( ON | OFF )] [-accounting ( ON | OFF )] [-auditFailedCmds ( ON | OFF )] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>serverIP</b>
IP address of your TACACS+ server.

<b>serverPort</b>
Port number on which the TACACS+ server listens for connections. Default value: 49 Minimum value: 1

<b>authTimeout</b>
Maximum number of seconds that the NetScaler appliance waits for a response from the TACACS+ server. Default value: 3 Minimum value: 1

<b>tacacsSecret</b>
Key shared between the TACACS+ server and clients. Required for allowing the NetScaler appliance to communicate with the TACACS+ server.

<b>authorization</b>
Use streaming authorization on the TACACS+ server. Possible values: ON, OFF

<b>accounting</b>
Send accounting messages to the TACACS+ server. Possible values: ON, OFF

<b>auditFailedCmds</b>
The option for sending accounting messages to the TACACS+ server. Possible values: ON, OFF

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups. Maximum value: 64



##Example

To configure a TACACS+ server running at 192.168.1.20 set aaa tacacsparams -serverip 192.168.1.20 -tacacssecret secret

##Related Commands

<ul><li><a href="../../../l#set-aaa-radiusp/l#set-aaa-radiusp">set aaa radiusparams</a></li><li><a href="../../../et-aaa-para/et-aaa-para">set aaa parameter</a></li></ul>



##unset aaa tacacsParams

Use this command to remove aaa tacacsParams settings.Refer to the set aaa tacacsParams command for meanings of the arguments.


##Synopsys

unset aaa tacacsParams [-serverIP] [-serverPort] [-authTimeout] [-tacacsSecret] [-authorization] [-accounting] [-auditFailedCmds] [-defaultAuthenticationGroup]


##show aaa tacacsParams

Displays the NetScaler appliance?s current AAA TACACS+ configuration.


##Synopsys

show aaa tacacsParams


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>serverIP</b>
IP address of your TACACS+ server.

<b>serverPort</b>
Port number on which the TACACS+ server listens for connections.

<b>authTimeout</b>
Maximum number of seconds that the NetScaler appliance waits for a response from the TACACS+ server.

<b>tacacsSecret</b>
The key shared between the client and the server.

<b>authorization</b>
The option for the streaming authorization for TACACS+ server.

<b>accounting</b>
The option to send accounting messages to TACACS+ server.

<b>auditFailedCmds</b>
The option to send accounting messages to TACACS+ server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##Example

&gt; sh aaa tacacsparams Configured TACACS parameter Server IP: 192.168.1.20 Port: 49 Timeout: 1 secs Done

