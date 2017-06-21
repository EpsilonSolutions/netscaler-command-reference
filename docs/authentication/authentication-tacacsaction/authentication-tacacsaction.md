#authentication tacacsAction

The following operations can be performed on "authentication tacacsAction":


[add](#add-authentication-tacacsaction) | [rm](#rm-authentication-tacacsaction) | [set](#set-authentication-tacacsaction) | [unset](#unset-authentication-tacacsaction) | [show](#show-authentication-tacacsaction)

##add authentication tacacsAction

Creates an action (profile) for a TACACS+ server. The profile contains all configuration data necessary to communicate with that TACACS+ server.


##Synopsys

add authentication tacacsAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-tacacsSecret } [-authorization ( ON | OFF )] [-accounting ( ON | OFF )] [-auditFailedCmds ( ON | OFF )] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name for the TACACS+ profile (action). 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after TACACS profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication action" or 'y authentication action').

<b>serverIP</b>
IP address assigned to the TACACS+ server.

<b>serverPort</b>
Port number on which the TACACS+ server listens for connections.
Default value: 49
Minimum value: 1

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the TACACS+ server.
Default value: 3
Minimum value: 1

<b>tacacsSecret</b>
Key shared between the TACACS+ server and the NetScaler appliance. 
Required for allowing the NetScaler appliance to communicate with the TACACS+ server.

<b>authorization</b>
Use streaming authorization on the TACACS+ server.
Possible values: ON, OFF

<b>accounting</b>
Whether the TACACS+ server is currently accepting accounting messages.
Possible values: ON, OFF

<b>auditFailedCmds</b>
The state of the TACACS+ server that will receive accounting messages.
Possible values: ON, OFF

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##rm authentication tacacsAction

Removes a TACACS+ profile (action). A profile cannot be removed as long as it is bound to a policy.


##Synopsys

rm authentication tacacsAction &lt;name>


##Arguments

<b>name</b>
Name of the profile to be removed.



##set authentication tacacsAction

Modifies a TACACS+ server profile (action).


##Synopsys

set authentication tacacsAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-tacacsSecret } [-authorization ( ON | OFF )] [-accounting ( ON | OFF )] [-auditFailedCmds ( ON | OFF )] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name of the TACACS+ profile to modify.

<b>serverIP</b>
IP address assigned to the TACACS+ server.

<b>serverPort</b>
Port number on which the TACACS+ server listens for connections.
Default value: 49
Minimum value: 1

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the TACACS+ server.
Default value: 3
Minimum value: 1

<b>tacacsSecret</b>
Key shared between the TACACS+ server and the NetScaler appliance. 
Required for allowing the NetScaler appliance to communicate with the TACACS+ server.

<b>authorization</b>
Use streaming authorization on the TACACS+ server.
Possible values: ON, OFF

<b>accounting</b>
Whether the TACACS+ server is currently accepting accounting messages.
Possible values: ON, OFF

<b>auditFailedCmds</b>
The state of the TACACS+ server that will receive accounting messages.
Possible values: ON, OFF

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##unset authentication tacacsAction

Use this command to remove authentication tacacsAction settings.Refer to the set authentication tacacsAction command for meanings of the arguments.


##Synopsys

unset authentication tacacsAction &lt;name> [-serverIP] [-serverPort] [-authTimeout] [-tacacsSecret] [-authorization] [-accounting] [-auditFailedCmds] [-defaultAuthenticationGroup]


##show authentication tacacsAction

Displays the current configuration settings for the specified TACACS+ profile (action).


##Synopsys

show authentication tacacsAction [&lt;name>]


##Arguments

<b>name</b>
Name of the TACACS+ profile.



##Outputs

<b>serverIP</b>
IP address assigned to the TACACS+ server.

<b>serverPort</b>
Port number on which the TACACS+ server listens for connections.

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the TACACS+ server.

<b>tacacsSecret</b>
Key shared between the TACACS+ server and the NetScaler appliance. 
Required for allowing the NetScaler appliance to communicate with the TACACS+ server.

<b>authorization</b>
Use streaming authorization on the TACACS+ server.

<b>accounting</b>
Whether the TACACS+ server is currently accepting accounting messages.

<b>auditFailedCmds</b>
The state of the TACACS+ server that will receive accounting messages.

<b>Success</b>

<b>Failure</b>

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



