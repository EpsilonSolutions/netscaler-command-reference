#system user

The following operations can be performed on "system user":


[add](#add-system-user) | [rm](#rm-system-user) | [set](#set-system-user) | [unset](#unset-system-user) | [bind](#bind-system-user) | [unbind](#unbind-system-user) | [show](#show-system-user)

##add system user

Adds a new user to the system.Note: You must provide the password after the user name.


##Synopsys

add system user &lt;userName> [-externalAuth ( ENABLED | DISABLED )] [-promptString &lt;string>] [-timeout &lt;secs>] [-logging ( ENABLED | DISABLED )]


##Arguments

<b>userName</b>
Name for a user. Must begin with a letter, number, or the underscore (_) character, and must contain only alphanumeric, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), and underscore characters. Cannot be changed after the user is added.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my user" or 'my user').

<b>password</b>
Password for the system user. Can include any ASCII character.

<b>externalAuth</b>
Whether to use external authentication servers for the system user authentication or not
Possible values: ENABLED, DISABLED
Default value: ENABLED

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
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>logging</b>
Users logging privilege
Possible values: ENABLED, DISABLED
Default value: DISABLED



##rm system user

Removes a system user from the appliance.


##Synopsys

rm system user &lt;userName>


##Arguments

<b>userName</b>
Name of the system user to remove.



##set system user

Modifies the specified parameters of a system-user entry.


##Synopsys

set system user &lt;userName> {-password } [-externalAuth ( ENABLED | DISABLED )] [-promptString &lt;string>] [-timeout &lt;secs>] [-logging ( ENABLED | DISABLED )]


##Arguments

<b>userName</b>
Name of the system-user entry to modify.

<b>password</b>
Password for the system user. Can include any ASCII character.

<b>externalAuth</b>
Whether to use external authentication servers for the system user authentication or not
Possible values: ENABLED, DISABLED
Default value: ENABLED

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
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>logging</b>
Users logging privilege
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset system user

Use this command to remove system user settings.Refer to the set system user command for meanings of the arguments.


##Synopsys

unset system user &lt;userName> [-externalAuth] [-promptString] [-timeout] [-logging]


##bind system user

Binds a command policy to a system user.


##Synopsys

bind system user &lt;userName> &lt;policyName> &lt;priority>


##Arguments

<b>userName</b>
Name of the system-user entry to which to bind the command policy.

<b>policyName</b>
Name of the command policy to bind to the system user.



##unbind system user

Unbinds a command policy from the system user.


##Synopsys

unbind system user &lt;userName> &lt;policyName>


##Arguments

<b>userName</b>
Name of the user entry from which to unbind the command policy.

<b>policyName</b>
Name of the command policy to unbind.



##show system user

Displays information about all system users configured on the appliance, or about the specified user.


##Synopsys

show system user [&lt;userName>]


##Arguments

<b>userName</b>
Name of a system user about whom to display information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>groupName</b>
The system group.

<b>policyName</b>
The name of command policy.

<b>priority</b>
The priority of the policy.

<b>password</b>
Password for the system user. Can include any ASCII character.

<b>encrypted</b>

<b>externalAuth</b>
Whether to use external authentication servers for the system user authentication or not

<b>promptString</b>
String to display at the command-line prompt. Can consist of letters, numbers, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), underscore (_), and the following variables: 
* %u - Will be replaced by the user name.
* %h - Will be replaced by the hostname of the NetScaler appliance.
* %t - Will be replaced by the current time in 12-hour format.
* %T - Will be replaced by the current time in 24-hour format.
* %d - Will be replaced by the current date.
* %s - Will be replaced by the state of the NetScaler appliance.
Note: The 63-character limit for the length of the string does not apply to the characters that replace the variables.

<b>promptInheritedFrom</b>
From where the prompt has been inherited.

<b>timeout</b>
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>timeoutKind</b>
From where the timeout has been inherited.

<b>logging</b>
Users logging privilege

<b>devno</b>

<b>count</b>

<b>stateflag</b>



