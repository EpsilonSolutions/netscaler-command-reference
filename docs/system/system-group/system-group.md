#system group

The following operations can be performed on "system group":


[add](#add-system-group) | [rm](#rm-system-group) | [bind](#bind-system-group) | [unbind](#unbind-system-group) | [show](#show-system-group) | [set](#set-system-group) | [unset](#unset-system-group)

##add system group

Creates a system-user group, to which you can bind individual users by using the bind system group command.


##Synopsys

add system group &lt;groupName> [-promptString &lt;string>] [-timeout &lt;secs>]


##Arguments

<b>groupName</b>
Name for the group. Must begin with a letter, number, or the underscore (_) character, and must contain only alphanumeric, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), and underscore characters. Cannot be changed after the group is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my group" or 'my group').

<b>promptString</b>
String to display at the command-line prompt. Can consist of letters, numbers, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), underscore (_), and the following variables: 
* %u - Will be replaced by the user name.
* %h - Will be replaced by the hostname of the NetScaler appliance.
* %t - Will be replaced by the current time in 12-hour format.
* %T - Will be replaced by the current time in 24-hour format.
* %d - Will be replaced by the current date.
* %s - Will be replaced by the state of the NetScaler appliance.
Note: The 63-character limit for the length of the string does not apply to the characters that replace the variables.

<b>timeout</b>
CLI session inactivity timeout, in seconds.If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.



##rm system group

Removes a system group from the appliance.


##Synopsys

rm system group &lt;groupName>


##Arguments

<b>groupName</b>
Name of the system group to remove.



##bind system group

Binds a system user to a system group.


##Synopsys

bind system group &lt;groupName> [-userName &lt;string>] [-policyName &lt;string>  &lt;priority>]


##Arguments

<b>groupName</b>
Name of the system group.

<b>userName</b>
Name of a system user to bind to the group.

<b>policyName</b>
Name of the command policy to be bind to the group.



##unbind system group

Unbinds a system user from a group.


##Synopsys

unbind system group &lt;groupName> [-userName &lt;string>] [-policyName &lt;string>]


##Arguments

<b>groupName</b>
Name of the system group from which to unbind the user.

<b>userName</b>
Name of the system user to unbind from the group.

<b>policyName</b>
Command policy to unbind from the group.



##show system group

Displays information about all system groups configured on the appliance, or about the specified group.


##Synopsys

show system group [&lt;groupName>]


##Arguments

<b>groupName</b>
Name of the system group about which to display information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>userName</b>
The system user.

<b>policyName</b>
The name of command policy.

<b>priority</b>
The priority of the command policy.

<b>promptString</b>
String to display at the command-line prompt. Can consist of letters, numbers, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), underscore (_), and the following variables: 
* %u - Will be replaced by the user name.
* %h - Will be replaced by the hostname of the NetScaler appliance.
* %t - Will be replaced by the current time in 12-hour format.
* %T - Will be replaced by the current time in 24-hour format.
* %d - Will be replaced by the current date.
* %s - Will be replaced by the state of the NetScaler appliance.
Note: The 63-character limit for the length of the string does not apply to the characters that replace the variables.

<b>timeout</b>
CLI session inactivity timeout, in seconds.If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##set system group

Modifies the specified parameters of a system group.


##Synopsys

set system group &lt;groupName> [-promptString &lt;string>] [-timeout &lt;secs>]


##Arguments

<b>groupName</b>
Name of system group to be modified.

<b>promptString</b>
String to display at the command-line prompt. Can consist of letters, numbers, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), underscore (_), and the following variables: 
* %u - Will be replaced by the user name.
* %h - Will be replaced by the hostname of the NetScaler appliance.
* %t - Will be replaced by the current time in 12-hour format.
* %T - Will be replaced by the current time in 24-hour format.
* %d - Will be replaced by the current date.
* %s - Will be replaced by the state of the NetScaler appliance.
Note: The 63-character limit for the length of the string does not apply to the characters that replace the variables.

<b>timeout</b>
CLI session inactivity timeout, in seconds.If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.



##unset system group

Use this command to remove system group settings.Refer to the set system group command for meanings of the arguments.


##Synopsys

unset system group &lt;groupName> [-promptString] [-timeout]


