#authentication vserver

The following operations can be performed on "authentication vserver":


[add](#add-authentication-vserver) | [rm](#rm-authentication-vserver) | [set](#set-authentication-vserver) | [unset](#unset-authentication-vserver) | [bind](#bind-authentication-vserver) | [unbind](#unbind-authentication-vserver) | [enable](#enable-authentication-vserver) | [disable](#disable-authentication-vserver) | [show](#show-authentication-vserver) | [stat](#stat-authentication-vserver) | [rename](#rename-authentication-vserver)

##add authentication vserver

Creates an authentication virtual server.


##Synopsys

add authentication vserver &lt;name> &lt;serviceType> [&lt;IPAddress>  [-range &lt;positive_integer>]] [&lt;port>] [-state ( ENABLED | DISABLED )] [-authentication ( ON | OFF )] [-AuthenticationDomain &lt;string>] [-comment &lt;string>] [-td &lt;positive_integer>] [-appflowLog ( ENABLED | DISABLED )] [-maxLoginAttempts &lt;positive_integer>  [-failedLoginTimeout &lt;mins>]]


##Arguments

<b>name</b>
Name for the new authentication virtual server. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the authentication virtual server is added by using the rename authentication vserver command.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>serviceType</b>
Protocol type of the authentication virtual server. Always SSL.
Possible values: SSL
Default value: SSL

<b>IPAddress</b>
IP address of the authentication virtual server, if a single IP address is assigned to the virtual server.

<b>range</b>
If you are creating a series of virtual servers with a range of IP addresses assigned to them, the length of the range. 
The new range of authentication virtual servers will have IP addresses consecutively numbered, starting with the primary address specified with the IP Address parameter.
Default value: 1
Minimum value: 1

<b>port</b>
TCP port on which the virtual server accepts connections.

<b>state</b>
Initial state of the new virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>authentication</b>
Require users to be authenticated before sending traffic through this virtual server.
Possible values: ON, OFF
Default value: ON

<b>AuthenticationDomain</b>
Fully-qualified domain name (FQDN) of the authentication virtual server.

<b>comment</b>
Any comments associated with this virtual server.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>appflowLog</b>
Log AppFlow flow information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxLoginAttempts</b>
Maximum Number of login Attempts
Minimum value: 1
Maximum value: 255

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts
Minimum value: 1



##Example

The following example creates an authentication vserver named myauthenticationvip which supports SSL portocol and with AAA functionality enabled: vserver myauthenticationvip SSL 65.219.17.34 443 -aaa ON

##rm authentication vserver

Removes an authentication virtual server.


##Synopsys

rm authentication vserver &lt;name>@ ...


##Arguments

<b>name</b>
Name of the authentication virtual server to remove.



##Example

rm vserver authn_vip

##set authentication vserver

Modifies the specified parameters of an existing authentication virtual server.


##Synopsys

set authentication vserver &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr|*>] [-authentication ( ON | OFF )] [-AuthenticationDomain &lt;string>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-maxLoginAttempts &lt;positive_integer>] [-failedLoginTimeout &lt;mins>]


##Arguments

<b>name</b>
Name of the virtual server to modify.

<b>IPAddress</b>
IP address of the authentication virtual server, if a single IP address is assigned to the virtual server.

<b>authentication</b>
Require users to be authenticated before sending traffic through this virtual server.
Possible values: ON, OFF
Default value: ON

<b>AuthenticationDomain</b>
Fully-qualified domain name (FQDN) of the authentication virtual server.

<b>comment</b>
Any comments associated with this virtual server.

<b>appflowLog</b>
Log AppFlow flow information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxLoginAttempts</b>
Maximum Number of login Attempts
Minimum value: 1
Maximum value: 255

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts
Minimum value: 1



##unset authentication vserver

Removes the settings of an existing authentication virtual server. Attributes for which a default value is available revert to their default values. Refer to the set authentication vserver command for descriptions of the parameters..Refer to the set authentication vserver command for meanings of the arguments.


##Synopsys

unset authentication vserver &lt;name> [-AuthenticationDomain] [-maxLoginAttempts] [-authentication] [-comment] [-appflowLog]


##bind authentication vserver

Binds authentication policies to an authentication virtual server.


##Synopsys

bind authentication vserver &lt;name> [-policy &lt;string>  [-priority &lt;positive_integer>]  [-secondary]  [-groupExtraction]  [-nextFactor &lt;string>]  [-gotoPriorityExpression &lt;expression>]]


##Arguments

<b>name</b>
Name of the authentication virtual server to which to bind the policy.

<b>policy</b>
Name of the policy to bind to the virtual server.

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Policies are evaluated in the order of their priorities, and the first policy that matches the request is applied. Must be unique within the list of policies bound to the authentication virtual server.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, 'my authentication policy' or "my authentication policy").
Minimum value: 0

<b>secondary</b>
Applicable only while bindind classic authentication policy as advance authentication policy use nFactor

<b>groupExtraction</b>
Applicable only while bindind classic authentication policy as advance authentication policy use nFactor

<b>nextFactor</b>
Applicable only while binding advance authentication policy as classic authentication policy does not support nFactor

<b>gotoPriorityExpression</b>
Applicable only to advance authentication policy. Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a priority number that is numerically higher than the highest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.



##unbind authentication vserver

Unbinds the specified policy from the specified authentication virtual server.


##Synopsys

unbind authentication vserver &lt;name> [-policy &lt;string>  [-secondary]  [-groupExtraction]]


##Arguments

<b>name</b>
Name of the virtual server.

<b>policy</b>
Name of the policy to be unbound.

<b>secondary</b>
Applicable only to classic authentication policy

<b>groupExtraction</b>
Applicable only to classic authentication policy



##enable authentication vserver

Enables an authentication virtual server that is disabled. Note: Virtual servers, when added, are normally enabled by default.


##Synopsys

enable authentication vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server to enable.



##Example

enable vserver authentication1

##disable authentication vserver

Disables an authentication virtual server, taking it out of service.


##Synopsys

disable authentication vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server to disable. 
Notes:
1.  The NetScaler appliance still responds to ARP and/or ping requests for the IP address of disabled virtual servers.
2.  Because the virtual server configuration still exists on the NetScaler appliance, you can reenable the virtual server.



##Example

disable vserver authn_vip

##show authentication vserver

Displays the configuration of the specified authentication virtual server.If no authentication virtual server is specified, displays a list of all authentication virtual servers that are currently configured on the NetScaler appliance.


##Synopsys

show authentication vserver [&lt;name>]show authentication vserver stats - alias for 'stat authentication vserver'


##Arguments

<b>name</b>
Name of the authentication virtual server.



##Outputs

<b>IPAddress</b>
The IP address of the authentication server.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>value</b>
Indicates whether or not the certificate is bound or if SSL offload is disabled.

<b>port</b>
The virtual TCP port of the authentication vserver.

<b>range</b>
The range of authentication vserver IP addresses. The new range of authentication vservers will have IP addresses consecutively numbered, starting with the primary address specified with the &lt;ipaddress> argument.

<b>serviceType</b>
The authentication vserver's protocol type, Currently the only possible value is SSL.

<b>type</b>
The type of Virtual Server, e.g. CONTENT based or ADDRESS based.

<b>state</b>
Initial state of the new virtual server.

<b>status</b>
Whether or not this vserver responds to ARPs and whether or not round-robin selection is temporarily in effect.

<b>cacheType</b>
Virtual server's cache type. The options are: TRANSPARENT, REVERSE and FORWARD.

<b>redirect</b>
The cache redirect policy.
The valid redirect policies are:
l.	CACHE - Directs all requests to the cache.
2.	POLICY - Applies cache redirection policy to determine whether the request should be directed to the cache or origin. This is the default setting.
3.	ORIGIN - Directs all requests to the origin server.

<b>precedence</b>
This argument is used only when configuring content switching on the specified virtual server. This is applicable only
if both the URL and RULE-based policies have been configured on the same virtual server.
It specifies the type of policy (URL or RULE) that takes precedence on the content switching virtual server. The default setting is RULE.
l	URL - In this case, the incoming request is matched against the URL-based policies before the rule-based policies.
l	RULE - In this case, the incoming request is matched against the rule-based policies before the URL-based policies.
For all URL-based policies, the precedence hierarchy is:
1.	Domain and exact URL
2.	Domain, prefix and suffix
3.	Domain and suffix
4.	Domain and prefix
5.	Domain only
6.	Exact URL
7.	Prefix and suffix
8.	Suffix only
9.	Prefix only
10.	Default

<b>redirectURL</b>
The URL where traffic is redirected if the virtual server in system becomes unavailable. WARNING!	Make sure that the domain you specify in the URL does not match the domain specified in the -d domainName argument of the ###add cs policy### command. If the same domain is specified in both arguments, the request will be continuously redirected to the same unavailable virtual server in the system. If so, the user may not get the requested content.

<b>authentication</b>
Indicates whether or not authentication is being applied to incoming users to the VPN.

<b>curAAAUsers</b>
The number of current users logged in to this vserver.

<b>AuthenticationDomain</b>
Fully-qualified domain name (FQDN) of the authentication virtual server.

<b>rule</b>
The name of the rule, or expression, if any, that policy for the authentication server is to use. Rules are combinations of Expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide. The default rule is ns_true.

<b>policyName</b>
The name of the policy, if any, bound to the authentication vserver.

<b>policy</b>
The name of the policy, if any, bound to the authentication vserver.

<b>serviceName</b>
The name of the service, if any, to which the vserver policy is bound.

<b>weight</b>
Weight for this service, if any. This weight is used when the system performs load balancing, giving greater priority to a specific service. It is useful when the services bound to a virtual server are of different capacity.

<b>cacheVserver</b>
The name of the default target cache virtual server, if any, to which requests are redirected.

<b>backupVServer</b>
The name of the backup vpn virtual server for this vpn virtual server.

<b>cltTimeout</b>
The idle time, if any, in seconds after which the client connection is terminated.

<b>soMethod</b>
VPN client applications are allocated from a block of Intranet IP addresses.
That block may be exhausted after a certain number of connections. This switch specifies the
method used to determine whether or not a new connection will spillover, or exhaust, the allocated block of
Intranet IP addresses for that application. Possible values are CONNECTION or DYNAMICCONNECTION.
CONNECTION means that a static integer value is the hard limit for the spillover threshold. The spillover
threshold is described below. DYNAMICCONNECTION means that the spillover threshold is set according to
the maximum number of connections defined for the vpn vserver.

<b>soThreshold</b>
VPN client applications are allocated from a block of Intranet IP addresses.
That block may be exhausted after a certain number of connections.
The value of this option is number of client connections after which the Mapped IP address is used
as the client source IP address instead of an address from the allocated block of Intranet IP addresses.

<b>soPersistence</b>
Whether or not cookie-based site persistance is enabled for this VPN vserver. Possible values are 'ConnectionProxy', HTTPRedirect, or NONE

<b>soPersistenceTimeOut</b>
The timeout, if any, for cookie-based site persistance of this VPN vserver.

<b>priority</b>
The priority, if any, of the vpn vserver policy.

<b>downStateFlush</b>
Perform delayed clean up of connections on this vserver.

<b>actType</b>

<b>disablePrimaryOnDown</b>
Tells whether traffic will continue reaching backup vservers even after primary comes UP from DOWN state.

<b>Listenpolicy</b>
Listenpolicy configured for authentication vserver

<b>Listenpriority</b>
Priority of listen policy for authentication vserver

<b>tcpProfileName</b>
The name of the TCP profile.

<b>httpProfileName</b>
Name of the HTTP profile.

<b>comment</b>
Any comments associated with this virtual server.

<b>policySubType</b>

<b>stateflag</b>

<b>flags</b>

<b>appflowLog</b>
Log AppFlow flow information.

<b>vstype</b>
Virtual Server Type, e.g. Load Balancing, Content Switch, Cache Redirection

<b>ngname</b>
Nodegroup devno to which this  authentication vsever belongs to

<b>maxLoginAttempts</b>
Maximum Number of login Attempts

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts

<b>secondary</b>
Bind the authentication policy to the secondary chain.
Provides for multifactor authentication in which a user must authenticate via both a primary authentication method and, afterward, via a secondary authentication method.
Because user groups are aggregated across authentication systems, usernames must be the same on all authentication servers. Passwords can be different.

<b>groupExtraction</b>
Bind the Authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called if primary and/or secondary authentication has succeeded.

<b>nextFactor</b>
On success invoke label.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>devno</b>

<b>count</b>



##Example

show authentication vserver

##stat authentication vserver

Displays statistics about the specified authentication virtual server. If no authentication virtual server is specified, displays statistics for all authentication virtual servers that are currently configured on the NetScaler appliance.


##Synopsys

stat authentication vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the authentication virtual server.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>IP address (IP)</b>
The IP address on which the service is running.

<b>Port (port)</b>
The port on which the service is running.

<b>Vserver protocol (Protocol)</b>
Protocol associated with the vserver

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>Requests (Req)</b>
Total number of requests received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Responses (Rsp)</b>
Number of responses received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Request bytes (Reqb)</b>
Total number of request bytes received on this service or virtual server.

<b>Response bytes (Rspb)</b>
Number of response bytes received by this service or virtual server.



##Related Commands

<ul><li><a href="../../../ation-policy.html#stat-authentication-p/ation-policy.html#stat-authentication-p">stat authentication Policy</a></li><li><a href="../../../ation-samlidppolicy.html#stat-authentication-samlidpp/ation-samlidppolicy.html#stat-authentication-samlidpp">stat authentication samlIdPPolicy</a></li><li><a href="../../../ation-policylabel.html#stat-authentication-policy/ation-policylabel.html#stat-authentication-policy">stat authentication policylabel</a></li><li><a href="../../../ation-loginschemapolicy.html#stat-authentication-loginschemap/ation-loginschemapolicy.html#stat-authentication-loginschemap">stat authentication loginSchemaPolicy</a></li></ul>



##rename authentication vserver

Rename an authentication virtual server.


##Synopsys

rename authentication vserver &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Current name of the authentication virtual server.

<b>newName</b>
New name of the authentication virtual server. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, 'my authentication policy' or "my authentication policy").



##Example

rename authentication vserver av1 av_new

