#cr vserver

The following operations can be performed on "cr vserver":


[add](#add-cr-vserver) | [rm](#rm-cr-vserver) | [set](#set-cr-vserver) | [unset](#unset-cr-vserver) | [bind](#bind-cr-vserver) | [unbind](#unbind-cr-vserver) | [enable](#enable-cr-vserver) | [disable](#disable-cr-vserver) | [show](#show-cr-vserver) | [stat](#stat-cr-vserver) | [rename](#rename-cr-vserver)

##add cr vserver

Creates a cache redirection virtual server.


##Synopsys

add cr vserver &lt;name> [-td &lt;positive_integer>] &lt;serviceType> [&lt;IPAddress>  &lt;port>  [-range &lt;positive_integer>]] [-cacheType &lt;cacheType>] [-redirect &lt;redirect>] [-onPolicyMatch ( CACHE | ORIGIN )] [-redirectURL &lt;URL>] [-cltTimeout &lt;secs>] [-precedence ( RULE | URL )] [-arp ( ON | OFF )] [-map ( ON | OFF )] [-format ( ON | OFF )] [-via ( ON | OFF )] [-dnsVserverName &lt;string>] [-destinationVServer &lt;string>] [-domain &lt;string>] [-soPersistenceTimeOut &lt;positive_integer>] [-soThreshold &lt;positive_integer>] [-reuse ( ON | OFF )] [-state ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-backupVServer &lt;string>] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-l2Conn ( ON | OFF )] [-backendssl ( ENABLED | DISABLED )] [-Listenpolicy &lt;expression>  [-Listenpriority &lt;positive_integer>]] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-comment &lt;string>] [-srcIPExpr &lt;expression>] [-originUSIP ( ON | OFF )] [-usePortRange ( ON | OFF )] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )]


##Arguments

<b>name</b>
Name for the cache redirection virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the cache redirection virtual server is created.
The following requirement applies only to the NetScaler CLI:  
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my server? or ?my server?).

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>serviceType</b>
Protocol (type of service) handled by the virtual server.
Possible values: HTTP, SSL, NNTP

<b>IPAddress</b>
IPv4 or IPv6 address of the cache redirection virtual server. Usually a public IP address. Clients send connection requests to this IP address.
Note: For a transparent cache redirection virtual server, use an asterisk (*) to specify a wildcard virtual server address.

<b>cacheType</b>
Mode of operation for the cache redirection virtual server. Available settings function as follows:
* TRANSPARENT - Intercept all traffic flowing to the appliance and apply cache redirection policies to determine whether content should be served from the cache or from the origin server.
* FORWARD - Resolve the hostname of the incoming request, by using a DNS server, and forward requests for non-cacheable content to the resolved origin servers. Cacheable requests are sent to the configured cache servers.
* REVERSE - Configure reverse proxy caches for specific origin servers. Incoming traffic directed to the reverse proxy can either be served from a cache server or be sent to the origin server with or without modification to the URL.
Possible values: TRANSPARENT, REVERSE, FORWARD
Default value: CRD_TRANSPARENT

<b>redirect</b>
Type of cache server to which to redirect HTTP requests. Available settings function as follows:
* CACHE - Direct all requests to the cache.
* POLICY - Apply the cache redirection policy to determine whether the request should be directed to the cache or to the origin.
* ORIGIN - Direct all requests to the origin server.
Possible values: CACHE, POLICY, ORIGIN
Default value: CRD_POLICY

<b>onPolicyMatch</b>
Redirect requests that match the policy to either the cache or the origin server, as specified.
Note: For this option to work, you must set the cache redirection type to POLICY.
Possible values: CACHE, ORIGIN
Default value: CRD_ORIGIN

<b>redirectURL</b>
URL of the server to which to redirect traffic if the cache redirection virtual server configured on the NetScaler appliance becomes unavailable.

<b>cltTimeout</b>
Time-out value, in seconds, after which to terminate an idle client connection.
Maximum value: 31536000

<b>precedence</b>
Type of policy (URL or RULE) that takes precedence on the cache redirection virtual server. Applies only to cache redirection virtual servers that have both URL and RULE based policies. If you specify URL, URL based policies are applied first, in the following order:
1.   Domain and exact URL
2.   Domain, prefix and suffix
3.   Domain and suffix
4.   Domain and prefix
5.   Domain only
6.   Exact URL
7.   Prefix and suffix
8.   Suffix only
9.   Prefix only
10.  Default
If you specify RULE, the rule based policies are applied before URL based policies are applied.
Possible values: RULE, URL
Default value: CS_PRIORITY_RULE

<b>arp</b>
Use ARP to determine the destination MAC address.
Possible values: ON, OFF

<b>ghost</b>

<b>map</b>
Obsolete.
Possible values: ON, OFF

<b>format</b>

<b>via</b>
Insert a via header in each HTTP request. In the case of a cache miss, the request is redirected from the cache server to the origin server. This header indicates whether the request is being sent from a cache server.
Possible values: ON, OFF
Default value: ON

<b>cacheVserver</b>
Name of the default cache virtual server to which to redirect requests (the default target of the cache redirection virtual server).

<b>dnsVserverName</b>
Name of the DNS virtual server that resolves domain names arriving at the forward proxy virtual server.
Note: This parameter applies only to forward proxy virtual servers, not reverse or transparent.

<b>destinationVServer</b>
Destination virtual server for a transparent or forward proxy cache redirection virtual server.

<b>domain</b>
Default domain for reverse proxies. Domains are configured to direct an incoming request from a specified source domain to a specified target domain. There can be several configured pairs of source and target domains. You can select one pair to be the default. If the host header or URL of an incoming request does not include a source domain, this option sends the request to the specified target domain.

<b>soPersistenceTimeOut</b>
Time-out, in minutes, for spillover persistence.
Minimum value: 2
Maximum value: 24

<b>soThreshold</b>
For CONNECTION (or) DYNAMICCONNECTION spillover, the number of connections above which the virtual server enters spillover mode. For BANDWIDTH spillover, the amount of incoming and outgoing traffic (in Kbps) before spillover. For HEALTH spillover, the percentage of active services (by weight) below which spillover occurs.
Minimum value: 1

<b>reuse</b>
Reuse TCP connections to the origin server across client connections. Do not set this parameter unless the Service Type parameter is set to HTTP. If you set this parameter to OFF, the possible settings of the Redirect parameter function as follows:
* CACHE - TCP connections to the cache servers are not reused.
* ORIGIN - TCP connections to the origin servers are not reused. 
* POLICY - TCP connections to the origin servers are not reused.
If you set the Reuse parameter to ON, connections to origin servers and connections to cache servers are reused.
Possible values: ON, OFF
Default value: ON

<b>state</b>
Initial state of the cache redirection virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>downStateFlush</b>
Perform delayed cleanup of connections to this virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>backupVServer</b>
Name of the backup virtual server to which traffic is forwarded if the active server becomes unavailable.

<b>disablePrimaryOnDown</b>
Continue sending traffic to a backup virtual server even after the primary virtual server comes UP from the DOWN state.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>l2Conn</b>
Use L2 parameters, such as MAC, VLAN, and channel to identify a connection.
Possible values: ON, OFF

<b>backendssl</b>
Decides whether the backend connection made by NS to the origin server will be HTTP or SSL. Applicable only for SSL type CR Forward proxy vserver.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>Listenpolicy</b>
String specifying the listen policy for the cache redirection virtual server. Can be either an in-line expression or the name of a named expression.
Default value: "none"

<b>Listenpriority</b>
Priority of the listen policy specified by the Listen Policy parameter. The lower the number, higher the priority.
Default value: 101
Maximum value: 100

<b>tcpProfileName</b>
Name of the profile containing TCP configuration information for the cache redirection virtual server.

<b>httpProfileName</b>
Name of the profile containing HTTP configuration information for cache redirection virtual server.

<b>comment</b>
Comments associated with this virtual server.

<b>srcIPExpr</b>
Expression used to extract the source IP addresses from the requests originating from the cache. Can be either an in-line expression or the name of a named expression.

<b>originUSIP</b>
Use the client?s IP address as the source IP address in requests sent to the origin server.  
Note: You can enable this parameter to implement fully transparent CR deployment.
Possible values: ON, OFF
Default value: OFF

<b>usePortRange</b>
Use a port number from the port range (set by using the set ns param command, or in the Create Virtual Server (Cache Redirection) dialog box) as the source port in the requests sent to the origin server.
Possible values: ON, OFF
Default value: OFF

<b>appflowLog</b>
Enable logging of AppFlow information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Name of the network profile containing network configurations for the cache redirection virtual server.

<b>icmpVsrResponse</b>
Criterion for responding to PING requests sent to this virtual server. If ACTIVE, respond only if the virtual server is available. If PASSIVE, respond even if the virtual server is not available.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance, injects even if one virtual server set to ACTIVE is UP.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE



##rm cr vserver

Removes a virtual server.


##Synopsys

rm cr vserver &lt;name>@ ...


##Arguments

<b>name</b>
Name of the virtual server to be removed.



##Example

rm vserver cr_vip

##set cr vserver

Changes the specified settings of the cache redirection virtual server.


##Synopsys

set cr vserver &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr|*>] [-redirect &lt;redirect>] [-onPolicyMatch ( CACHE | ORIGIN )] [-precedence ( RULE | URL )] [-arp ( ON | OFF )] [-via ( ON | OFF )] [-dnsVserverName &lt;string>] [-destinationVServer &lt;string>] [-domain &lt;string>] [-reuse ( ON | OFF )] [-backupVServer &lt;string>] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-redirectURL &lt;URL>] [-cltTimeout &lt;secs>] [-downStateFlush ( ENABLED | DISABLED )] [-l2Conn ( ON | OFF )] [-backendssl ( ENABLED | DISABLED )] [-Listenpolicy &lt;expression>] [-Listenpriority &lt;positive_integer>] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-netProfile &lt;string>] [-comment &lt;string>] [-srcIPExpr &lt;expression>] [-originUSIP ( ON | OFF )] [-usePortRange ( ON | OFF )] [-appflowLog ( ENABLED | DISABLED )] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )]


##Arguments

<b>name</b>
Name of the cache redirection virtual server.

<b>IPAddress</b>
New IPv4 or IPv6 address of the cache redirection virtual server. Usually a public IP address. Clients send connection requests to this IP address.

<b>redirect</b>
Type of server to which to redirect HTTP requests. Available settings function as follows: *	CACHE - Direct all requests to the cache.*	POLICY - Apply the cache redirection policy to determine whether the request should be directed to the cache or to the origin.*	ORIGIN - Direct all requests to the origin server.
Possible values: CACHE, POLICY, ORIGIN
Default value: CRD_POLICY

<b>onPolicyMatch</b>
Redirect requests that match the policy to either the cache or the origin server, as specified.
Note: For this option to work, you must set the cache redirection type to POLICY.
Possible values: CACHE, ORIGIN
Default value: CRD_ORIGIN

<b>precedence</b>
Type of policy (URL or RULE) that takes precedence on the cache redirection virtual server. You can use this argument only when configuring cache redirection on the specified virtual server. It applies only if both URL and RULE based policies have been configured on the same virtual server. Available settings function as follows:URL - The incoming request is matched against the URL-based policies before it is matched against the rule-based policies.
For URL based policies, the precedence hierarchy is:
1.   Domain and exact URL
2.   Domain, prefix and suffix
3.   Domain and suffix
4.   Domain and prefix
5.   Domain only
6.   Exact URL
7.   Prefix and suffix
8.   Suffix only
9.   Prefix only
10.  Default
RULE - The incoming request is matched against the rule-based policies before it is matched against the URL-based policies.
Possible values: RULE, URL
Default value: CS_PRIORITY_RULE

<b>arp</b>
Use ARP to determine the destination MAC address. Specify OFF to use the incoming destination MAC address, or ON to use ARP to determine the destination MAC address.
Possible values: ON, OFF

<b>via</b>
Insert a via header in each HTTP request. In the case of a cache miss, the request is redirected from the cache server to the origin server. This header indicates whether the request is being sent from a cache server.
Possible values: ON, OFF
Default value: ON

<b>cacheVserver</b>
Name of the default target cache virtual server to which to redirect requests.

<b>dnsVserverName</b>
Name of the DNS virtual server that resolves domain names arriving at the forward proxy virtual server.
Note: This parameter applies only to forward proxy virtual servers, not reverse or transparent.

<b>destinationVServer</b>
Destination virtual server for a transparent or forward proxy cache redirection virtual server.

<b>domain</b>
Default domain for reverse proxies. Domains are configured to direct incoming requests from a specified source domain to a specified target domain. There can be several configured pairs of source and target domains. You can select one pair to be the default. If the host header or URL of an incoming request does not include a source domain, this option sends the request to the specified target domain.

<b>reuse</b>
Reuse TCP connections to the origin server across client connections
Possible values: ON, OFF
Default value: ON

<b>backupVServer</b>
Name of the backup virtual server to which traffic is forwarded if the active server becomes unavailable.

<b>disablePrimaryOnDown</b>
Continue sending traffic to a backup virtual server even after the primary virtual server comes UP from the DOWN state.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>redirectURL</b>
URL of the server to which to redirect traffic if the cache redirection virtual server in the NetScaler becomes unavailable.

<b>cltTimeout</b>
Time-out value, in seconds, after which an idle client connection is terminated.
Maximum value: 31536000

<b>downStateFlush</b>
Perform delayed cleanup of connections to this virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>l2Conn</b>
Use L2 parameters, such as MAC, VLAN, and channel to identify a connection.
Possible values: ON, OFF

<b>backendssl</b>
Decides whether the backend connection made by NS to the origin server will be HTTP or SSL. Applicable only for SSL type CR Forward proxy vserver.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>Listenpolicy</b>
String specifying the listen policy for the cache redirection virtual server. Can be either an in-line expression or the name of a named expression.
Default value: "none"

<b>Listenpriority</b>
Priority of the listen policy specified by the Listen Policy parameter. The lower the number, higher the priority.
Default value: 101
Maximum value: 100

<b>tcpProfileName</b>
Name of the profile containing TCP configuration information for the cache redirection virtual server.

<b>httpProfileName</b>
Name of the profile containing HTTP configuration information for cache redirection virtual server.

<b>netProfile</b>
Name of the network profile containing network configurations for the cache redirection virtual server.

<b>comment</b>
Comments associated with this virtual server.

<b>srcIPExpr</b>
Expression used to extract the source IP addresses from the requests originating from the cache. Can be either an in-line expression or the name of a named expression.

<b>originUSIP</b>
Use the client?s IP address as the source IP address in requests sent to the origin server.  
Note: You can enable this parameter to implement fully transparent CR deployment.
Possible values: ON, OFF
Default value: OFF

<b>usePortRange</b>
Use a port number from the port range (set by using the set ns param command, or in the Create Virtual Server (Cache Redirection) dialog box) as the source port in the requests sent to the origin server.
Possible values: ON, OFF
Default value: OFF

<b>appflowLog</b>
Enable logging of AppFlow information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>icmpVsrResponse</b>
Criterion for responding to PING requests sent to this virtual server. If ACTIVE, respond only if the virtual server is available. If PASSIVE, respond even if the virtual server is not available.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance, injects even if one virtual server set to ACTIVE is UP.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE



##unset cr vserver

Restores the specified parameters of a cache redirection virtual server to their default values. To unset all except the Name parameter, do not specify a value for any other parameter. Refer to the set cr vserver command for a description of the parameters..Refer to the set cr vserver command for meanings of the arguments.


##Synopsys

unset cr vserver &lt;name> [-dnsVserverName] [-destinationVServer] [-domain] [-backupVServer] [-cltTimeout] [-redirectURL] [-l2Conn] [-backendssl] [-originUSIP] [-usePortRange] [-srcIPExpr] [-tcpProfileName] [-httpProfileName] [-appflowLog] [-netProfile] [-icmpVsrResponse] [-redirect] [-onPolicyMatch] [-precedence] [-arp] [-via] [-reuse] [-disablePrimaryOnDown] [-downStateFlush] [-Listenpolicy] [-Listenpriority] [-comment] [-RHIstate]


##Related Commands

<ul><li><a href="../../../p/p">rm cr policy</a></li><li><a href="../../../r-p/r-p">show cr policy</a></li></ul>



##bind cr vserver

Binds a cache redirection policy to a cache redirection virtual server.


##Synopsys

bind cr vserver &lt;name> [-lbvserver &lt;string> | (-policyName &lt;string>  [-priority &lt;positive_integer>]) | &lt;targetVserver>]


##Arguments

<b>name</b>
Name of the cache redirection virtual server to which to bind the cache redirection policy.

<b>lbvserver</b>
Name of the virtual server to which content is forwarded. Applicable only if the policy is a map policy and the cache redirection virtual server is of type REVERSE.

<b>policyName</b>
Name of the cache redirection policy that you are binding.



##unbind cr vserver

Unbinds a cache redirection policy from a cache redirection virtual server.


##Synopsys

unbind cr vserver &lt;name> [-policyName &lt;string> | -lbvserver &lt;string>]


##Arguments

<b>name</b>
Name of the cache redirection virtual server from which to unbind the policy.

<b>policyName</b>
Name of the cache redirection policy that you are unbinding.

<b>lbvserver</b>
The virtual server name (created with the add lb vserver command) to which content will be switched.
Default value: "default_lb"



##Related Commands

<ul><li><a href="../../../p/p">rm cr policy</a></li><li><a href="../../../r-p/r-p">show cr policy</a></li></ul>



##enable cr vserver

Enables a cache redirection virtual server. Note:	Virtual servers, when added, are enabled by default.


##Synopsys

enable cr vserver &lt;name>@


##Arguments

<b>name</b>
Name of the cache redirection virtual server to be enabled.



##Example

enable vserver cr_vip

##disable cr vserver

Disables a cache redirection virtual server.


##Synopsys

disable cr vserver &lt;name>@


##Arguments

<b>name</b>
Name of the cache redirection virtual server to be disabled. (Because the virtual server is still configured, you can reenable it.)
Note: The appliance still responds to ARP and ping requests sent to the IP address of this virtual server.



##Example

disable vserver cr_vip

##show cr vserver

Displays cache redirection virtual server information. To display information about all configured cache redirection virtual servers, do not include a parameter. To display detailed information about a specific virtual server, use the name parameter to specify the name of the virtual server.


##Synopsys

show cr vserver [&lt;name>]


##Arguments

<b>name</b>
Name of a cache redirection virtual server about which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>IPAddress</b>
The IP address of the virtual server.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>stateflag</b>

<b>value</b>
The ssl card status for the transparent ssl cr vserver.

<b>port</b>
Port number of the virtual server.

<b>range</b>
Number of consecutive IP addresses, starting with the address specified by the IP Address parameter, to include in a range of addresses assigned to this virtual server.

<b>serviceType</b>
Protocol (type of service) handled by the virtual server.

<b>ngname</b>
Nodegroup devno to which this crvserver belongs to

<b>type</b>
Virtual server type.

<b>vsvrcfgflags</b>
Contains the config info of vserver to be used at validation

<b>state</b>
Initial state of the cache redirection virtual server.

<b>status</b>
Status.

<b>cacheType</b>
Mode of operation for the cache redirection virtual server. Available settings function as follows:
* TRANSPARENT - Intercept all traffic flowing to the appliance and apply cache redirection policies to determine whether content should be served from the cache or from the origin server.
* FORWARD - Resolve the hostname of the incoming request, by using a DNS server, and forward requests for non-cacheable content to the resolved origin servers. Cacheable requests are sent to the configured cache servers.
* REVERSE - Configure reverse proxy caches for specific origin servers. Incoming traffic directed to the reverse proxy can either be served from a cache server or be sent to the origin server with or without modification to the URL.

<b>redirect</b>
Type of cache server to which to redirect HTTP requests. Available settings function as follows:
* CACHE - Direct all requests to the cache.
* POLICY - Apply the cache redirection policy to determine whether the request should be directed to the cache or to the origin.
* ORIGIN - Direct all requests to the origin server.

<b>onPolicyMatch</b>
Redirect requests that match the policy to either the cache or the origin server, as specified.
Note: For this option to work, you must set the cache redirection type to POLICY.

<b>precedence</b>
Type of policy (URL or RULE) that takes precedence on the cache redirection virtual server. Applies only to cache redirection virtual servers that have both URL and RULE based policies. If you specify URL, URL based policies are applied first, in the following order:
1.   Domain and exact URL
2.   Domain, prefix and suffix
3.   Domain and suffix
4.   Domain and prefix
5.   Domain only
6.   Exact URL
7.   Prefix and suffix
8.   Suffix only
9.   Prefix only
10.  Default
If you specify RULE, the rule based policies are applied before URL based policies are applied.

<b>redirectURL</b>
URL of the server to which to redirect traffic if the cache redirection virtual server configured on the NetScaler appliance becomes unavailable.

<b>authentication</b>
Authentication.

<b>homePage</b>
Home page.

<b>dnsVserverName</b>
Name of the DNS virtual server that resolves domain names arriving at the forward proxy virtual server.
Note: This parameter applies only to forward proxy virtual servers, not reverse or transparent.

<b>domain</b>
Default domain for reverse proxies. Domains are configured to direct an incoming request from a specified source domain to a specified target domain. There can be several configured pairs of source and target domains. You can select one pair to be the default. If the host header or URL of an incoming request does not include a source domain, this option sends the request to the specified target domain.

<b>rule</b>
Rule.

<b>policyName</b>
Policies bound to this vserver.

<b>hits</b>
Number of hits.

<b>serviceName</b>
Service name.

<b>weight</b>
Weight for this service.

<b>cacheVserver</b>
Name of the default cache virtual server to which to redirect requests (the default target of the cache redirection virtual server).NOTE: This attribute is deprecated.The functionality is intact, but we advise to use bind command to do default binding for CR

<b>targetVserver</b>
The CSW target server names.

<b>backupVServer</b>
Name of the backup virtual server to which traffic is forwarded if the active server becomes unavailable.

<b>priority</b>
The priority for the policy.

<b>cltTimeout</b>
Time-out value, in seconds, after which to terminate an idle client connection.

<b>soMethod</b>
The spillover factor. When the main virtual server reaches this spillover threshold, it will give further traffic to the backupvserver.

<b>soPersistence</b>
The state of spillover persistence.

<b>soPersistenceTimeOut</b>
The spillover persistence entry timeout.

<b>soThreshold</b>
The spillover threshold value.

<b>reuse</b>
Reuse TCP connections to the origin server across client connections. Do not set this parameter unless the Service Type parameter is set to HTTP. If you set this parameter to OFF, the possible settings of the Redirect parameter function as follows:
* CACHE - TCP connections to the cache servers are not reused.
* ORIGIN - TCP connections to the origin servers are not reused. 
* POLICY - TCP connections to the origin servers are not reused.
If you set the Reuse parameter to ON, connections to origin servers and connections to cache servers are reused.

<b>arp</b>

<b>destinationVServer</b>
Destination virtual server for a transparent or forward proxy cache redirection virtual server.

<b>via</b>
Insert a via header in each HTTP request. In the case of a cache miss, the request is redirected from the cache server to the origin server. This header indicates whether the request is being sent from a cache server.

<b>downStateFlush</b>
Perform delayed clean up of connections on this vserver.

<b>disablePrimaryOnDown</b>
Tells whether traffic will continue reaching backup vservers even after primary comes UP from DOWN state.

<b>l2Conn</b>
Use L2 parameters, such as MAC, VLAN, and channel to identify a connection.

<b>backendssl</b>
Decides whether the backend connection made by NS to the origin server will be HTTP or SSL. Applicable only for SSL type CR Forward proxy vserver.

<b>comment</b>
Comments associated with this virtual server.

<b>Listenpolicy</b>
The string is listenpolicy configured for CR vserver

<b>Listenpriority</b>
This parameter is the priority for listen policy of CR Vserver.

<b>tcpProfileName</b>
Name of the profile containing TCP configuration information for the cache redirection virtual server.

<b>httpProfileName</b>
Name of the profile containing HTTP configuration information for cache redirection virtual server.

<b>srcIPExpr</b>
Expression used to extract the source IP addresses from the requests originating from the cache. Can be either an in-line expression or the name of a named expression.

<b>originUSIP</b>
Use the client?s IP address as the source IP address in requests sent to the origin server.  
Note: You can enable this parameter to implement fully transparent CR deployment.

<b>usePortRange</b>
Use a port number from the port range (set by using the set ns param command, or in the Create Virtual Server (Cache Redirection) dialog box) as the source port in the requests sent to the origin server.

<b>appflowLog</b>
Enable logging of AppFlow information.

<b>netProfile</b>
Name of the network profile containing network configurations for the cache redirection virtual server.

<b>icmpVsrResponse</b>
Criterion for responding to PING requests sent to this virtual server. If ACTIVE, respond only if the virtual server is available. If PASSIVE, respond even if the virtual server is not available.

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance, injects even if one virtual server set to ACTIVE is UP.

<b>lbvserver</b>
The Default target server name.

<b>inherited</b>
On State describes that policy bound is inherited from global binding.

<b>devno</b>

<b>count</b>



##stat cr vserver

Displays statistics for all cache redirection virtual servers or for the cache redirection virtual server specified by the name parameter.


##Synopsys

stat cr vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of a specific cache redirection virtual server.

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



##rename cr vserver

Renames a cache redirection virtual server.


##Synopsys

rename cr vserver &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the cache redirection virtual server.

<b>newName</b>
New name for the cache redirection virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my name? or ?my name?).



##Example

rename cr vserver vscr1 vscrnew

