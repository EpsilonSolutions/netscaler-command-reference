#system parameter

The following operations can be performed on "system parameter":


[set](#set-system-parameter) | [unset](#unset-system-parameter) | [show](#show-system-parameter)

##set system parameter

Modifies the specified system parameters.


##Synopsys

set system parameter [-rbaOnResponse ( ENABLED | DISABLED )] [-promptString &lt;string>] [-natPcbForceFlushLimit &lt;positive_integer>] [-natPcbRstOnTimeout ( ENABLED | DISABLED )] [-timeout &lt;secs>] [-localAuth ( ENABLED | DISABLED )] [-restrictedtimeout ( ENABLED | DISABLED )]


##Arguments

<b>rbaOnResponse</b>
Enable or disable Role-Based Authentication (RBA) on responses.
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

<b>natPcbForceFlushLimit</b>
Flush the system if the number of Network Address Translation Protocol Control Blocks (NATPCBs) exceeds this value.
Default value: 2147483647
Minimum value: 1000

<b>natPcbRstOnTimeout</b>
Send a reset signal to client and server connections when their NATPCBs time out. Avoids the buildup of idle TCP connections on both the sides.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>timeout</b>
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>localAuth</b>
When enabled, local users can access NetScaler even when external authentication is configured. When disabled, local users are not allowed to access the NetScaler, Local users can access the NetScaler only when the configured external authentication servers are unavailable.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>restrictedtimeout</b>
Enable/Disable the restricted timeout behaviour. When enabled, timeout cannot be configured beyond admin configured timeout and also it will have\\
 the [minimum - maximum] range check. When disabled, timeout will have the old behaviour. By default the value is disabled
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset system parameter

Use this command to remove system parameter settings.Refer to the set system parameter command for meanings of the arguments.


##Synopsys

unset system parameter [-rbaOnResponse] [-promptString] [-natPcbForceFlushLimit] [-natPcbRstOnTimeout] [-timeout] [-localAuth] [-restrictedtimeout]


##show system parameter

Displays information about the system parameters.


##Synopsys

show system parameter


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>rbaOnResponse</b>
Enable or disable Role-Based Authentication (RBA) on responses.

<b>promptString</b>
The global system prompt.

<b>natPcbForceFlushLimit</b>
Flush the system if the number of Network Address Translation Protocol Control Blocks (NATPCBs) exceeds this value.

<b>natPcbRstOnTimeout</b>
Send RST to client and server connections when the natpcbs timeout.This avoids the buildup of idle TCP connections on the both the sides.

<b>timeout</b>
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>maxClient</b>
Maximum number of client connection allowed by the system

<b>localAuth</b>
When enabled, local users can access NetScaler even when external authentication is configured. When disabled, local users are not allowed to access the NetScaler, Local users can access the NetScaler only when the configured external authentication servers are unavailable.

<b>restrictedtimeout</b>
Enable/Disable the restricted timeout behaviour. When enabled, timeout cannot be configured beyond admin configured timeout and also it will have\\
 the [minimum - maximum] range check. When disabled, timeout will have the old behaviour. By default the value is disabled



