#aaa parameter

The following operations can be performed on "aaa parameter":


[set](#set-aaa-parameter) | [unset](#unset-aaa-parameter) | [show](#show-aaa-parameter)

##set aaa parameter

Sets the global AAA configuration. Any configuration settings made at this level overrides configuration settings for the authentication server.


##Synopsys

set aaa parameter [-enableStaticPageCaching ( YES | NO )] [-enableEnhancedAuthFeedback ( YES | NO )] [-defaultAuthType &lt;defaultAuthType>] [-maxAAAUsers &lt;positive_integer>] [-maxLoginAttempts &lt;positive_integer>  [-failedLoginTimeout &lt;mins>]] [-aaadnatIp &lt;ip_addr|*>] [-enableSessionStickiness ( YES | NO )]


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



##Example

set aaa parameter -defaultAuthType RADIUS -maxAAAUSers 100

##unset aaa parameter

Resets the global AAA parameter settings on the NetScaler appliance. Attributes for which a default value is available revert to their default values. See the set aaa parameter command for descriptions of the parameters..Refer to the set aaa parameter command for meanings of the arguments.


##Synopsys

unset aaa parameter [-enableStaticPageCaching] [-enableEnhancedAuthFeedback] [-defaultAuthType] [-maxAAAUsers] [-aaadnatIp] [-maxLoginAttempts] [-enableSessionStickiness]


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



##Example

&gt; show aaa parameterConfigured AAA parameters        DefaultAuthType: LDAP   MaxAAAUsers: 5 Done&gt;

