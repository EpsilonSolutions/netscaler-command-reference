#gslb vserver

The following operations can be performed on "gslb vserver":


[add](#add-gslb-vserver) | [rm](#rm-gslb-vserver) | [set](#set-gslb-vserver) | [unset](#unset-gslb-vserver) | [bind](#bind-gslb-vserver) | [unbind](#unbind-gslb-vserver) | [enable](#enable-gslb-vserver) | [disable](#disable-gslb-vserver) | [show](#show-gslb-vserver) | [stat](#stat-gslb-vserver) | [rename](#rename-gslb-vserver)

##add gslb vserver

Creates a global server load balancing (GSLB) virtual server.


##Synopsys

add gslb vserver &lt;name> &lt;serviceType> [-dnsRecordType &lt;dnsRecordType>] [-lbMethod &lt;lbMethod>] [-backupLBMethod &lt;backupLBMethod>] [-netmask &lt;netmask>] [-v6netmasklen &lt;positive_integer>] [-tolerance &lt;positive_integer>] [-persistenceType ( SOURCEIP | NONE )] [-persistenceId &lt;positive_integer>] [-persistMask &lt;netmask>] [-v6persistmasklen &lt;positive_integer>] [-timeout &lt;mins>] [-EDR ( ENABLED | DISABLED )] [-MIR ( ENABLED | DISABLED )] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-dynamicWeight &lt;dynamicWeight>] [-state ( ENABLED | DISABLED )] [-considerEffectiveState ( NONE | STATE_ONLY )] [-comment &lt;string>] [-soMethod &lt;soMethod>] [-soPersistence ( ENABLED | DISABLED )] [-soPersistenceTimeOut &lt;positive_integer>] [-soThreshold &lt;positive_integer>] [-soBackupAction &lt;soBackupAction>] [-appflowLog ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the GSLB virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the virtual server is created.
CLI Users:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').

<b>serviceType</b>
Protocol used by services bound to the virtual server.
Possible values: HTTP, FTP, TCP, UDP, SSL, SSL_BRIDGE, SSL_TCP, NNTP, ANY, SIP_UDP, SIP_TCP, SIP_SSL, RADIUS, RDP, RTSP, MYSQL, MSSQL, ORACLE

<b>dnsRecordType</b>
DNS record type to associate with the GSLB virtual server's domain name.
Possible values: A, AAAA, CNAME
Default value: A

<b>lbMethod</b>
Load balancing method for the GSLB virtual server.
Possible values: ROUNDROBIN, LEASTCONNECTION, LEASTRESPONSETIME, SOURCEIPHASH, LEASTBANDWIDTH, LEASTPACKETS, STATICPROXIMITY, RTT, CUSTOMLOAD
Default value: LEASTCONNECTION

<b>backupLBMethod</b>
Backup load balancing method. Becomes operational if the primary load balancing method fails or cannot be used. Valid only if the primary method is based on either round-trip time (RTT) or static proximity.
Possible values: ROUNDROBIN, LEASTCONNECTION, LEASTRESPONSETIME, SOURCEIPHASH, LEASTBANDWIDTH, LEASTPACKETS, STATICPROXIMITY, RTT, CUSTOMLOAD

<b>netmask</b>
IPv4 network mask for use in the SOURCEIPHASH load balancing method.
Default value: 0xFFFFFFFF

<b>v6netmasklen</b>
Number of bits to consider, in an IPv6 source IP address, for creating the hash that is required by the SOURCEIPHASH load balancing method.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>tolerance</b>
Site selection tolerance, in milliseconds, for implementing the RTT load balancing method. If a site's RTT deviates from the lowest RTT by more than the specified tolerance, the site is not considered when the NetScaler appliance makes a GSLB decision. The appliance implements the round robin method of global server load balancing between sites whose RTT values are within the specified tolerance. If the tolerance is 0 (zero), the appliance always sends clients the IP address of the site with the lowest RTT.
Minimum value: 0
Maximum value: 100

<b>persistenceType</b>
Use source IP address based persistence for the virtual server. 
After the load balancing method selects a service for the first packet, the IP address received in response to the DNS query is used for subsequent requests from the same client.
Possible values: SOURCEIP, NONE

<b>persistenceId</b>
The persistence ID for the GSLB virtual server. The ID is a positive integer that enables GSLB sites to identify the GSLB virtual server, and is required if source IP address based or spill over based persistence is enabled on the virtual server.
Minimum value: 0
Maximum value: 65535

<b>persistMask</b>
The optional IPv4 network mask applied to IPv4 addresses to establish source IP address based persistence.
Default value: 0xFFFFFFFF

<b>v6persistmasklen</b>
Number of bits to consider in an IPv6 source IP address when creating source IP address based persistence sessions.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>timeout</b>
Idle time, in minutes, after which a persistence entry is cleared.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>EDR</b>
Send clients an empty DNS response when the GSLB virtual server is DOWN.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>MIR</b>
Include multiple IP addresses in the DNS responses sent to clients.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>disablePrimaryOnDown</b>
Continue to direct traffic to the backup chain even after the primary GSLB virtual server returns to the UP state. Used when spillover is configured for the virtual server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dynamicWeight</b>
Specify if the appliance should consider the service count, service weights, or ignore both when using weight-based load balancing methods. The state of the number of services bound to the virtual server help the appliance to select the service.
Possible values: SERVICECOUNT, SERVICEWEIGHT, DISABLED
Default value: DISABLED

<b>state</b>
State of the GSLB virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>considerEffectiveState</b>
If the primary state of all bound GSLB services is DOWN, consider the effective states of all the GSLB services, obtained through the Metrics Exchange Protocol (MEP), when determining the state of the GSLB virtual server. To consider the effective state, set the parameter to STATE_ONLY. To disregard the effective state, set the parameter to NONE. 
The effective state of a GSLB service is the ability of the corresponding virtual server to serve traffic. The effective state of the load balancing virtual server, which is transferred to the GSLB service, is UP even if only one virtual server in the backup chain of virtual servers is in the UP state.
Possible values: NONE, STATE_ONLY
Default value: NONE

<b>comment</b>
Any comments that you might want to associate with the GSLB virtual server.

<b>soMethod</b>
Type of threshold that, when exceeded, triggers spillover. Available settings function as follows:
* CONNECTION - Spillover occurs when the number of client connections exceeds the threshold.
* DYNAMICCONNECTION - Spillover occurs when the number of client connections at the GSLB virtual server exceeds the sum of the maximum client (Max Clients) settings for bound GSLB services. Do not specify a spillover threshold for this setting, because the threshold is implied by the Max Clients settings of the bound GSLB services.
* BANDWIDTH - Spillover occurs when the bandwidth consumed by the GSLB virtual server's incoming and outgoing traffic exceeds the threshold. 
* HEALTH - Spillover occurs when the percentage of weights of the GSLB services that are UP drops below the threshold. For example, if services gslbSvc1, gslbSvc2, and gslbSvc3 are bound to a virtual server, with weights 1, 2, and 3, and the spillover threshold is 50%, spillover occurs if gslbSvc1 and gslbSvc3 or gslbSvc2 and gslbSvc3 transition to DOWN. 
* NONE - Spillover does not occur.
Possible values: CONNECTION, DYNAMICCONNECTION, BANDWIDTH, HEALTH, NONE

<b>soPersistence</b>
If spillover occurs, maintain source IP address based persistence for both primary and backup GSLB virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>soPersistenceTimeOut</b>
Timeout for spillover persistence, in minutes.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>soThreshold</b>
Threshold at which spillover occurs. Specify an integer for the CONNECTION spillover method, a bandwidth value in kilobits per second for the BANDWIDTH method (do not enter the units), or a percentage for the HEALTH method (do not enter the percentage symbol).
Minimum value: 1
Maximum value: 4294967287

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists
Possible values: DROP, ACCEPT, REDIRECT

<b>appflowLog</b>
Enable logging appflow flow information
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

add gslb vserver gvip http

##rm gslb vserver

Removes a global server load balancing (GSLB) virtual server configured on the appliance.


##Synopsys

rm gslb vserver &lt;name>


##Arguments

<b>name</b>
Name of the GSLB virtual server to remove.



##Example

rm gslb vserver gvip

##set gslb vserver

Modifies the specified parameters of a global server load balancing (GSLB) virtual server.


##Synopsys

set gslb vserver &lt;name> [-dnsRecordType &lt;dnsRecordType>] [-backupVServer &lt;string>] [-lbMethod &lt;lbMethod>] [-backupLBMethod &lt;backupLBMethod>] [-netmask &lt;netmask>] [-v6netmasklen &lt;positive_integer>] [-tolerance &lt;positive_integer>] [-persistenceType ( SOURCEIP | NONE )] [-persistenceId &lt;positive_integer>] [-persistMask &lt;netmask>] [-v6persistmasklen &lt;positive_integer>] [-timeout &lt;mins>] [-EDR ( ENABLED | DISABLED )] [-MIR ( ENABLED | DISABLED )] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-dynamicWeight &lt;dynamicWeight>] [-considerEffectiveState ( NONE | STATE_ONLY )] [-soMethod &lt;soMethod>] [-soPersistence ( ENABLED | DISABLED )] [-soPersistenceTimeOut &lt;positive_integer>] [-soThreshold &lt;positive_integer>] [-soBackupAction &lt;soBackupAction>] [-serviceName &lt;string>  -weight &lt;positive_integer>] [-domainName &lt;string>  [-TTL &lt;secs>]  [-backupIP &lt;ip_addr|ipv6_addr|*>]  [-cookieDomain &lt;string>]  [-cookieTimeout &lt;mins>]  [-sitedomainTTL &lt;secs>]] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the GSLB virtual server.

<b>dnsRecordType</b>
DNS record type to associate with the GSLB virtual server's domain name.
Possible values: A, AAAA, CNAME
Default value: A

<b>backupVServer</b>
Name of the backup GSLB virtual server to which the appliance should to forward requests if the status of the primary GSLB virtual server is down or exceeds its spillover threshold.

<b>lbMethod</b>
Load balancing method for the GSLB virtual server.
Possible values: ROUNDROBIN, LEASTCONNECTION, LEASTRESPONSETIME, SOURCEIPHASH, LEASTBANDWIDTH, LEASTPACKETS, STATICPROXIMITY, RTT, CUSTOMLOAD
Default value: LEASTCONNECTION

<b>backupLBMethod</b>
Backup load balancing method. Becomes operational if the primary load balancing method fails or cannot be used. Valid only if the primary method is based on either round-trip time (RTT) or static proximity.
Possible values: ROUNDROBIN, LEASTCONNECTION, LEASTRESPONSETIME, SOURCEIPHASH, LEASTBANDWIDTH, LEASTPACKETS, STATICPROXIMITY, RTT, CUSTOMLOAD

<b>netmask</b>
IPv4 network mask for use in the SOURCEIPHASH load balancing method.
Default value: 0xFFFFFFFF

<b>v6netmasklen</b>
Number of bits to consider, in an IPv6 source IP address, for creating the hash that is required by the SOURCEIPHASH load balancing method.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>tolerance</b>
Site selection tolerance, in milliseconds, for implementing the RTT load balancing method. If a site's RTT deviates from the lowest RTT by more than the specified tolerance, the site is not considered when the NetScaler appliance makes a GSLB decision. The appliance implements the round robin method of global server load balancing between sites whose RTT values are within the specified tolerance. If the tolerance is 0 (zero), the appliance always sends clients the IP address of the site with the lowest RTT.
Minimum value: 0
Maximum value: 100

<b>persistenceType</b>
Persistence type for the virtual server. Possible value for this parameter is SOURCEIP, which specifies persistence based on the source IP address of inbound packets. After the load balancing method selects a link for transmission of the first packet, the IP address received in response to the DNS query is used for subsequent requests from the same client.
Possible values: SOURCEIP, NONE

<b>persistenceId</b>
The persistence ID for the GSLB virtual server. The ID is a positive integer that enables GSLB sites to identify the GSLB virtual server, and is required if source IP address based or spill over based persistence is enabled on the virtual server.
Minimum value: 0
Maximum value: 65535

<b>persistMask</b>
The optional IPv4 network mask applied to IPv4 addresses to establish source IP address based persistence.
Default value: 0xFFFFFFFF

<b>v6persistmasklen</b>
Number of bits to consider in an IPv6 source IP address when creating source IP address based persistence sessions.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>timeout</b>
Idle time, in minutes, after which a persistence entry is cleared.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>EDR</b>
Send clients an empty DNS response when the GSLB virtual server is DOWN.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>MIR</b>
Include multiple IP addresses in the DNS responses sent to clients.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>disablePrimaryOnDown</b>
Continue to direct traffic to the backup chain even after the primary GSLB virtual server returns to the UP state. Used when spillover is configured for the virtual server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dynamicWeight</b>
Specify if the appliance should consider the service count, service weights, or ignore both when using weight-based load balancing methods. The state of the number of services bound to the virtual server help the appliance to select the service.
Possible values: SERVICECOUNT, SERVICEWEIGHT, DISABLED
Default value: DISABLED

<b>considerEffectiveState</b>
If the primary state of all bound GSLB services is DOWN, consider the effective states of all the GSLB services, obtained through the Metrics Exchange Protocol (MEP), when determining the state of the GSLB virtual server. To consider the effective state, set the parameter to STATE_ONLY. To disregard the effective state, set the parameter to NONE. 
The effective state of a GSLB service is the ability of the corresponding virtual server to serve traffic. The effective state of the load balancing virtual server, which is transferred to the GSLB service, is UP even if only one virtual server in the backup chain of virtual servers is in the UP state.
Possible values: NONE, STATE_ONLY
Default value: NONE

<b>soMethod</b>
Type of threshold that, when exceeded, triggers spillover. Available settings function as follows:
* CONNECTION - Spillover occurs when the number of client connections exceeds the threshold.
* DYNAMICCONNECTION - Spillover occurs when the number of client connections at the GSLB virtual server exceeds the sum of the maximum client (Max Clients) settings for bound GSLB services. Do not specify a spillover threshold for this setting, because the threshold is implied by the Max Clients settings of the bound GSLB services.
* BANDWIDTH - Spillover occurs when the bandwidth consumed by the GSLB virtual server's incoming and outgoing traffic exceeds the threshold. 
* HEALTH - Spillover occurs when the percentage of weights of the GSLB services that are UP drops below the threshold. For example, if services gslbSvc1, gslbSvc2, and gslbSvc3 are bound to a virtual server, with weights 1, 2, and 3, and the spillover threshold is 50%, spillover occurs if gslbSvc1 and gslbSvc3 or gslbSvc2 and gslbSvc3 transition to DOWN. 
* NONE - Spillover does not occur.
Possible values: CONNECTION, DYNAMICCONNECTION, BANDWIDTH, HEALTH, NONE

<b>soPersistence</b>
If spillover occurs, maintain source IP address based persistence for both primary and backup GSLB virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>soPersistenceTimeOut</b>
Timeout for spillover persistence, in minutes.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>soThreshold</b>
Threshold at which spillover occurs. Specify an integer for the CONNECTION spillover method, a bandwidth value in kilobits per second for the BANDWIDTH method (do not enter the units), or a percentage for the HEALTH method (do not enter the percentage symbol).
Minimum value: 1
Maximum value: 4294967287

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists
Possible values: DROP, ACCEPT, REDIRECT

<b>serviceName</b>
Name of the GSLB service for which to change the weight.

<b>weight</b>
Weight to assign to the GSLB service.
Minimum value: 1
Maximum value: 100

<b>domainName</b>
Domain name for which to change the time to live (TTL) and/or backup service IP address.

<b>TTL</b>
Time to live (TTL) for the domain.
Minimum value: 1

<b>backupIP</b>
The IP address of the backup service for the specified domain name. Used when all the services bound to the domain are down, or when the backup chain of virtual servers is down.

<b>cookieDomain</b>
The cookie domain for the GSLB site. Used when inserting the GSLB site cookie in the HTTP response.

<b>cookieTimeout</b>
Timeout, in minutes, for the GSLB site cookie.
Maximum value: 1440

<b>sitedomainTTL</b>
TTL, in seconds, for all internally created site domains (created when a site prefix is configured on a GSLB service) that are associated with this virtual server.
Minimum value: 1

<b>comment</b>
Any comments that you might want to associate with the GSLB virtual server.

<b>appflowLog</b>
Enable logging appflow flow information
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set gslb vserver gvip -persistenceType SOURCEIP

##unset gslb vserver

Removes the specified settings from the specified global server load balancing (GSLB) virtual server. Attributes for which a default value is available revert to their default values..Refer to the set gslb vserver command for meanings of the arguments.


##Synopsys

unset gslb vserver &lt;name>@ [-backupVServer] [-dnsRecordType] [-lbMethod] [-backupLBMethod] [-netmask] [-v6netmasklen] [-tolerance] [-persistenceType] [-persistenceId] [-persistMask] [-v6persistmasklen] [-timeout] [-EDR] [-MIR] [-disablePrimaryOnDown] [-dynamicWeight] [-considerEffectiveState] [-soMethod] [-soPersistence] [-soPersistenceTimeOut] [-soBackupAction] [-serviceName] [-weight] [-comment] [-appflowLog]


##Example

unset gslb vserver lb_vip -backupVServer	For multiple gslb vservers the command is:	unset gslb vserver lb_vip[1-3] -backupVServer

##bind gslb vserver

Binds a domain, service, backup IP address, or cookie domain to a GSLB virtual server.


##Synopsys

bind gslb vserver &lt;name> ((-serviceName &lt;string>  [-weight &lt;positive_integer>]  ) | (-domainName &lt;string>  [-TTL &lt;secs>]  [-backupIP &lt;ip_addr|ipv6_addr|*>]  [-cookieDomain &lt;string>]  [-cookieTimeout &lt;mins>]  [-sitedomainTTL &lt;secs>]) | (-policyName &lt;string>@  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]  [-type ( REQUEST | RESPONSE )]))


##Arguments

<b>name</b>
Name of the virtual server on which to perform the binding operation.

<b>serviceName</b>
Name of the GSLB service for which to change the weight.

<b>weight</b>
Weight to assign to the GSLB service.
Default value: 1
Minimum value: 1
Maximum value: 100

<b>domainName</b>
Domain name for which to change the time to live (TTL) and/or backup service IP address.

<b>TTL</b>
Time to live (TTL) for the domain.
Minimum value: 1

<b>backupIP</b>
The IP address of the backup service for the specified domain name. Used when all the services bound to the domain are down, or when the backup chain of virtual servers is down.

<b>cookieDomain</b>
The cookie domain for the GSLB site. Used when inserting the GSLB site cookie in the HTTP response.

<b>cookieTimeout</b>
Timeout, in minutes, for the GSLB site cookie.

<b>sitedomainTTL</b>
TTL, in seconds, for all internally created site domains (created when a site prefix is configured on a GSLB service) that are associated with this virtual server.
Default value: 3600
Minimum value: 1

<b>policyName</b>
Name of the policy bound to the GSLB vserver.

<b>priority</b>
Priority.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.
	o	If gotoPriorityExpression is not present or if it is equal to END then the policy bank evaluation ends here
	o	Else if the gotoPriorityExpression is equal to NEXT then the next policy in the priority order is evaluated.
	o	Else gotoPriorityExpression is evaluated. The result of gotoPriorityExpression (which has to be a number) is processed as follows:
		-	An UNDEF event is triggered if
			.	gotoPriorityExpression cannot be evaluated
			.	gotoPriorityExpression evaluates to number which is smaller than the maximum priority in the policy bank but is not same as any policy's priority
			.	gotoPriorityExpression evaluates to a priority that is smaller than the current policy's priority
		-	If the gotoPriorityExpression evaluates to the priority of the current policy then the next policy in the priority order is evaluated.
		-	If the gotoPriorityExpression evaluates to the priority of a policy further ahead in the list then that policy will be evaluated next.
		This field is applicable only to rewrite and responder policies.

<b>type</b>
Bind point to which to bind the policy.
Possible values: REQUEST, RESPONSE



##Example

bind gslb vserver gvip -domainName www.mynw.com

##unbind gslb vserver

Unbinds the domain or service from the GSLB virtual server.


##Synopsys

unbind gslb vserver &lt;name> (-serviceName &lt;string> | (-domainName &lt;string>  [-backupIP]  [-cookieDomain]) | -policyName &lt;string>@)


##Arguments

<b>name</b>
Name of the GSLB virtual server.

<b>serviceName</b>
Name of the GSLB service for which to change the weight.

<b>domainName</b>
Domain name for which to change the time to live (TTL) and/or backup service IP address.

<b>backupIP</b>
The IP address of the backup service for the specified domain name. Used when all the services bound to the domain are down, or when the backup chain of virtual servers is down.

<b>cookieDomain</b>
The cookie domain for the GSLB site. Used when inserting the GSLB site cookie in the HTTP response.

<b>policyName</b>
The policy that has been bound to this load balancing virtual server, using the ###bind gslb vserver### command.



##Example

unbind gslb vserver gvip -domainName www.mynw.com

##enable gslb vserver

Enables a global server load balancing (GSLB) virtual server that has been disabled. (A GSLB virtual server is enabled by default.)


##Synopsys

enable gslb vserver &lt;name>@


##Arguments

<b>name</b>
Name of the GSLB virtual server to enable.



##Example

enable gslb vserver gslb_vip	To enable multiple gslb vservers use the following command:	enable gslb vserver gslb_vip[1-3]

##disable gslb vserver

Disables a global server load balancing (GSLB) virtual server and takes it out of service.


##Synopsys

disable gslb vserver &lt;name>@


##Arguments

<b>name</b>
Name of the GSLB virtual server to disable.



##Example

disable gslb vserver gslb_vip	To disable multiple gslb vservers use the following command:        disable gslb vserver gslb_vip[1-3]

##show gslb vserver

Displays the parameters of all the global server load balancing (GSLB) virtual servers configured on the appliance, or the parameters of the specified GSLB virtual server.


##Synopsys

show gslb vserver [&lt;name>]show gslb vserver stats - alias for 'stat gslb vserver'


##Arguments

<b>name</b>
Name of the GSLB virtual server.



##Outputs

<b>serviceType</b>
Protocol used by services bound to the virtual server.

<b>state</b>
State of the gslb vserver.

<b>ipType</b>
The IP type for this GSLB vserver.

<b>dnsRecordType</b>
The IP type for this GSLB vserver.

<b>persistenceType</b>
Indicates if persistence is set on the gslb vserver

<b>persistenceId</b>
Persistence id of the gslb vserver

<b>lbMethod</b>
The load balancing method set for the virtual server

<b>backupLBMethod</b>
Indicates the backup method in case the primary fails

<b>tolerance</b>
Indicates the deviation we can tolerate when we have the LB method as RTT

<b>timeout</b>
Idle timeout for persistence entries.

<b>netmask</b>
The netmask used in the SOURCEIPHASH policy.

<b>v6netmasklen</b>
The netmask used for ipv6 traffic in the SOURCE/DEST IPHASH policy.

<b>persistMask</b>
The netmask used while SOURCEIP based persistency is ENABLED.

<b>v6persistmasklen</b>
The netmask applied for ipv6 traffic when the persistency type is SOURCEIP.

<b>serviceName</b>
The service name.

<b>weight</b>
Weight for the service.

<b>domainName</b>
The name of the domain for which TTL and/or backupIP has changed.

<b>TTL</b>
TTL for the given domain.

<b>backupIP</b>
Backup IP for the given domain.

<b>cookieDomain</b>
The cookie domain for the GSLB domain. This will be used when inserting the GSLB site cookie in the HTTP response. By default, cookie domain will not be inserted.

<b>cookieTimeout</b>
Time out value of the cookie in minutes

<b>sitedomainTTL</b>
Site domain TTL.

<b>IPAddress</b>
IP address.

<b>port</b>
Port number.

<b>status</b>
Current status of the gslb vserver. During the initial phase if the configured lb method is not round robin , the vserver will adopt round robin to distribute traffic for a predefined number of requests.

<b>lbrrreason</b>
Reason why a vserver is in RR. The following are the reasons:
1  - MEP is DOWN (GSLB)
2  - LB method has changed
3  - Bound service's state changed to UP
4  - A new service is bound
5  - Startup RR factor has changed
6  - LB feature is enabled
7  - Load monitor is not active on a service
8  - Vserver is Enabled
9  - SSL feature is Enabled
10 - All bound services have reached threshold. Using effective state to load balance (GSLB)
11 - Primary state of bound services are not UP. Using effective state to load balance (GSLB)
12 - No LB decision can be made as all bound services have either reached threshold or are not UP (GSLB)
13 - All load monitors are active

<b>preferredLocation</b>
The target site to be returned in the DNS response when a policy is successfully evaluated against the incoming DNS request. Target site is specified in dotted notation with up to 6 qualifiers. Wildcard `*' is accepted as a valid qualifier token.

<b>backupVServer</b>
Backup vserver in case the primary fails

<b>backupSessionTimeout</b>
A non zero value enables the feature. The minimum value is 2 minutes. To disable the feature set the value to zero. The created session is in effect for a specific client per domain.

<b>EDR</b>
Indicates if Empty Down Response is enabled/disabled

<b>MIR</b>
Indicates if Multi IP Response is enabled/disabled

<b>disablePrimaryOnDown</b>
Continue to direct traffic to the backup chain even after the primary GSLB virtual server returns to the UP state. Used when spillover is configured for the virtual server.

<b>dynamicWeight</b>
Dynamic weight method. Possible values are, the svc count or the svc weights or ignore both.

<b>isCname</b>
is cname feature set on vserver

<b>cumulativeWeight</b>
Cumulative weight is the weight of GSLB service considering both its configured weight and dynamic weight. It is equal to product of dynamic weight and configured weight of the gslb service

<b>dynamicConfWt</b>
Weight obtained by the virtue of bound service count or weight

<b>thresholdValue</b>
Tells whether threshold exceeded for this service participating in CUSTOMLB

<b>sitePersistence</b>
Type of Site Persistence set

<b>svrEffGslbState</b>
Effective state of the gslb svc

<b>gslbthreshold</b>
Indicates if gslb svc has reached threshold

<b>considerEffectiveState</b>
If the primary state of all bound GSLB services is DOWN, consider the effective states of all the GSLB services, obtained through the Metrics Exchange Protocol (MEP), when determining the state of the GSLB virtual server. To consider the effective state, set the parameter to STATE_ONLY. To disregard the effective state, set the parameter to NONE. 
The effective state of a GSLB service is the ability of the corresponding virtual server to serve traffic. The effective state of the load balancing virtual server, which is transferred to the GSLB service, is UP even if only one virtual server in the backup chain of virtual servers is in the UP state.

<b>cnameEntry</b>
The cname of the gslb service.

<b>totalServices</b>
Total number of services bound to the vserver.

<b>activeServices</b>
Total number of active services bound to the vserver.

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>stateChangeTimemSec</b>
Time at which last state change happened. Milliseconds part.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>comment</b>
Any comments that you might want to associate with the GSLB virtual server.

<b>soPersistenceTimeOut</b>
Timeout for spillover persistence, in minutes.

<b>soMethod</b>
Type of threshold that, when exceeded, triggers spillover. Available settings function as follows:
* CONNECTION - Spillover occurs when the number of client connections exceeds the threshold.
* DYNAMICCONNECTION - Spillover occurs when the number of client connections at the GSLB virtual server exceeds the sum of the maximum client (Max Clients) settings for bound GSLB services. Do not specify a spillover threshold for this setting, because the threshold is implied by the Max Clients settings of the bound GSLB services.
* BANDWIDTH - Spillover occurs when the bandwidth consumed by the GSLB virtual server's incoming and outgoing traffic exceeds the threshold. 
* HEALTH - Spillover occurs when the percentage of weights of the GSLB services that are UP drops below the threshold. For example, if services gslbSvc1, gslbSvc2, and gslbSvc3 are bound to a virtual server, with weights 1, 2, and 3, and the spillover threshold is 50%, spillover occurs if gslbSvc1 and gslbSvc3 or gslbSvc2 and gslbSvc3 transition to DOWN. 
* NONE - Spillover does not occur.

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists

<b>soPersistence</b>
If spillover occurs, maintain source IP address based persistence for both primary and backup GSLB virtual servers.

<b>soThreshold</b>
Threshold at which spillover occurs. Specify an integer for the CONNECTION spillover method, a bandwidth value in kilobits per second for the BANDWIDTH method (do not enter the units), or a percentage for the HEALTH method (do not enter the percentage symbol).

<b>health</b>
Health of vserver based on percentage of weights of active svcs/all svcs. This does not consider administratively disabled svcs

<b>stateflag</b>
stateflag

<b>appflowLog</b>
Enable logging appflow flow information

<b>policyName</b>
Name of the policy bound to the GSLB vserver.

<b>priority</b>
Priority.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.
	o	If gotoPriorityExpression is not present or if it is equal to END then the policy bank evaluation ends here
	o	Else if the gotoPriorityExpression is equal to NEXT then the next policy in the priority order is evaluated.
	o	Else gotoPriorityExpression is evaluated. The result of gotoPriorityExpression (which has to be a number) is processed as follows:
		-	An UNDEF event is triggered if
			.	gotoPriorityExpression cannot be evaluated
			.	gotoPriorityExpression evaluates to number which is smaller than the maximum priority in the policy bank but is not same as any policy's priority
			.	gotoPriorityExpression evaluates to a priority that is smaller than the current policy's priority
		-	If the gotoPriorityExpression evaluates to the priority of the current policy then the next policy in the priority order is evaluated.
		-	If the gotoPriorityExpression evaluates to the priority of a policy further ahead in the list then that policy will be evaluated next.
		This field is applicable only to rewrite and responder policies.

<b>type</b>
The bindpoint to which the policy is bound

<b>vsvrbindsvcip</b>
used for showing the ip of bound entities

<b>vsvrbindsvcport</b>
used for showing ports of bound entities

<b>gslbBoundSvcType</b>
Protocol used by services bound to the GSLBvirtual server.

<b>sitePersistCookie</b>
This field is introduced for displaying the cookie in cluster setup.

<b>svcSitePersistence</b>
Type of Site Persistence set on the bound service

<b>devno</b>

<b>count</b>



##Example

show gslb vserver gvip

##stat gslb vserver

Displays statistics associated with a global server load balancing (GSLB) virtual server.


##Synopsys

stat gslb vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the GSLB virtual server for which to display statistics. If you do not specify a name, statistics are displayed for all GSLB virtual servers.

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

<b>Current Client Est connections (ClntEstConn)</b>
Number of client connections in ESTABLISHED state.

<b>total INACTIVE services (inactSvcs)</b>
number of INACTIVE services bound to a vserver

<b>Vserver Health (Health)</b>
Health of the vserver. This gives percentage of UP services bound to this vserver.

<b>Vserver protocol (Protocol)</b>
Protocol associated with the vserver

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>total ACTIVE services (actSvcs)</b>
number of ACTIVE services bound to a vserver

<b>Vserver hits (Hits)</b>
Total vserver hits

<b>Request bytes (Reqb)</b>
Total number of request bytes received on this service or virtual server.

<b>Response bytes (Rspb)</b>
Number of response bytes received by this service or virtual server.

<b>Spill Over Threshold (SOThresh)</b>
Spill Over Threshold set on the VServer.

<b>Spill Over Hits (NumSo )</b>
Number of times vserver experienced spill over.

<b>Vserver Down Backup Hits (VserverDownBackupHits )</b>
Number of times traffic was diverted to backup vserver since primary vserver was DOWN.

<b>Requests (Req)</b>
Total number of requests received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Responses (Rsp)</b>
Number of responses received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Current client connections (ClntConn)</b>
Number of current client connections.

<b>Current server connections (SvrConn)</b>
Number of current connections to the actual servers behind the virtual server.

<b>Current Server Est connections (SvrEstConn)</b>
Number of server connections in ESTABLISHED state.



##Related Commands

<ul><li><a href="../../../-gslb/-gslb">stat gslb site</a></li><li><a href="../../../tat-gslb-se/tat-gslb-se">stat gslb service</a></li><li><a href="../../../at-gslb-d/at-gslb-d">stat gslb domain</a></li></ul>



##rename gslb vserver

Renames a global server load balancing (GSLB) virtual server.


##Synopsys

rename gslb vserver &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the GSLB virtual server.

<b>newName</b>
New name for the GSLB virtual server.



##Example

rename gslb vserver gsl_vsvr gslb_vsvr_new

