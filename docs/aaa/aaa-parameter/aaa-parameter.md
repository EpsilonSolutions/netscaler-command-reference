#aaa parameter

The following operations can be performed on "aaa parameter":


[set](#set-aaa-parameter) | [unset](#unset-aaa-parameter) | [show](#show-aaa-parameter)

##set aaa parameter

Sets the global AAA configuration. Any configuration settings made at this level overrides configuration settings for the authentication server.


##Synopsys

set aaa parameter [-enableStaticPageCaching ( YES | NO )] [-enableEnhancedAuthFeedback ( YES | NO )] [-defaultAuthType &lt;defaultAuthType>] [-maxAAAUsers &lt;positive_integer>] [-maxLoginAttempts &lt;positive_integer>  [-failedLoginTimeout &lt;mins>]] [-aaadnatIp &lt;ip_addr|*>] [-enableSessionStickiness ( YES | NO )] [-aaaSessionLoglevel &lt;aaaSessionLoglevel>] [-aaadLoglevel &lt;aaadLoglevel>] [-dynAddr ( ON | OFF )] [-ftMode &lt;ftMode>]


##Arguments

<b>enableStaticPageCaching</b>
The default state of VPN Static Page caching. If nothing is specified, the default value is set to YES.
Possible values: YES, NO
Default value: YES

<b>enableEnhancedAuthFeedback</b>
Enhanced auth feedback provides more information to the end user about the reason for an authentication failure.  The default value is set to NO.
Possible values: YES, NO
Default value: NO

<b>defaultAuthType</b>
The default authentication server type.
Possible values: LOCAL, LDAP, RADIUS, TACACS, CERT
Default value: LOCAL

<b>maxAAAUsers</b>
Maximum number of concurrent users allowed to log on to VPN simultaneously.
Minimum value: 1

<b>maxLoginAttempts</b>
Maximum Number of login Attempts
Minimum value: 1

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts
Minimum value: 1

<b>aaadnatIp</b>
Source IP address to use for traffic that is sent to the authentication server.

<b>enableSessionStickiness</b>
Enables/Disables stickiness to authentication servers
Possible values: YES, NO
Default value: NO

<b>aaaSessionLoglevel</b>
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
Default value: DEFAULT_LOGLEVEL_AAA

<b>aaadLoglevel</b>
AAAD log level, which specifies the types of AAAD events to log in nsvpn.log. 
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

<b>dynAddr</b>
Set by the DHCP client when the IP address was fetched dynamically.
Possible values: ON, OFF
Default value: OFF

<b>ftMode</b>
First time user mode determines which configuration options are shown by default when logging in to the GUI. This setting is controlled by the GUI.
Possible values: ON, HA, OFF
Default value: ON



##Example

set aaa parameter -defaultAuthType RADIUS -maxAAAUSers 100

##unset aaa parameter

Resets the global AAA parameter settings on the NetScaler appliance. Attributes for which a default value is available revert to their default values. See the set aaa parameter command for descriptions of the parameters..Refer to the set aaa parameter command for meanings of the arguments.


##Synopsys

unset aaa parameter [-enableStaticPageCaching] [-enableEnhancedAuthFeedback] [-defaultAuthType] [-maxAAAUsers] [-aaadnatIp] [-maxLoginAttempts] [-enableSessionStickiness] [-aaaSessionLoglevel] [-aaadLoglevel] [-dynAddr] [-ftMode]


##show aaa parameter

Displays the current AAA global configuration.


##Synopsys

show aaa parameter


##Outputs

<b>enableStaticPageCaching</b>
Indicates if static page caching is enabled or not.

<b>enableEnhancedAuthFeedback</b>
Indicates whether enhanced auth feedback is enabled or not.

<b>defaultAuthType</b>
The default authentication server type.

<b>maxAAAUsers</b>
The maximum number of concurrent users allowed to log into the system at any time.

<b>aaadnatIp</b>
The natIp to be used for the AAA traffic

<b>maxLoginAttempts</b>
Maximum Number of login Attempts

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts

<b>enableSessionStickiness</b>
Enables/Disables stickiness to authentication servers

<b>aaaSessionLoglevel</b>
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

<b>aaadLoglevel</b>
AAAD log level, which specifies the types of AAAD events to log in nsvpn.log. 
Available values function as follows: 
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.

<b>dynAddr</b>
Set by the DHCP client when the IP address was fetched dynamically.

<b>ftMode</b>
First time user mode determines which configuration options are shown by default when logging in to the GUI. This setting is controlled by the GUI.



##Example

&gt; show aaa parameterConfigured AAA parameters        DefaultAuthType: LDAP   MaxAAAUsers: 5 Done&gt;

