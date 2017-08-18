#authentication tacacsAction

The following operations can be performed on "authentication tacacsAction":


[add](#add-authentication-tacacsaction) | [rm](#rm-authentication-tacacsaction) | [set](#set-authentication-tacacsaction) | [unset](#unset-authentication-tacacsaction) | [show](#show-authentication-tacacsaction)

##add authentication tacacsAction

Creates an action (profile) for a TACACS+ server. The profile contains all configuration data necessary to communicate with that TACACS+ server.


##Synopsys

add authentication tacacsAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-tacacsSecret } [-authorization ( ON | OFF )] [-accounting ( ON | OFF )] [-auditFailedCmds ( ON | OFF )] [-groupAttrName &lt;string>] [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>]


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

<b>groupAttrName</b>
TACACS+ group attribute name.
Used for group extraction on the TACACS+ server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Name of the custom attribute to be extracted from server and stored at index '1' (where '1' changes for each attribute)

<b>Attribute2</b>
Name of the custom attribute to be extracted from server and stored at index '2' (where '2' changes for each attribute)

<b>Attribute3</b>
Name of the custom attribute to be extracted from server and stored at index '3' (where '3' changes for each attribute)

<b>Attribute4</b>
Name of the custom attribute to be extracted from server and stored at index '4' (where '4' changes for each attribute)

<b>Attribute5</b>
Name of the custom attribute to be extracted from server and stored at index '5' (where '5' changes for each attribute)

<b>Attribute6</b>
Name of the custom attribute to be extracted from server and stored at index '6' (where '6' changes for each attribute)

<b>Attribute7</b>
Name of the custom attribute to be extracted from server and stored at index '7' (where '7' changes for each attribute)

<b>Attribute8</b>
Name of the custom attribute to be extracted from server and stored at index '8' (where '8' changes for each attribute)

<b>Attribute9</b>
Name of the custom attribute to be extracted from server and stored at index '9' (where '9' changes for each attribute)

<b>Attribute10</b>
Name of the custom attribute to be extracted from server and stored at index '10' (where '10' changes for each attribute)

<b>Attribute11</b>
Name of the custom attribute to be extracted from server and stored at index '11' (where '11' changes for each attribute)

<b>Attribute12</b>
Name of the custom attribute to be extracted from server and stored at index '12' (where '12' changes for each attribute)

<b>Attribute13</b>
Name of the custom attribute to be extracted from server and stored at index '13' (where '13' changes for each attribute)

<b>Attribute14</b>
Name of the custom attribute to be extracted from server and stored at index '14' (where '14' changes for each attribute)

<b>Attribute15</b>
Name of the custom attribute to be extracted from server and stored at index '15' (where '15' changes for each attribute)

<b>Attribute16</b>
Name of the custom attribute to be extracted from server and stored at index '16' (where '16' changes for each attribute)



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

set authentication tacacsAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] {-tacacsSecret } [-authorization ( ON | OFF )] [-accounting ( ON | OFF )] [-auditFailedCmds ( ON | OFF )] [-groupAttrName &lt;string>] [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>]


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

<b>groupAttrName</b>
TACACS+ group attribute name.
Used for group extraction on the TACACS+ server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Name of the custom attribute to be extracted from server and stored at index '1' (where '1' changes for each attribute)

<b>Attribute2</b>
Name of the custom attribute to be extracted from server and stored at index '2' (where '2' changes for each attribute)

<b>Attribute3</b>
Name of the custom attribute to be extracted from server and stored at index '3' (where '3' changes for each attribute)

<b>Attribute4</b>
Name of the custom attribute to be extracted from server and stored at index '4' (where '4' changes for each attribute)

<b>Attribute5</b>
Name of the custom attribute to be extracted from server and stored at index '5' (where '5' changes for each attribute)

<b>Attribute6</b>
Name of the custom attribute to be extracted from server and stored at index '6' (where '6' changes for each attribute)

<b>Attribute7</b>
Name of the custom attribute to be extracted from server and stored at index '7' (where '7' changes for each attribute)

<b>Attribute8</b>
Name of the custom attribute to be extracted from server and stored at index '8' (where '8' changes for each attribute)

<b>Attribute9</b>
Name of the custom attribute to be extracted from server and stored at index '9' (where '9' changes for each attribute)

<b>Attribute10</b>
Name of the custom attribute to be extracted from server and stored at index '10' (where '10' changes for each attribute)

<b>Attribute11</b>
Name of the custom attribute to be extracted from server and stored at index '11' (where '11' changes for each attribute)

<b>Attribute12</b>
Name of the custom attribute to be extracted from server and stored at index '12' (where '12' changes for each attribute)

<b>Attribute13</b>
Name of the custom attribute to be extracted from server and stored at index '13' (where '13' changes for each attribute)

<b>Attribute14</b>
Name of the custom attribute to be extracted from server and stored at index '14' (where '14' changes for each attribute)

<b>Attribute15</b>
Name of the custom attribute to be extracted from server and stored at index '15' (where '15' changes for each attribute)

<b>Attribute16</b>
Name of the custom attribute to be extracted from server and stored at index '16' (where '16' changes for each attribute)



##unset authentication tacacsAction

Use this command to remove authentication tacacsAction settings.Refer to the set authentication tacacsAction command for meanings of the arguments.


##Synopsys

unset authentication tacacsAction &lt;name> [-serverIP] [-serverPort] [-authTimeout] [-tacacsSecret] [-authorization] [-accounting] [-auditFailedCmds] [-groupAttrName] [-defaultAuthenticationGroup] [-Attribute1] [-Attribute2] [-Attribute3] [-Attribute4] [-Attribute5] [-Attribute6] [-Attribute7] [-Attribute8] [-Attribute9] [-Attribute10] [-Attribute11] [-Attribute12] [-Attribute13] [-Attribute14] [-Attribute15] [-Attribute16]


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

<b>groupAttrName</b>
TACACS+ group attribute name.
Used for group extraction on the TACACS+ server.

<b>Success</b>

<b>Failure</b>

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>stateflag</b>

<b>Attribute1</b>
Name of the custom attribute to be extracted from server and stored at index '1' (where '1' changes for each attribute)

<b>Attribute2</b>
Name of the custom attribute to be extracted from server and stored at index '2' (where '2' changes for each attribute)

<b>Attribute3</b>
Name of the custom attribute to be extracted from server and stored at index '3' (where '3' changes for each attribute)

<b>Attribute4</b>
Name of the custom attribute to be extracted from server and stored at index '4' (where '4' changes for each attribute)

<b>Attribute5</b>
Name of the custom attribute to be extracted from server and stored at index '5' (where '5' changes for each attribute)

<b>Attribute6</b>
Name of the custom attribute to be extracted from server and stored at index '6' (where '6' changes for each attribute)

<b>Attribute7</b>
Name of the custom attribute to be extracted from server and stored at index '7' (where '7' changes for each attribute)

<b>Attribute8</b>
Name of the custom attribute to be extracted from server and stored at index '8' (where '8' changes for each attribute)

<b>Attribute9</b>
Name of the custom attribute to be extracted from server and stored at index '9' (where '9' changes for each attribute)

<b>Attribute10</b>
Name of the custom attribute to be extracted from server and stored at index '10' (where '10' changes for each attribute)

<b>Attribute11</b>
Name of the custom attribute to be extracted from server and stored at index '11' (where '11' changes for each attribute)

<b>Attribute12</b>
Name of the custom attribute to be extracted from server and stored at index '12' (where '12' changes for each attribute)

<b>Attribute13</b>
Name of the custom attribute to be extracted from server and stored at index '13' (where '13' changes for each attribute)

<b>Attribute14</b>
Name of the custom attribute to be extracted from server and stored at index '14' (where '14' changes for each attribute)

<b>Attribute15</b>
Name of the custom attribute to be extracted from server and stored at index '15' (where '15' changes for each attribute)

<b>Attribute16</b>
Name of the custom attribute to be extracted from server and stored at index '16' (where '16' changes for each attribute)

<b>devno</b>

<b>count</b>



