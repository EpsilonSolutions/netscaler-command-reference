#system parameter

The following operations can be performed on "system parameter":


[set](#set-system-parameter) | [unset](#unset-system-parameter) | [show](#show-system-parameter)

##set system parameter

Modifies the specified system parameters.


##Synopsys

set system parameter [-rbaOnResponse ( ENABLED | DISABLED )] [-promptString &lt;string>] [-natPcbForceFlushLimit &lt;positive_integer>] [-natPcbRstOnTimeout ( ENABLED | DISABLED )] [-timeout &lt;secs>] [-localAuth ( ENABLED | DISABLED )] [-minpasswordlen &lt;positive_integer>] [-strongpassword &lt;strongpassword>] [-restrictedtimeout ( ENABLED | DISABLED )] [-fipsUserMode ( ENABLED | DISABLED )] [-doppler ( ENABLED | DISABLED )] [-googleanalytics ( ENABLED | DISABLED )] [-totalAuthTimeout &lt;positive_integer>] [-cliLoglevel &lt;cliLoglevel>] [-forcePasswordChange ( ENABLED | DISABLED )] [-basicAuth ( ENABLED | DISABLED )]


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
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument is enabled, Timeout can have values in the range [300-86400] seconds.
If Restrictedtimeout argument is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>localAuth</b>
When enabled, local users can access NetScaler even when external authentication is configured. When disabled, local users are not allowed to access the NetScaler, Local users can access the NetScaler only when the configured external authentication servers are unavailable.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>minpasswordlen</b>
Minimum length of system user password. When strong password is enabled default minimum length is 4. User entered value can be greater than or equal to 4. Default mininum value is 1 when strong password is disabled. Maximum value is 127 in both cases.
Minimum value: 1
Maximum value: 127

<b>strongpassword</b>
After enabling strong password (enableall / enablelocal - not included in exclude list), all the passwords / sensitive information must have - Atleast 1 Lower case character, Atleast 1 Upper case character, Atleast 1 numeric character, Atleast 1 special character ( ~, `, !, @, #, $, %, ^, &, *, -, _, =, +, {, }, [, ], |, \\, :, &lt;, &gt;, /, ., ,, " "). Exclude list in case of enablelocal is - NS_FIPS, NS_CRL, NS_RSAKEY, NS_PKCS12, NS_PKCS8, NS_LDAP, NS_TACACS, NS_TACACSACTION, NS_RADIUS, NS_RADIUSACTION, NS_ENCRYPTION_PARAMS. So no Strong Password checks will be performed on these ObjectType commands for enablelocal case.
Possible values: enableall, enablelocal, disabled
Default value: disabled

<b>restrictedtimeout</b>
Enable/Disable the restricted timeout behaviour. When enabled, timeout cannot be configured beyond admin configured timeout  and also it will have the [minimum - maximum] range check. When disabled, timeout will have the old behaviour. By default the value is disabled
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>fipsUserMode</b>
Use this option to set the FIPS mode for key user-land processes. When enabled, these user-land processes will operate in FIPS mode. In this mode, theses processes will use FIPS 140-2 Level-1 certified crypto algorithms. Default is disabled, wherein, these user-land processes will not operate in FIPS mode.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>doppler</b>
Enable or disable Doppler
Possible values: ENABLED, DISABLED
Default value: 0

<b>googleanalytics</b>
Enable or disable Google analytics
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>totalAuthTimeout</b>
Total time a request can take for authentication/authorization
Default value: 20
Minimum value: 5
Maximum value: 120

<b>cliLoglevel</b>
Audit log level, which specifies the types of events to log for cli executed commands.
Available values function as follows:
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.
Possible values: EMERGENCY, ALERT, CRITICAL, ERROR, WARNING, NOTICE, INFORMATIONAL, DEBUG
Default value: INFORMATIONAL

<b>forcePasswordChange</b>
Enable or disable force password change for nsroot user
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>basicAuth</b>
Enable or disable basic authentication for Nitro API.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##unset system parameter

Resets the specified system parameters..Refer to the set system parameter command for meanings of the arguments.


##Synopsys

unset system parameter [-minpasswordlen] [-rbaOnResponse] [-promptString] [-natPcbForceFlushLimit] [-natPcbRstOnTimeout] [-timeout] [-localAuth] [-strongpassword] [-restrictedtimeout] [-fipsUserMode] [-doppler] [-googleanalytics] [-totalAuthTimeout] [-cliLoglevel] [-forcePasswordChange] [-basicAuth]


##show system parameter

Displays information about the system parameters.


##Synopsys

show system parameter


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
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument is enabled, Timeout can have values in the range [300-86400] seconds.
If Restrictedtimeout argument is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>maxClient</b>
Maximum number of client connection allowed by the system

<b>localAuth</b>
When enabled, local users can access NetScaler even when external authentication is configured. When disabled, local users are not allowed to access the NetScaler, Local users can access the NetScaler only when the configured external authentication servers are unavailable.

<b>minpasswordlen</b>
Minimum length of system user password. When strong password is enabled default minimum length is 4. User entered value can be greater than or equal to 4. Default mininum value is 1 when strong password is disabled. Maximum value is 127 in both cases.

<b>strongpassword</b>
After enabling strong password (enableall / enablelocal - not included in exclude list), all the passwords / sensitive information must have - Atleast 1 Lower case character, Atleast 1 Upper case character, Atleast 1 numeric character, Atleast 1 special character ( ~, `, !, @, #, $, %, ^, &, *, -, _, =, +, {, }, [, ], |, \\, :, &lt;, >, /, ., ,, " "). Exclude list in case of enablelocal is - NS_FIPS, NS_CRL, NS_RSAKEY, NS_PKCS12, NS_PKCS8, NS_LDAP, NS_TACACS, NS_TACACSACTION, NS_RADIUS, NS_RADIUSACTION, NS_ENCRYPTION_PARAMS. So no Strong Password checks will be performed on these ObjectType commands for enablelocal case.

<b>restrictedtimeout</b>
Enable/Disable the restricted timeout behaviour. When enabled, timeout cannot be configured beyond admin configured timeout  and also it will have the [minimum - maximum] range check. When disabled, timeout will have the old behaviour. By default the value is disabled

<b>fipsUserMode</b>
Use this option to set the FIPS mode for key user-land processes. When enabled, these user-land processes will operate in FIPS mode. In this mode, theses processes will use FIPS 140-2 Level-1 certified crypto algorithms. Default is disabled, wherein, these user-land processes will not operate in FIPS mode.

<b>doppler</b>
Enable or disable Doppler

<b>googleanalytics</b>
Enable or disable Google analytics

<b>cliLoglevel</b>
Audit log level, which specifies the types of events to log for cli executed commands.
Available values function as follows:
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.

<b>forcePasswordChange</b>
Enable or disable force password change for nsroot user

<b>totalAuthTimeout</b>
Total time a request can take for authentication/authorization

<b>basicAuth</b>
Enable or disable basic authentication for Nitro API.



