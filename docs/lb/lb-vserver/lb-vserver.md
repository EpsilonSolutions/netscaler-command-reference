#lb vserver

The following operations can be performed on "lb vserver":


[add](#add-lb-vserver) | [rm](#rm-lb-vserver) | [set](#set-lb-vserver) | [unset](#unset-lb-vserver) | [bind](#bind-lb-vserver) | [unbind](#unbind-lb-vserver) | [enable](#enable-lb-vserver) | [disable](#disable-lb-vserver) | [show](#show-lb-vserver) | [stat](#stat-lb-vserver) | [rename](#rename-lb-vserver)

##add lb vserver

Creates a load balancing virtual server.


##Synopsys

add lb vserver &lt;name>@ &lt;serviceType> [(&lt;IPAddress>@  &lt;port>  [-range &lt;positive_integer>]) | (-IPPattern &lt;ippat>  -IPMask &lt;ipmask>)] [-persistenceType &lt;persistenceType>] [-timeout &lt;mins>] [-persistenceBackup ( SOURCEIP | NONE )] [-backupPersistenceTimeout &lt;mins>] [-lbMethod &lt;lbMethod>  [-hashLength &lt;positive_integer>]   [-netmask &lt;netmask>]    [-v6netmasklen &lt;positive_integer>]    [-dataLength &lt;positive_integer>]  [-dataOffset &lt;positive_integer>]] [-cookieName &lt;string>] [-rule &lt;expression>] [-Listenpolicy &lt;expression>  [-Listenpriority &lt;positive_integer>]] [-resRule &lt;expression>] [-persistMask &lt;netmask>] [-v6persistmasklen &lt;positive_integer>] [-pq ( ON | OFF )] [-sc ( ON | OFF )] [-rtspNat ( ON | OFF )] [-m &lt;m>] [-tosId &lt;positive_integer>] [-sessionless ( ENABLED | DISABLED )] [-state ( ENABLED | DISABLED )] [-connfailover &lt;connfailover>] [-redirectURL &lt;URL>] [-cacheable ( YES | NO )] [-cltTimeout &lt;secs>] [-soMethod &lt;soMethod>] [-soPersistence ( ENABLED | DISABLED )] [-soPersistenceTimeOut &lt;positive_integer>] [-healthThreshold &lt;positive_integer>] [-soThreshold &lt;positive_integer>] [-soBackupAction &lt;soBackupAction>] [-redirectPortRewrite ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-backupVServer &lt;string>] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-insertVserverIPPort &lt;insertVserverIPPort>  [&lt;vipHeader>] ] [-AuthenticationHost &lt;string>] [-Authentication ( ON | OFF )] [-authn401 ( ON | OFF )] [-authnVsName &lt;string>] [-push ( ENABLED | DISABLED )] [-pushVserver &lt;string>] [-pushLabel &lt;expression>] [-pushMultiClients ( YES | NO )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-dbProfileName &lt;string>] [-comment &lt;string>] [-l2Conn ( ON | OFF )] [-oracleServerVersion ( 10G | 11G )] [-mssqlServerVersion &lt;mssqlServerVersion>] [-mysqlProtocolVersion &lt;positive_integer>] [-mysqlServerVersion &lt;string>] [-mysqlCharacterSet &lt;positive_integer>] [-mysqlServerCapabilities &lt;positive_integer>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )] [-newServiceRequest &lt;positive_integer>  [&lt;newServiceRequestUnit>]] [-newServiceRequestIncrementInterval &lt;positive_integer>] [-minAutoscaleMembers &lt;positive_integer>] [-maxAutoscaleMembers &lt;positive_integer>] [-persistAVPno &lt;positive_integer> ...] [-skippersistency &lt;skippersistency>] [-td &lt;positive_integer>] [-authnProfile &lt;string>] [-macmodeRetainvlan ( ENABLED | DISABLED )] [-dbsLb ( ENABLED | DISABLED )] [-dns64 ( ENABLED | DISABLED )] [-bypassAAAA ( YES | NO )] [-RecursionAvailable ( YES | NO )] [-processLocal ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the virtual server is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').

<b>serviceType</b>
Protocol used by the service (also called the service type).
Possible values: HTTP, FTP, TCP, UDP, SSL, SSL_BRIDGE, SSL_TCP, DTLS, NNTP, DNS, DHCPRA, ANY, SIP_UDP, DNS_TCP, RTSP, PUSH, SSL_PUSH, RADIUS, RDP, MYSQL, MSSQL, DIAMETER, SSL_DIAMETER, TFTP, ORACLE

<b>IPAddress</b>
IPv4 or IPv6 address to assign to the virtual server.

<b>IPPattern</b>
IP address pattern, in dotted decimal notation, for identifying packets to be accepted by the virtual server. The IP Mask parameter specifies which part of the destination IP address is matched against the pattern.  Mutually exclusive with the IP Address parameter. 
For example, if the IP pattern assigned to the virtual server is 198.51.100.0 and the IP mask is 255.255.240.0 (a forward mask), the first 20 bits in the destination IP addresses are matched with the first 20 bits in the pattern. The virtual server accepts requests with IP addresses that range from 198.51.96.1 to 198.51.111.254.  You can also use a pattern such as 0.0.2.2 and a mask such as 0.0.255.255 (a reverse mask).
If a destination IP address matches more than one IP pattern, the pattern with the longest match is selected, and the associated virtual server processes the request. For example, if virtual servers vs1 and vs2 have the same IP pattern, 0.0.100.128, but different IP masks of 0.0.255.255 and 0.0.224.255, a destination IP address of 198.51.100.128 has the longest match with the IP pattern of vs1. If a destination IP address matches two or more virtual servers to the same extent, the request is processed by the virtual server whose port number matches the port number in the request.

<b>port</b>
Port number for the virtual server.

<b>range</b>
Number of IP addresses that the appliance must generate and assign to the virtual server. The virtual server then functions as a network virtual server, accepting traffic on any of the generated IP addresses. The IP addresses are generated automatically, as follows: 
* For a range of n, the last octet of the address specified by the IP Address parameter increments n-1 times. 
* If the last octet exceeds 255, it rolls over to 0 and the third octet increments by 1.
Note: The Range parameter assigns multiple IP addresses to one virtual server. To generate an array of virtual servers, each of which owns only one IP address, use brackets in the IP Address and Name parameters to specify the range. For example:
add lb vserver my_vserver[1-3] HTTP 192.0.2.[1-3] 80
Default value: 1
Minimum value: 1
Maximum value: 254

<b>persistenceType</b>
Type of persistence for the virtual server. Available settings function as follows:
* SOURCEIP - Connections from the same client IP address belong to the same persistence session.
* COOKIEINSERT - Connections that have the same HTTP Cookie, inserted by a Set-Cookie directive from a server, belong to the same persistence session. 
* SSLSESSION - Connections that have the same SSL Session ID belong to the same persistence session.
* CUSTOMSERVERID - Connections with the same server ID form part of the same session. For this persistence type, set the Server ID (CustomServerID) parameter for each service and configure the Rule parameter to identify the server ID in a request.
* RULE - All connections that match a user defined rule belong to the same persistence session. 
* URLPASSIVE - Requests that have the same server ID in the URL query belong to the same persistence session. The server ID is the hexadecimal representation of the IP address and port of the service to which the request must be forwarded. This persistence type requires a rule to identify the server ID in the request. 
* DESTIP - Connections to the same destination IP address belong to the same persistence session.
* SRCIPDESTIP - Connections that have the same source IP address and destination IP address belong to the same persistence session.
* CALLID - Connections that have the same CALL-ID SIP header belong to the same persistence session.
* RTSPSID - Connections that have the same RTSP Session ID belong to the same persistence session.
Possible values: SOURCEIP, COOKIEINSERT, SSLSESSION, RULE, URLPASSIVE, CUSTOMSERVERID, DESTIP, SRCIPDESTIP, CALLID, RTSPSID, DIAMETER, NONE

<b>timeout</b>
Time period for which a persistence session is in effect.
Default value: 2
Maximum value: 1440

<b>persistenceBackup</b>
Backup persistence type for the virtual server. Becomes operational if the primary persistence mechanism fails.
Possible values: SOURCEIP, NONE

<b>backupPersistenceTimeout</b>
Time period for which backup persistence is in effect.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>lbMethod</b>
Load balancing method.  The available settings function as follows:
* ROUNDROBIN - Distribute requests in rotation, regardless of the load. Weights can be assigned to services to enforce weighted round robin distribution.
* LEASTCONNECTION (default) - Select the service with the fewest connections. 
* LEASTRESPONSETIME - Select the service with the lowest average response time. 
* LEASTBANDWIDTH - Select the service currently handling the least traffic.
* LEASTPACKETS - Select the service currently serving the lowest number of packets per second.
* CUSTOMLOAD - Base service selection on the SNMP metrics obtained by custom load monitors.
* LRTM - Select the service with the lowest response time. Response times are learned through monitoring probes. This method also takes the number of active connections into account.
Also available are a number of hashing methods, in which the appliance extracts a predetermined portion of the request, creates a hash of the portion, and then checks whether any previous requests had the same hash value. If it finds a match, it forwards the request to the service that served those previous requests. Following are the hashing methods: 
* URLHASH - Create a hash of the request URL (or part of the URL).
* DOMAINHASH - Create a hash of the domain name in the request (or part of the domain name). The domain name is taken from either the URL or the Host header. If the domain name appears in both locations, the URL is preferred. If the request does not contain a domain name, the load balancing method defaults to LEASTCONNECTION.
* DESTINATIONIPHASH - Create a hash of the destination IP address in the IP header. 
* SOURCEIPHASH - Create a hash of the source IP address in the IP header.  
* TOKEN - Extract a token from the request, create a hash of the token, and then select the service to which any previous requests with the same token hash value were sent. 
* SRCIPDESTIPHASH - Create a hash of the string obtained by concatenating the source IP address and destination IP address in the IP header.  
* SRCIPSRCPORTHASH - Create a hash of the source IP address and source port in the IP header.  
* CALLIDHASH - Create a hash of the SIP Call-ID header.
Possible values: ROUNDROBIN, LEASTCONNECTION, LEASTRESPONSETIME, URLHASH, DOMAINHASH, DESTINATIONIPHASH, SOURCEIPHASH, SRCIPDESTIPHASH, LEASTBANDWIDTH, LEASTPACKETS, TOKEN, SRCIPSRCPORTHASH, LRTM, CALLIDHASH, CUSTOMLOAD, LEASTREQUEST
Default value: PEMGMT_LB_LEASTCONNS

<b>cookieName</b>
Use this parameter to specify the cookie name for COOKIE peristence type. It specifies the name of cookie with a maximum of 32 characters. If not specified, cookie name is internally generated.

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.
Default value: "none"

<b>Listenpolicy</b>
Default syntax expression identifying traffic accepted by the virtual server. Can be either an expression (for example, CLIENT.IP.DST.IN_SUBNET(192.0.2.0/24) or the name of a named expression. In the above example, the virtual server accepts all requests whose destination IP address is in the 192.0.2.0/24 subnet.
Default value: "none"

<b>Listenpriority</b>
Integer specifying the priority of the listen policy. A higher number specifies a lower priority. If a request matches the listen policies of more than one virtual server the virtual server whose listen policy has the highest priority (the lowest priority number) accepts the request.
Default value: 101
Maximum value: 101

<b>resRule</b>
Default syntax expression specifying which part of a server's response to use for creating rule based persistence sessions (persistence type RULE). Can be either an expression or the name of a named expression.
Example:
HTTP.RES.HEADER("setcookie").VALUE(0).TYPECAST_NVLIST_T('=',';').VALUE("server1").
Default value: "none"

<b>persistMask</b>
Persistence mask for IP based persistence types, for IPv4 virtual servers.
Default value: 0xFFFFFFFF

<b>v6persistmasklen</b>
Persistence mask for IP based persistence types, for IPv6 virtual servers.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>pq</b>
Use priority queuing on the virtual server. based persistence types, for IPv6 virtual servers.
Possible values: ON, OFF
Default value: OFF

<b>sc</b>
Use SureConnect on the virtual server.
Possible values: ON, OFF
Default value: OFF

<b>rtspNat</b>
Use network address translation (NAT) for RTSP data connections.
Possible values: ON, OFF
Default value: OFF

<b>m</b>
Redirection mode for load balancing. Available settings function as follows:
* IP - Before forwarding a request to a server, change the destination IP address to the server's IP address. 
* MAC - Before forwarding a request to a server, change the destination MAC address to the server's MAC address.  The destination IP address is not changed. MAC-based redirection mode is used mostly in firewall load balancing deployments. 
* IPTUNNEL - Perform IP-in-IP encapsulation for client IP packets. In the outer IP headers, set the destination IP address to the IP address of the server and the source IP address to the subnet IP (SNIP). The client IP packets are not modified. Applicable to both IPv4 and IPv6 packets. 
* TOS - Encode the virtual server's TOS ID in the TOS field of the IP header. 
You can use either the IPTUNNEL or the TOS option to implement Direct Server Return (DSR).
Possible values: IP, MAC, IPTUNNEL, TOS
Default value: NSFWD_IP

<b>tosId</b>
TOS ID of the virtual server. Applicable only when the load balancing redirection mode is set to TOS.
Minimum value: 1
Maximum value: 63

<b>dataLength</b>
Length of the token to be extracted from the data segment of an incoming packet, for use in the token method of load balancing. The length of the token, specified in bytes, must not be greater than 24 KB. Applicable to virtual servers of type TCP.
Minimum value: 1
Maximum value: 100

<b>dataOffset</b>
Offset to be considered when extracting a token from the TCP payload. Applicable to virtual servers, of type TCP, using the token method of load balancing. Must be within the first 24 KB of the TCP payload.
Maximum value: 25400

<b>sessionless</b>
Perform load balancing on a per-packet basis, without establishing sessions. Recommended for load balancing of intrusion detection system (IDS) servers and scenarios involving direct server return (DSR), where session information is unnecessary.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>state</b>
State of the load balancing virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>connfailover</b>
Mode in which the connection failover feature must operate for the virtual server. After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary appliance. Clients remain connected to the same servers. Available settings function as follows:
* STATEFUL - The primary appliance shares state information with the secondary appliance, in real time, resulting in some runtime processing overhead. 
* STATELESS - State information is not shared, and the new primary appliance tries to re-create the packet flow on the basis of the information contained in the packets it receives. 
* DISABLED - Connection failover does not occur.
Possible values: DISABLED, STATEFUL, STATELESS
Default value: DISABLED

<b>redirectURL</b>
URL to which to redirect traffic if the virtual server becomes unavailable. 
WARNING! Make sure that the domain in the URL does not match the domain specified for a content switching policy. If it does, requests are continuously redirected to the unavailable virtual server.

<b>cacheable</b>
Route cacheable requests to a cache redirection virtual server. The load balancing virtual server can forward requests only to a transparent cache redirection virtual server that has an IP address and port combination of *:80, so such a cache redirection virtual server must be configured on the appliance.
Possible values: YES, NO
Default value: NO

<b>cltTimeout</b>
Idle time, in seconds, after which a client connection is terminated.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>soMethod</b>
Type of threshold that, when exceeded, triggers spillover. Available settings function as follows:
* CONNECTION - Spillover occurs when the number of client connections exceeds the threshold.
* DYNAMICCONNECTION - Spillover occurs when the number of client connections at the virtual server exceeds the sum of the maximum client (Max Clients) settings for bound services. Do not specify a spillover threshold for this setting, because the threshold is implied by the Max Clients settings of bound services.
* BANDWIDTH - Spillover occurs when the bandwidth consumed by the virtual server's incoming and outgoing traffic exceeds the threshold. 
* HEALTH - Spillover occurs when the percentage of weights of the services that are UP drops below the threshold. For example, if services svc1, svc2, and svc3 are bound to a virtual server, with weights 1, 2, and 3, and the spillover threshold is 50%, spillover occurs if svc1 and svc3 or svc2 and svc3 transition to DOWN. 
* NONE - Spillover does not occur.
Possible values: CONNECTION, DYNAMICCONNECTION, BANDWIDTH, HEALTH, NONE

<b>soPersistence</b>
If spillover occurs, maintain source IP address based persistence for both primary and backup virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>soPersistenceTimeOut</b>
Timeout for spillover persistence, in minutes.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>healthThreshold</b>
Threshold in percent of active services below which vserver state is made down. If this threshold is 0, vserver state will be up even if one bound service is up.
Default value: 0
Minimum value: 0
Maximum value: 100

<b>soThreshold</b>
Threshold at which spillover occurs. Specify an integer for the CONNECTION spillover method, a bandwidth value in kilobits per second for the BANDWIDTH method (do not enter the units), or a percentage for the HEALTH method (do not enter the percentage symbol).
Minimum value: 1
Maximum value: 4294967287

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists
Possible values: DROP, ACCEPT, REDIRECT

<b>redirectPortRewrite</b>
Rewrite the port and change the protocol to ensure successful HTTP redirects from services.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>downStateFlush</b>
Flush all active transactions associated with a virtual server whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>backupVServer</b>
Name of the backup virtual server to which to forward requests if the primary virtual server goes DOWN or reaches its spillover threshold.

<b>disablePrimaryOnDown</b>
If the primary virtual server goes down, do not allow it to return to primary status until manually enabled.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>insertVserverIPPort</b>
Insert an HTTP header, whose value is the IP address and port number of the virtual server, before forwarding a request to the server. The format of the header is &lt;vipHeader&gt;: &lt;virtual server IP address&gt;_&lt;port number &gt;, where vipHeader is the name that you specify for the header. If the virtual server has an IPv6 address, the address in the header is enclosed in brackets ([ and ]) to separate it from the port number. If you have mapped an IPv4 address to a virtual server's IPv6 address, the value of this parameter determines which IP address is inserted in the header, as follows:
* VIPADDR - Insert the IP address of the virtual server in the HTTP header regardless of whether the virtual server has an IPv4 address or an IPv6 address. A mapped IPv4 address, if configured, is ignored.
* V6TOV4MAPPING - Insert the IPv4 address that is mapped to the virtual server's IPv6 address. If a mapped IPv4 address is not configured, insert the IPv6 address.
* OFF - Disable header insertion.
Possible values: OFF, VIPADDR, V6TOV4MAPPING

<b>AuthenticationHost</b>
Fully qualified domain name (FQDN) of the authentication virtual server to which the user must be redirected for authentication. Make sure that the Authentication parameter is set to ENABLED.

<b>Authentication</b>
Enable or disable user authentication.
Possible values: ON, OFF
Default value: OFF

<b>authn401</b>
Enable or disable user authentication with HTTP 401 responses.
Possible values: ON, OFF
Default value: OFF

<b>authnVsName</b>
Name of an authentication virtual server with which to authenticate users.

<b>push</b>
Process traffic with the push virtual server that is bound to this load balancing virtual server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>pushVserver</b>
Name of the load balancing virtual server, of type PUSH or SSL_PUSH, to which the server pushes updates received on the load balancing virtual server that you are configuring.

<b>pushLabel</b>
Expression for extracting a label from the server's response. Can be either an expression or the name of a named expression.
Default value: "none"

<b>pushMultiClients</b>
Allow multiple Web 2.0 connections from the same client to connect to the virtual server and expect updates.
Possible values: YES, NO
Default value: NO

<b>tcpProfileName</b>
Name of the TCP profile whose settings are to be applied to the virtual server.

<b>httpProfileName</b>
Name of the HTTP profile whose settings are to be applied to the virtual server.

<b>dbProfileName</b>
Name of the DB profile whose settings are to be applied to the virtual server.

<b>comment</b>
Any comments that you might want to associate with the virtual server.

<b>l2Conn</b>
Use Layer 2 parameters (channel number, MAC address, and VLAN ID) in addition to the 4-tuple (&lt;source IP&gt;:&lt;source port&gt;::&lt;destination IP&gt;:&lt;destination port&gt;) that is used to identify a connection. Allows multiple TCP and non-TCP connections with the same 4-tuple to co-exist on the NetScaler appliance.
Possible values: ON, OFF

<b>oracleServerVersion</b>
Oracle server version
Possible values: 10G, 11G
Default value: ORACLE_SERVER_10G

<b>mssqlServerVersion</b>
For a load balancing virtual server of type MSSQL, the Microsoft SQL Server version. Set this parameter if you expect some clients to run a version different from the version of the database. This setting provides compatibility between the client-side and server-side connections by ensuring that all communication conforms to the server's version.
Possible values: 70, 2000, 2000SP1, 2005, 2008, 2008R2, 2012
Default value: TDS_PROT_2008B

<b>mysqlProtocolVersion</b>
MySQL protocol version that the virtual server advertises to clients.
Default value: NSA_MYSQL_PROTOCOL_VER_DEFAULT

<b>mysqlServerVersion</b>
MySQL server version string that the virtual server advertises to clients.
Default value: NSA_MYSQL_SERVER_VER_DEFAULT

<b>mysqlCharacterSet</b>
Character set that the virtual server advertises to clients.
Default value: NSA_MYSQL_CHAR_SET_DEFAULT

<b>mysqlServerCapabilities</b>
Server capabilities that the virtual server advertises to clients.
Default value: NSA_MYSQL_SVR_CAPABILITIES_DEFAULT

<b>appflowLog</b>
Apply AppFlow logging to the virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Name of the network profile to associate with the virtual server. If you set this parameter, the virtual server uses only the IP addresses in the network profile as source IP addresses when initiating connections with servers.

<b>icmpVsrResponse</b>
How the NetScaler appliance responds to ping requests received for an IP address that is common to one or more virtual servers. Available settings function as follows:
* If set to PASSIVE on all the virtual servers that share the IP address, the appliance always responds to the ping requests.
* If set to ACTIVE on all the virtual servers that share the IP address, the appliance responds to the ping requests if at least one of the virtual servers is UP. Otherwise, the appliance does not respond.
* If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance responds if at least one virtual server with the ACTIVE setting is UP. Otherwise, the appliance does not respond.
Note: This parameter is available at the virtual server level. A similar parameter, ICMP Response, is available at the IP address level, for IPv4 addresses of type VIP. To set that parameter, use the add ip command in the CLI or the Create IP dialog box in the GUI.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>RHIstate</b>
Route Health Injection (RHI) functionality of the NetSaler appliance for advertising the route of the VIP address associated with the virtual server. When Vserver RHI Level (RHI) parameter is set to VSVR_CNTRLD, the following are different RHI behaviors for the VIP address on the basis of RHIstate (RHI STATE) settings on the virtual servers associated with the VIP address:
* If you set RHI STATE to PASSIVE on all virtual servers, the NetScaler ADC always advertises the route for the VIP address.
* If you set RHI STATE to ACTIVE on all virtual servers, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers is in UP state.
* If you set RHI STATE to ACTIVE on some and PASSIVE on others, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers, whose RHI STATE set to ACTIVE, is in UP state.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>newServiceRequest</b>
Number of requests, or percentage of the load on existing services, by which to increase the load on a new service at each interval in slow-start mode. A non-zero value indicates that slow-start is applicable. A zero value indicates that the global RR startup parameter is applied. Changing the value to zero will cause services currently in slow start to take the full traffic as determined by the LB method. Subsequently, any new services added will use the global RR factor.
Default value: 0

<b>newServiceRequestIncrementInterval</b>
Interval, in seconds, between successive increments in the load on a new service or a service whose state has just changed from DOWN to UP. A value of 0 (zero) specifies manual slow start.
Default value: 0
Maximum value: 3600

<b>minAutoscaleMembers</b>
Minimum number of members expected to be present when vserver is used in Autoscale.
Default value: 0
Maximum value: 5000

<b>maxAutoscaleMembers</b>
Maximum number of members expected to be present when vserver is used in Autoscale.
Default value: 0
Maximum value: 5000

<b>persistAVPno</b>
Persist AVP number for Diameter Persistency. 
            In case this AVP is not defined in Base RFC 3588 and it is nested inside a Grouped AVP, 
            define a sequence of AVP numbers (max 3) in order of parent to child. So say persist AVP number X 
            is nested inside AVP Y which is nested in Z, then define the list as  Z Y X
Minimum value: 1

<b>skippersistency</b>
This argument decides the behavior incase the service which is selected from an existing persistence session has reached threshold.
Possible values: Bypass, ReLb, None
Default value: NS_DONT_SKIPPERSIST

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>authnProfile</b>
Name of the authentication profile to be used when authentication is turned on.

<b>macmodeRetainvlan</b>
This option is used to retain vlan information of incoming packet when macmode is enabled
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dbsLb</b>
Enable database specific load balancing for MySQL and MSSQL service types.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dns64</b>
This argument is for enabling/disabling the dns64 on lbvserver
Possible values: ENABLED, DISABLED

<b>bypassAAAA</b>
If this option is enabled while resolving DNS64 query AAAA queries are not sent to back end dns server
Possible values: YES, NO
Default value: NO

<b>RecursionAvailable</b>
When set to YES, this option causes the DNS replies from this vserver to have the RA bit turned on. Typically one would set this option to YES, when the vserver is load balancing a set of DNS servers thatsupport recursive queries.
Possible values: YES, NO
Default value: NO

<b>processLocal</b>
By turning on this option packets destined to a vserver in a cluster will not under go any steering. Turn this option for single packet request response mode or when the upstream device is performing a proper RSS for connection based distribution.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add lb vserver http_vsvr http 10.102.1.10 80	To add multiple vservers at once use the following command:	add lb vs http_vsvr[1-4] http 10.102.27.[115-118] 80	This command adds the vserver http_vsvr1 with the IP address 10.102.27.115, http_vsvr2 with 10.102.27.116, http_vsvr3 with 10.102.27.117 and http_vsvr4 with 10.102.27.118

##rm lb vserver

Removes a virtual server from the NetScaler appliance.


##Synopsys

rm lb vserver &lt;name>@ ...


##Arguments

<b>name</b>
Name of the virtual server.



##Example

rm vserver lb_vip	To remove multiple vservers use the following command:	rm vserver lb_vip[1-3]

##set lb vserver

Modifies the specified parameters of a load balancing virtual server.


##Synopsys

set lb vserver &lt;name>@ [-IPAddress &lt;ip_addr|ipv6_addr|*>@] [-IPPattern &lt;ippat>] [-IPMask &lt;ipmask>] [-weight &lt;positive_integer>  &lt;serviceName>@] [-persistenceType &lt;persistenceType>] [-timeout &lt;mins>] [-persistenceBackup ( SOURCEIP | NONE )] [-backupPersistenceTimeout &lt;mins>] [-lbMethod &lt;lbMethod>  [-hashLength &lt;positive_integer>]   [-netmask &lt;netmask>]    [-v6netmasklen &lt;positive_integer>]  ] [-rule &lt;expression>] [-cookieName &lt;string>] [-resRule &lt;expression>] [-persistMask &lt;netmask>] [-v6persistmasklen &lt;positive_integer>] [-pq ( ON | OFF )] [-sc ( ON | OFF )] [-rtspNat ( ON | OFF )] [-m &lt;m>] [-tosId &lt;positive_integer>] [-dataLength &lt;positive_integer>] [-dataOffset &lt;positive_integer>] [-sessionless ( ENABLED | DISABLED )] [-connfailover &lt;connfailover>] [-backupVServer &lt;string>] [-redirectURL &lt;URL>] [-cacheable ( YES | NO )] [-cltTimeout &lt;secs>] [-soMethod &lt;soMethod>] [-soThreshold &lt;positive_integer>] [-soPersistence ( ENABLED | DISABLED )] [-soPersistenceTimeOut &lt;positive_integer>] [-healthThreshold &lt;positive_integer>] [-soBackupAction &lt;soBackupAction>] [-redirectPortRewrite ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-insertVserverIPPort &lt;insertVserverIPPort>  [&lt;vipHeader>] ] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-AuthenticationHost &lt;string>] [-Authentication ( ON | OFF )] [-authn401 ( ON | OFF )] [-authnVsName &lt;string>] [-push ( ENABLED | DISABLED )] [-pushVserver &lt;string>] [-pushLabel &lt;expression>] [-pushMultiClients ( YES | NO )] [-Listenpolicy &lt;expression>] [-Listenpriority &lt;positive_integer>] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-dbProfileName &lt;string>] [-comment &lt;string>] [-l2Conn ( ON | OFF )] [-oracleServerVersion ( 10G | 11G )] [-mssqlServerVersion &lt;mssqlServerVersion>] [-mysqlProtocolVersion &lt;positive_integer>] [-mysqlServerVersion &lt;string>] [-mysqlCharacterSet &lt;positive_integer>] [-mysqlServerCapabilities &lt;positive_integer>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )] [-newServiceRequest &lt;positive_integer>] [&lt;newServiceRequestUnit>] [-newServiceRequestIncrementInterval &lt;positive_integer>] [-minAutoscaleMembers &lt;positive_integer>] [-maxAutoscaleMembers &lt;positive_integer>] [-persistAVPno &lt;positive_integer> ...] [-skippersistency &lt;skippersistency>] [-authnProfile &lt;string>] [-macmodeRetainvlan ( ENABLED | DISABLED )] [-dbsLb ( ENABLED | DISABLED )] [-dns64 ( ENABLED | DISABLED )] [-bypassAAAA ( YES | NO )] [-RecursionAvailable ( YES | NO )] [-processLocal ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the virtual server.

<b>IPAddress</b>
IPv4 or IPv6 address to assign to the virtual server.

<b>IPPattern</b>
IP address pattern, in dotted decimal notation, for identifying packets to be accepted by the virtual server. The IP Mask parameter specifies which part of the destination IP address is matched against the pattern.  Mutually exclusive with the IP Address parameter. 
For example, if the IP pattern assigned to the virtual server is 198.51.100.0 and the IP mask is 255.255.240.0 (a forward mask), the first 20 bits in the destination IP addresses are matched with the first 20 bits in the pattern. The virtual server accepts requests with IP addresses that range from 198.51.96.1 to 198.51.111.254.  You can also use a pattern such as 0.0.2.2 and a mask such as 0.0.255.255 (a reverse mask).
If a destination IP address matches more than one IP pattern, the pattern with the longest match is selected, and the associated virtual server processes the request. For example, if virtual servers vs1 and vs2 have the same IP pattern, 0.0.100.128, but different IP masks of 0.0.255.255 and 0.0.224.255, a destination IP address of 198.51.100.128 has the longest match with the IP pattern of vs1. If a destination IP address matches two or more virtual servers to the same extent, the request is processed by the virtual server whose port number matches the port number in the request.

<b>IPMask</b>
IP mask, in dotted decimal notation, for the IP Pattern parameter. Can have leading or trailing non-zero octets (for example, 255.255.240.0 or 0.0.255.255). Accordingly, the mask specifies whether the first n bits or the last n bits of the destination IP address in a client request are to be matched with the corresponding bits in the IP pattern. The former is called a forward mask. The latter is called a reverse mask.

<b>weight</b>
Weight to assign to the specified service.
Minimum value: 1
Maximum value: 100

<b>persistenceType</b>
Type of persistence for the virtual server. Available settings function as follows:
* SOURCEIP - Connections from the same client IP address belong to the same persistence session.
* COOKIEINSERT - Connections that have the same HTTP Cookie, inserted by a Set-Cookie directive from a server, belong to the same persistence session. 
* SSLSESSION - Connections that have the same SSL Session ID belong to the same persistence session.
* CUSTOMSERVERID - Connections with the same server ID form part of the same session. For this persistence type, set the Server ID (CustomServerID) parameter for each service and configure the Rule parameter to identify the server ID in a request.
* RULE - All connections that match a user defined rule belong to the same persistence session. 
* URLPASSIVE - Requests that have the same server ID in the URL query belong to the same persistence session. The server ID is the hexadecimal representation of the IP address and port of the service to which the request must be forwarded. This persistence type requires a rule to identify the server ID in the request. 
* DESTIP - Connections to the same destination IP address belong to the same persistence session.
* SRCIPDESTIP - Connections that have the same source IP address and destination IP address belong to the same persistence session.
* CALLID - Connections that have the same CALL-ID SIP header belong to the same persistence session.
* RTSPSID - Connections that have the same RTSP Session ID belong to the same persistence session.
Possible values: SOURCEIP, COOKIEINSERT, SSLSESSION, RULE, URLPASSIVE, CUSTOMSERVERID, DESTIP, SRCIPDESTIP, CALLID, RTSPSID, DIAMETER, NONE

<b>timeout</b>
Time period for which a persistence session is in effect.
Default value: 2
Maximum value: 1440

<b>persistenceBackup</b>
Backup persistence type for the virtual server. Becomes operational if the primary persistence mechanism fails.
Possible values: SOURCEIP, NONE

<b>backupPersistenceTimeout</b>
Time period for which backup persistence is in effect.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>lbMethod</b>
Load balancing method.  The available settings function as follows:
* ROUNDROBIN - Distribute requests in rotation, regardless of the load. Weights can be assigned to services to enforce weighted round robin distribution.
* LEASTCONNECTION (default) - Select the service with the fewest connections. 
* LEASTRESPONSETIME - Select the service with the lowest average response time. 
* LEASTBANDWIDTH - Select the service currently handling the least traffic.
* LEASTPACKETS - Select the service currently serving the lowest number of packets per second.
* CUSTOMLOAD - Base service selection on the SNMP metrics obtained by custom load monitors.
* LRTM - Select the service with the lowest response time. Response times are learned through monitoring probes. This method also takes the number of active connections into account.
Also available are a number of hashing methods, in which the appliance extracts a predetermined portion of the request, creates a hash of the portion, and then checks whether any previous requests had the same hash value. If it finds a match, it forwards the request to the service that served those previous requests. Following are the hashing methods: 
* URLHASH - Create a hash of the request URL (or part of the URL).
* DOMAINHASH - Create a hash of the domain name in the request (or part of the domain name). The domain name is taken from either the URL or the Host header. If the domain name appears in both locations, the URL is preferred. If the request does not contain a domain name, the load balancing method defaults to LEASTCONNECTION.
* DESTINATIONIPHASH - Create a hash of the destination IP address in the IP header. 
* SOURCEIPHASH - Create a hash of the source IP address in the IP header.  
* TOKEN - Extract a token from the request, create a hash of the token, and then select the service to which any previous requests with the same token hash value were sent. 
* SRCIPDESTIPHASH - Create a hash of the string obtained by concatenating the source IP address and destination IP address in the IP header.  
* SRCIPSRCPORTHASH - Create a hash of the source IP address and source port in the IP header.  
* CALLIDHASH - Create a hash of the SIP Call-ID header.
Possible values: ROUNDROBIN, LEASTCONNECTION, LEASTRESPONSETIME, URLHASH, DOMAINHASH, DESTINATIONIPHASH, SOURCEIPHASH, SRCIPDESTIPHASH, LEASTBANDWIDTH, LEASTPACKETS, TOKEN, SRCIPSRCPORTHASH, LRTM, CALLIDHASH, CUSTOMLOAD, LEASTREQUEST
Default value: PEMGMT_LB_LEASTCONNS

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.
Default value: "none"

<b>cookieName</b>
Use this parameter to specify the cookie name for COOKIE peristence type. It specifies the name of cookie with a maximum of 32 characters. If not specified, cookie name is internally generated.

<b>resRule</b>
Default syntax expression specifying which part of a server's response to use for creating rule based persistence sessions (persistence type RULE). Can be either an expression or the name of a named expression.
Example:
HTTP.RES.HEADER("setcookie").VALUE(0).TYPECAST_NVLIST_T('=',';').VALUE("server1").
Default value: "none"

<b>persistMask</b>
Persistence mask for IP based persistence types, for IPv4 virtual servers.
Default value: 0xFFFFFFFF

<b>v6persistmasklen</b>
Persistence mask for IP based persistence types, for IPv6 virtual servers.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>pq</b>
Use priority queuing on the virtual server. based persistence types, for IPv6 virtual servers.
Possible values: ON, OFF
Default value: OFF

<b>sc</b>
Use SureConnect on the virtual server.
Possible values: ON, OFF
Default value: OFF

<b>rtspNat</b>
Use network address translation (NAT) for RTSP data connections.
Possible values: ON, OFF
Default value: OFF

<b>m</b>
Redirection mode for load balancing. Available settings function as follows:
* IP - Before forwarding a request to a server, change the destination IP address to the server's IP address. 
* MAC - Before forwarding a request to a server, change the destination MAC address to the server's MAC address.  The destination IP address is not changed. MAC-based redirection mode is used mostly in firewall load balancing deployments. 
* IPTUNNEL - Perform IP-in-IP encapsulation for client IP packets. In the outer IP headers, set the destination IP address to the IP address of the server and the source IP address to the subnet IP (SNIP). The client IP packets are not modified. Applicable to both IPv4 and IPv6 packets. 
* TOS - Encode the virtual server's TOS ID in the TOS field of the IP header. 
You can use either the IPTUNNEL or the TOS option to implement Direct Server Return (DSR).
Possible values: IP, MAC, IPTUNNEL, TOS
Default value: NSFWD_IP

<b>tosId</b>
TOS ID of the virtual server. Applicable only when the load balancing redirection mode is set to TOS.
Minimum value: 1
Maximum value: 63

<b>dataLength</b>
Length of the token to be extracted from the data segment of an incoming packet, for use in the token method of load balancing. The length of the token, specified in bytes, must not be greater than 24 KB. Applicable to virtual servers of type TCP.
Minimum value: 1
Maximum value: 100

<b>dataOffset</b>
Offset to be considered when extracting a token from the TCP payload. Applicable to virtual servers, of type TCP, using the token method of load balancing. Must be within the first 24 KB of the TCP payload.
Maximum value: 25400

<b>sessionless</b>
Perform load balancing on a per-packet basis, without establishing sessions. Recommended for load balancing of intrusion detection system (IDS) servers and scenarios involving direct server return (DSR), where session information is unnecessary.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>connfailover</b>
Mode in which the connection failover feature must operate for the virtual server. After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary appliance. Clients remain connected to the same servers. Available settings function as follows:
* STATEFUL - The primary appliance shares state information with the secondary appliance, in real time, resulting in some runtime processing overhead. 
* STATELESS - State information is not shared, and the new primary appliance tries to re-create the packet flow on the basis of the information contained in the packets it receives. 
* DISABLED - Connection failover does not occur.
Possible values: DISABLED, STATEFUL, STATELESS
Default value: DISABLED

<b>backupVServer</b>
Name of the backup virtual server to which to forward requests if the primary virtual server goes DOWN or reaches its spillover threshold.

<b>redirectURL</b>
URL to which to redirect traffic if the virtual server becomes unavailable. 
WARNING! Make sure that the domain in the URL does not match the domain specified for a content switching policy. If it does, requests are continuously redirected to the unavailable virtual server.

<b>cacheable</b>
Route cacheable requests to a cache redirection virtual server. The load balancing virtual server can forward requests only to a transparent cache redirection virtual server that has an IP address and port combination of *:80, so such a cache redirection virtual server must be configured on the appliance.
Possible values: YES, NO
Default value: NO

<b>cltTimeout</b>
Idle time, in seconds, after which a client connection is terminated.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>soMethod</b>
Type of threshold that, when exceeded, triggers spillover. Available settings function as follows:
* CONNECTION - Spillover occurs when the number of client connections exceeds the threshold.
* DYNAMICCONNECTION - Spillover occurs when the number of client connections at the virtual server exceeds the sum of the maximum client (Max Clients) settings for bound services. Do not specify a spillover threshold for this setting, because the threshold is implied by the Max Clients settings of bound services.
* BANDWIDTH - Spillover occurs when the bandwidth consumed by the virtual server's incoming and outgoing traffic exceeds the threshold. 
* HEALTH - Spillover occurs when the percentage of weights of the services that are UP drops below the threshold. For example, if services svc1, svc2, and svc3 are bound to a virtual server, with weights 1, 2, and 3, and the spillover threshold is 50%, spillover occurs if svc1 and svc3 or svc2 and svc3 transition to DOWN. 
* NONE - Spillover does not occur.
Possible values: CONNECTION, DYNAMICCONNECTION, BANDWIDTH, HEALTH, NONE

<b>soPersistence</b>
If spillover occurs, maintain source IP address based persistence for both primary and backup virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>soPersistenceTimeOut</b>
Timeout for spillover persistence, in minutes.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>healthThreshold</b>
Threshold in percent of active services below which vserver state is made down. If this threshold is 0, vserver state will be up even if one bound service is up.
Default value: 0
Minimum value: 0
Maximum value: 100

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists
Possible values: DROP, ACCEPT, REDIRECT

<b>redirectPortRewrite</b>
Rewrite the port and change the protocol to ensure successful HTTP redirects from services.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>downStateFlush</b>
Flush all active transactions associated with a virtual server whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>insertVserverIPPort</b>
Insert an HTTP header, whose value is the IP address and port number of the virtual server, before forwarding a request to the server. The format of the header is &lt;vipHeader&gt;: &lt;virtual server IP address&gt;_&lt;port number &gt;, where vipHeader is the name that you specify for the header. If the virtual server has an IPv6 address, the address in the header is enclosed in brackets ([ and ]) to separate it from the port number. If you have mapped an IPv4 address to a virtual server's IPv6 address, the value of this parameter determines which IP address is inserted in the header, as follows:
* VIPADDR - Insert the IP address of the virtual server in the HTTP header regardless of whether the virtual server has an IPv4 address or an IPv6 address. A mapped IPv4 address, if configured, is ignored.
* V6TOV4MAPPING - Insert the IPv4 address that is mapped to the virtual server's IPv6 address. If a mapped IPv4 address is not configured, insert the IPv6 address.
* OFF - Disable header insertion.
Possible values: OFF, VIPADDR, V6TOV4MAPPING

<b>disablePrimaryOnDown</b>
If the primary virtual server goes down, do not allow it to return to primary status until manually enabled.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>AuthenticationHost</b>
Fully qualified domain name (FQDN) of the authentication virtual server to which the user must be redirected for authentication. Make sure that the Authentication parameter is set to ENABLED.

<b>Authentication</b>
Enable or disable user authentication.
Possible values: ON, OFF
Default value: OFF

<b>authn401</b>
Enable or disable user authentication with HTTP 401 responses.
Possible values: ON, OFF
Default value: OFF

<b>authnVsName</b>
Name of an authentication virtual server with which to authenticate users.

<b>push</b>
Process traffic with the push virtual server that is bound to this load balancing virtual server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>pushVserver</b>
Name of the load balancing virtual server, of type PUSH or SSL_PUSH, to which the server pushes updates received on the load balancing virtual server that you are configuring.

<b>pushLabel</b>
Expression for extracting a label from the server's response. Can be either an expression or the name of a named expression.
Default value: "none"

<b>pushMultiClients</b>
Allow multiple Web 2.0 connections from the same client to connect to the virtual server and expect updates.
Possible values: YES, NO
Default value: NO

<b>Listenpolicy</b>
Default syntax expression identifying traffic accepted by the virtual server. Can be either an expression (for example, CLIENT.IP.DST.IN_SUBNET(192.0.2.0/24) or the name of a named expression. In the above example, the virtual server accepts all requests whose destination IP address is in the 192.0.2.0/24 subnet.
Default value: "none"

<b>Listenpriority</b>
Integer specifying the priority of the listen policy. A higher number specifies a lower priority. If a request matches the listen policies of more than one virtual server the virtual server whose listen policy has the highest priority (the lowest priority number) accepts the request.
Default value: 101
Maximum value: 101

<b>tcpProfileName</b>
Name of the TCP profile whose settings are to be applied to the virtual server.

<b>httpProfileName</b>
Name of the HTTP profile whose settings are to be applied to the virtual server.

<b>dbProfileName</b>
Name of the DB profile whose settings are to be applied to the virtual server.

<b>comment</b>
Any comments that you might want to associate with the virtual server.

<b>l2Conn</b>
Use Layer 2 parameters (channel number, MAC address, and VLAN ID) in addition to the 4-tuple (&lt;source IP&gt;:&lt;source port&gt;::&lt;destination IP&gt;:&lt;destination port&gt;) that is used to identify a connection. Allows multiple TCP and non-TCP connections with the same 4-tuple to co-exist on the NetScaler appliance.
Possible values: ON, OFF

<b>oracleServerVersion</b>
Oracle server version
Possible values: 10G, 11G
Default value: ORACLE_SERVER_10G

<b>mssqlServerVersion</b>
For a load balancing virtual server of type MSSQL, the Microsoft SQL Server version. Set this parameter if you expect some clients to run a version different from the version of the database. This setting provides compatibility between the client-side and server-side connections by ensuring that all communication conforms to the server's version.
Possible values: 70, 2000, 2000SP1, 2005, 2008, 2008R2, 2012
Default value: TDS_PROT_2008B

<b>mysqlProtocolVersion</b>
MySQL protocol version that the virtual server advertises to clients.
Default value: NSA_MYSQL_PROTOCOL_VER_DEFAULT

<b>mysqlServerVersion</b>
MySQL server version string that the virtual server advertises to clients.
Default value: NSA_MYSQL_SERVER_VER_DEFAULT

<b>mysqlCharacterSet</b>
Character set that the virtual server advertises to clients.
Default value: NSA_MYSQL_CHAR_SET_DEFAULT

<b>mysqlServerCapabilities</b>
Server capabilities that the virtual server advertises to clients.
Default value: NSA_MYSQL_SVR_CAPABILITIES_DEFAULT

<b>appflowLog</b>
Apply AppFlow logging to the virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Name of the network profile to associate with the virtual server. If you set this parameter, the virtual server uses only the IP addresses in the network profile as source IP addresses when initiating connections with servers.

<b>icmpVsrResponse</b>
How the NetScaler appliance responds to ping requests received for an IP address that is common to one or more virtual servers. Available settings function as follows:
* If set to PASSIVE on all the virtual servers that share the IP address, the appliance always responds to the ping requests.
* If set to ACTIVE on all the virtual servers that share the IP address, the appliance responds to the ping requests if at least one of the virtual servers is UP. Otherwise, the appliance does not respond.
* If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance responds if at least one virtual server with the ACTIVE setting is UP. Otherwise, the appliance does not respond.
Note: This parameter is available at the virtual server level. A similar parameter, ICMP Response, is available at the IP address level, for IPv4 addresses of type VIP. To set that parameter, use the add ip command in the CLI or the Create IP dialog box in the GUI.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>RHIstate</b>
Route Health Injection (RHI) functionality of the NetSaler appliance for advertising the route of the VIP address associated with the virtual server. When Vserver RHI Level (RHI) parameter is set to VSVR_CNTRLD, the following are different RHI behaviors for the VIP address on the basis of RHIstate (RHI STATE) settings on the virtual servers associated with the VIP address:
* If you set RHI STATE to PASSIVE on all virtual servers, the NetScaler ADC always advertises the route for the VIP address.
* If you set RHI STATE to ACTIVE on all virtual servers, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers is in UP state.
* If you set RHI STATE to ACTIVE on some and PASSIVE on others, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers, whose RHI STATE set to ACTIVE, is in UP state.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>newServiceRequest</b>
Number of requests, or percentage of the load on existing services, by which to increase the load on a new service at each interval in slow-start mode. A non-zero value indicates that slow-start is applicable. A zero value indicates that the global RR startup parameter is applied. Changing the value to zero will cause services currently in slow start to take the full traffic as determined by the LB method. Subsequently, any new services added will use the global RR factor.
Default value: 0

<b>newServiceRequestIncrementInterval</b>
Interval, in seconds, between successive increments in the load on a new service or a service whose state has just changed from DOWN to UP. A value of 0 (zero) specifies manual slow start.
Default value: 0
Maximum value: 3600

<b>minAutoscaleMembers</b>
Minimum number of members expected to be present when vserver is used in Autoscale.
Default value: 0
Maximum value: 5000

<b>maxAutoscaleMembers</b>
Maximum number of members expected to be present when vserver is used in Autoscale.
Default value: 0
Maximum value: 5000

<b>persistAVPno</b>
Persist AVP number for Diameter Persistency. 
            In case this AVP is not defined in Base RFC 3588 and it is nested inside a Grouped AVP, 
            define a sequence of AVP numbers (max 3) in order of parent to child. So say persist AVP number X 
            is nested inside AVP Y which is nested in Z, then define the list as  Z Y X
Minimum value: 1

<b>skippersistency</b>
This argument decides the behavior incase the service which is selected from an existing persistence session has reached threshold.
Possible values: Bypass, ReLb, None
Default value: NS_DONT_SKIPPERSIST

<b>authnProfile</b>
Name of the authentication profile to be used when authentication is turned on.

<b>macmodeRetainvlan</b>
This option is used to retain vlan information of incoming packet when macmode is enabled
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dbsLb</b>
Enable database specific load balancing for MySQL and MSSQL service types.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dns64</b>
This argument is for enabling/disabling the dns64 on lbvserver
Possible values: ENABLED, DISABLED

<b>bypassAAAA</b>
If this option is enabled while resolving DNS64 query AAAA queries are not sent to back end dns server
Possible values: YES, NO
Default value: NO

<b>RecursionAvailable</b>
When set to YES, this option causes the DNS replies from this vserver to have the RA bit turned on. Typically one would set this option to YES, when the vserver is load balancing a set of DNS servers thatsupport recursive queries.
Possible values: YES, NO
Default value: NO

<b>processLocal</b>
By turning on this option packets destined to a vserver in a cluster will not under go any steering. Turn this option for single packet request response mode or when the upstream device is performing a proper RSS for connection based distribution.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set lb vserver http_vip  -lbmethod  LEASTRESPONSETIME	To set the load balancing method for multiple vserver use the following command:	set lb vserver http_vip[1-3] -lbmethod  LEASTRESPONSETIME

##unset lb vserver

Removes the specified parameter settings from the virtual server..Refer to the set lb vserver command for meanings of the arguments.


##Synopsys

unset lb vserver &lt;name>@ [-backupVServer] [-cltTimeout] [-redirectURL] [-authn401] [-Authentication] [-AuthenticationHost] [-authnVsName] [-pushVserver] [-pushLabel] [-tcpProfileName] [-httpProfileName] [-dbProfileName] [-rule] [-l2Conn] [-mysqlProtocolVersion] [-mysqlServerVersion] [-mysqlCharacterSet] [-mysqlServerCapabilities] [-appflowLog] [-netProfile] [-icmpVsrResponse] [-skippersistency] [-minAutoscaleMembers] [-maxAutoscaleMembers] [-authnProfile] [-macmodeRetainvlan] [-dbsLb] [-serviceName] [-persistenceType] [-timeout] [-persistenceBackup] [-backupPersistenceTimeout] [-lbMethod] [-hashLength] [-netmask] [-v6netmasklen] [-cookieName] [-resRule] [-persistMask] [-v6persistmasklen] [-pq] [-sc] [-rtspNat] [-m] [-tosId] [-dataLength] [-dataOffset] [-sessionless] [-connfailover] [-cacheable] [-soMethod] [-soPersistence] [-soPersistenceTimeOut] [-healthThreshold] [-soBackupAction] [-redirectPortRewrite] [-downStateFlush] [-insertVserverIPPort] [-vipHeader] [-disablePrimaryOnDown] [-push] [-pushMultiClients] [-Listenpolicy] [-Listenpriority] [-comment] [-oracleServerVersion] [-mssqlServerVersion] [-RHIstate] [-newServiceRequest] [-newServiceRequestUnit] [-newServiceRequestIncrementInterval] [-persistAVPno] [-RecursionAvailable]


##Example

unset lb vserver lb_vip -backupVServer	To unset the backup virtual server for multiple vservers use the following command:	unset lb vserver lb_vip[1-3] -backupVServer

##bind lb vserver

Binds a service, service group, or policy to a virtual server.


##Synopsys

bind lb vserver &lt;name>@ ((&lt;serviceName>@  [-weight &lt;positive_integer>] ) | &lt;serviceGroupName>@ | (-policyName &lt;string>@  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]  [-type ( REQUEST | RESPONSE )]  [-invoke  (&lt;labelType>  &lt;labelName>) ]  ))


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the virtual server is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').

<b>serviceName</b>
Name of the service.

<b>serviceGroupName</b>
Name of the service group.

<b>policyName</b>
Name of the policy to bind to the virtual server.



##Example

bind lb vserver http_vip http_svc	To bind a service to multiple vservers use the following command:	bind lb vs http_vip[1-3] http_svc	To bind multiple services to a vserver use the following command:	bind lb vs http_vip http_svc[1-3]

##unbind lb vserver

Unbinds a service, service group, or policy from a virtual server.


##Synopsys

unbind lb vserver &lt;name>@ (&lt;serviceName>@ | &lt;serviceGroupName>@ | (-policyName &lt;string>@  [-type ( REQUEST | RESPONSE )])) [-priority &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the virtual server is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').

<b>serviceName</b>
Name of the service.

<b>serviceGroupName</b>
The name of the service group that is unbound.

<b>policyName</b>
Name of the policy to bind to the virtual server.

<b>priority</b>
Priority number of the policy.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind lb vserver http_vip  http_svc	To unbind a service from multiple vservers use the following command:	unbind lb vs http_vip[1-3] http_svc        To unbind multiple services from a vserver use the following command:        unbind lb vs http_vip http_svc[1-3]

##enable lb vserver

Enables a virtual server.


##Synopsys

enable lb vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server.



##Example

enable vserver lb_vip	To enable multiple vservers at once use the following command:	enable vserver lb_vip[1-3]

##disable lb vserver

Disables a virtual server.


##Synopsys

disable lb vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server.



##Example

disable vserver lb_vip	To disable multiple vservers at once use the following command:	disable vserver lb_vip[1-3]

##show lb vserver

Displays the statistical data collected for a load balancing virtual server.


##Synopsys

show lb vserver [&lt;name>]show lb vserver stats - alias for 'stat lb vserver'


##Arguments

<b>name</b>
Name of the virtual server. If no name is provided, statistical data of all configured virtual servers is displayed.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>insertVserverIPPort</b>
The virtual IP and port header insertion option for the vserver.

<b>vipHeader</b>
Name for the inserted header. The default name is vip-header.

<b>value</b>
SSL status.

<b>stateflag</b>

<b>appfwPolicyFlag</b>

<b>IPAddress</b>
IPv4 or IPv6 address to assign to the virtual server.

<b>IPPattern</b>
The IP pattern of the virtual server.

<b>IPMask</b>
The IP address mask of the virtual server.

<b>Listenpolicy</b>
The string is listenpolicy configured for lb vserver

<b>Listenpriority</b>
This parameter is the priority for listen policy of LB Vserver.

<b>IPMapping</b>
The permanent mapping for the V6 Address

<b>port</b>
Port number for the virtual server.

<b>range</b>
Number of IP addresses that the appliance must generate and assign to the virtual server. The virtual server then functions as a network virtual server, accepting traffic on any of the generated IP addresses. The IP addresses are generated automatically, as follows: 
* For a range of n, the last octet of the address specified by the IP Address parameter increments n-1 times. 
* If the last octet exceeds 255, it rolls over to 0 and the third octet increments by 1.
Note: The Range parameter assigns multiple IP addresses to one virtual server. To generate an array of virtual servers, each of which owns only one IP address, use brackets in the IP Address and Name parameters to specify the range. For example:
add lb vserver my_vserver[1-3] HTTP 192.0.2.[1-3] 80

<b>serviceType</b>
Protocol used by the service (also called the service type).

<b>ngname</b>
Nodegroup name to which this lbvsever belongs to

<b>type</b>
The bindpoint to which the policy is bound

<b>state</b>
State of the load balancing virtual server.

<b>effectiveState</b>
Effective state of the LB vserver , based on the state of backup vservers.

<b>status</b>
Current status of the lb vserver. During the initial phase if the configured lb method is not round robin , the vserver will adopt round robin to distribute traffic for a predefined number of requests.

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

<b>cacheType</b>
Cache type.

<b>redirect</b>
Cache redirect type.

<b>precedence</b>
Precedence.

<b>redirectURL</b>
The redirect URL.

<b>Authentication</b>
Authentication.

<b>authn401</b>
HTTP 401 response based authentication.

<b>authnVsName</b>
Name of an authentication virtual server with which to authenticate users.

<b>homePage</b>
Home page.

<b>dnsVserverName</b>
DNS vserver name.

<b>domain</b>
Domain.

<b>policyName</b>
Name of the policy bound to the LB vserver.

<b>serviceName</b>
Service to bind to the virtual server.

<b>serviceGroupName</b>
The service group name bound to the selected load balancing virtual server.

<b>weight</b>
Weight to assign to the specified service.

<b>dynamicWeight</b>
Dynamic weight

<b>cacheVserver</b>
Cache virtual server.

<b>backupVServer</b>
Name of the backup virtual server to which to forward requests if the primary virtual server goes DOWN or reaches its spillover threshold.

<b>priority</b>
Priority.

<b>cltTimeout</b>
The client timeout in seconds.

<b>soMethod</b>
The spillover method to be in effect.

<b>soPersistence</b>
State of spillover persistence.

<b>soPersistenceTimeOut</b>
The maximum time persistence is in effect for a specific client on a spillover vserver.

<b>healthThreshold</b>
Threshold in percent of active services below which vserver state is made down.

<b>soThreshold</b>
Threshold at which spillover occurs. Specify an integer for the CONNECTION spillover method, a bandwidth value in kilobits per second for the BANDWIDTH method (do not enter the units), or a percentage for the HEALTH method (do not enter the percentage symbol).

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists

<b>lbMethod</b>
The load balancing method to be in effect

<b>hashLength</b>
The hash length.

<b>dataOffset</b>
The data offset length for TOKEN load balancing method.

<b>health</b>
Health of vserver based on percentage of weights of active svcs/all svcs. This does not consider administratively disabled svcs

<b>dataLength</b>
The data length for TOKEN load balancing method.

<b>netmask</b>
The netmask of the destination network.

<b>v6netmasklen</b>
The netmask of the destination network.

<b>rule</b>
Rule type.

<b>resRule</b>
Use this parameter to specify the expression to be used in response for RULE persistence type.
The string is an in-line expression with a maximum of 1499 characters.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>ruleType</b>
Rule type.

<b>groupName</b>
LB group to which the lb vserver is to be bound.

<b>m</b>
The LB mode.

<b>tosId</b>
TOS ID

<b>persistenceType</b>
The persistence type for the specified virtual server

<b>timeout</b>
The maximum time persistence is in effect for a specific client.

<b>cookieDomain</b>
Domain name to be used in the set cookie header in case of cookie persistence.

<b>persistMask</b>
The persistence mask for v4 traffic

<b>v6persistmasklen</b>
The persistence mask for v6 traffic.

<b>persistenceBackup</b>
The maximum time backup persistence is in effect for a specific client.

<b>backupPersistenceTimeout</b>
Time period for which backup persistence is in effect.

<b>cacheable</b>
The state of caching.

<b>pq</b>
The state of priority queuing on the specified virtual server.

<b>sc</b>
The state of SureConnect the specified virtual server.

<b>rtspNat</b>
Use network address translation (NAT) for RTSP data connections.

<b>sessionless</b>
To enable sessionless load balancing, enable this option

<b>map</b>
Map.

<b>connfailover</b>
The connection failover mode of the virtual server

<b>redirectPortRewrite</b>
Rewrite the port and change the protocol to ensure successful HTTP redirects from services.

<b>downStateFlush</b>
Flush all active transactions associated with a virtual server whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.

<b>disablePrimaryOnDown</b>
Tells whether traffic will continue reaching backup vservers even after primary comes UP from DOWN state.

<b>gt2GB</b>
Allow for greater than 2 GB transactions on this vserver.

<b>consolidatedLConn</b>
Use consolidated stats for LeastConnection.

<b>consolidatedLConnGbl</b>
Fetches Global setting.

<b>thresholdValue</b>
Tells whether threshold exceeded for this service participating in CUSTOMLB

<b>invoke</b>
Invoke policies bound to a virtual server or policy label.

<b>labelType</b>
The invocation type.

<b>labelName</b>
Name of the label invoked.

<b>cookieIpPort</b>
Encryped Ip address and port of the service that is inserted into the set-cookie http header

<b>cookieName</b>
Use this parameter to specify the cookie name for COOKIE peristence type. It specifies the name of cookie with a maximum of 32 characters. If not specified, cookie name is internally generated.

<b>vserverId</b>
Vserver Id

<b>version</b>
Cookie version

<b>totalServices</b>
Total number of services bound to the vserver.

<b>activeServices</b>
Total number of active services bound to the vserver.

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>stateChangeTimeSeconds</b>
Time when last state change happened. Seconds part.

<b>stateChangeTimemSec</b>
Time at which last state change happened. Milliseconds part.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>hits</b>
Number of hits.

<b>piPolicyhits</b>
Number of hits.

<b>AuthenticationHost</b>
Fully qualified domain name (FQDN) of the authentication virtual server to which the user must be redirected for authentication. Make sure that the Authentication parameter is set to ENABLED.

<b>push</b>
Process traffic with the push virtual server that is bound to this load balancing virtual server.

<b>pushVserver</b>
Name of the load balancing virtual server, of type PUSH or SSL_PUSH, to which the server pushes updates received on the load balancing virtual server that you are configuring.

<b>pushLabel</b>
Expression for extracting a label from the server's response. Can be either an expression or the name of a named expression.

<b>pushMultiClients</b>
Allow multiple Web 2.0 connections from the same client to connect to the virtual server and expect updates.

<b>tcpProfileName</b>
Name of the TCP profile whose settings are to be applied to the virtual server.

<b>httpProfileName</b>
Name of the HTTP profile whose settings are to be applied to the virtual server.

<b>dbProfileName</b>
Name of the DB profile whose settings are to be applied to the virtual server.

<b>comment</b>
Any comments that you might want to associate with the virtual server.

<b>flag</b>

<b>flags</b>

<b>policySubType</b>

<b>l2Conn</b>
Use Layer 2 parameters (channel number, MAC address, and VLAN ID) in addition to the 4-tuple (&lt;source IP>:&lt;source port>::&lt;destination IP>:&lt;destination port>) that is used to identify a connection. Allows multiple TCP and non-TCP connections with the same 4-tuple to co-exist on the NetScaler appliance.

<b>oracleServerVersion</b>
Oracle server version

<b>mssqlServerVersion</b>
For a load balancing virtual server of type MSSQL, the Microsoft SQL Server version. Set this parameter if you expect some clients to run a version different from the version of the database. This setting provides compatibility between the client-side and server-side connections by ensuring that all communication conforms to the server's version.

<b>mysqlProtocolVersion</b>
MySQL protocol version that the virtual server advertises to clients.

<b>mysqlServerVersion</b>
MySQL server version string that the virtual server advertises to clients.

<b>mysqlCharacterSet</b>
Character set that the virtual server advertises to clients.

<b>mysqlServerCapabilities</b>
Server capabilities that the virtual server advertises to clients.

<b>appflowLog</b>
Apply AppFlow logging to the virtual server.

<b>netProfile</b>
Name of the network profile to associate with the virtual server. If you set this parameter, the virtual server uses only the IP addresses in the network profile as source IP addresses when initiating connections with servers.

<b>isGslb</b>
This field is set to true if it is a GSLBVserver.

<b>icmpVsrResponse</b>
How the NetScaler appliance responds to ping requests received for an IP address that is common to one or more virtual servers. Available settings function as follows:
* If set to PASSIVE on all the virtual servers that share the IP address, the appliance always responds to the ping requests.
* If set to ACTIVE on all the virtual servers that share the IP address, the appliance responds to the ping requests if at least one of the virtual servers is UP. Otherwise, the appliance does not respond.
* If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance responds if at least one virtual server with the ACTIVE setting is UP. Otherwise, the appliance does not respond.
Note: This parameter is available at the virtual server level. A similar parameter, ICMP Response, is available at the IP address level, for IPv4 addresses of type VIP. To set that parameter, use the add ip command in the CLI or the Create IP dialog box in the GUI.

<b>RHIstate</b>
Route Health Injection (RHI) functionality of the NetSaler appliance for advertising the route of the VIP address associated with the virtual server. When Vserver RHI Level (RHI) parameter is set to VSVR_CNTRLD, the following are different RHI behaviors for the VIP address on the basis of RHIstate (RHI STATE) settings on the virtual servers associated with the VIP address:
* If you set RHI STATE to PASSIVE on all virtual servers, the NetScaler ADC always advertises the route for the VIP address.
* If you set RHI STATE to ACTIVE on all virtual servers, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers is in UP state.
* If you set RHI STATE to ACTIVE on some and PASSIVE on others, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers, whose RHI STATE set to ACTIVE, is in UP state.

<b>newServiceRequest</b>
Number of requests, or percentage of the load on existing services, by which to increase the load on a new service at each interval in slow-start mode. A non-zero value indicates that slow-start is applicable. A zero value indicates that the global RR startup parameter is applied. Changing the value to zero will cause services currently in slow start to take the full traffic as determined by the LB method. Subsequently, any new services added will use the global RR factor.

<b>newServiceRequestUnit</b>
Units in which to increment load at each interval in slow-start mode.

<b>newServiceRequestIncrementInterval</b>
Interval, in seconds, between successive increments in the load on a new service or a service whose state has just changed from DOWN to UP. A value of 0 (zero) specifies manual slow start.

<b>vsvrcfgflags</b>
Contains the config info of vserver to be used at validation

<b>vsvrbindsvcip</b>
used for showing the ip of bound entities

<b>vsvrbindsvcport</b>
used for showing ports of bound entities

<b>persistAVPno</b>
Persist AVP number for Diameter Persistency. 
            In case this AVP is not defined in Base RFC 3588 and it is nested inside a Grouped AVP, 
            define a sequence of AVP numbers (max 3) in order of parent to child. So say persist AVP number X 
            is nested inside AVP Y which is nested in Z, then define the list as  Z Y X

<b>skippersistency</b>
This argument decides the behavior incase the service which is selected from an existing persistence session has reached threshold.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>minAutoscaleMembers</b>
Minimum number of members expected to be present when vserver is used in Autoscale.

<b>maxAutoscaleMembers</b>
Maximum number of members expected to be present when vserver is used in Autoscale.

<b>authnProfile</b>
Name of the authentication profile to be used when authentication is turned on.

<b>macmodeRetainvlan</b>
This option is used to retain vlan information of incoming packet when macmode is enabled

<b>dbsLb</b>
Enable database specific load balancing for MySQL and MSSQL service types.

<b>dns64</b>
This argument is for enabling/disabling the dns64 on lbvserver

<b>bypassAAAA</b>
If this option is enabled while resolving DNS64 query AAAA queries are not sent to back end dns server

<b>RecursionAvailable</b>
When set to YES, this option causes the DNS replies from this vserver to have the RA bit turned on. Typically one would set this option to YES, when the vserver is load balancing a set of DNS servers thatsupport recursive queries.

<b>processLocal</b>
By turning on this option packets destined to a vserver in a cluster will not under go any steering. Turn this option for single packet request response mode or when the upstream device is performing a proper RSS for connection based distribution.

<b>vsvrdynconnsothreshold</b>
Spillover threshold for dynamic connection

<b>devno</b>

<b>count</b>



##stat lb vserver

Displays the statistical data collected for a load balancing virtual server.


##Synopsys

stat lb vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )] [-sortBy Hits  [&lt;sortOrder>]]


##Arguments

<b>name</b>
Name of the virtual server. If no name is provided, statistical data of all configured virtual servers is displayed.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full

<b>sortBy</b>
use this argument to sort by specific key
Possible values: Hits



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Requests in vserver's surgeQ (vSurgeQ)</b>
Number of requests waiting on this vserver.

<b>Current Client Est connections (ClntEstConn)</b>
Number of client connections in ESTABLISHED state.

<b>total INACTIVE services (inactSvcs)</b>
number of INACTIVE services bound to a vserver

<b>Vserver Health (Health)</b>
Health of the vserver. This gives percentage of UP services bound to this vserver.

<b>Vserver IP address (vsvrIP)</b>
IP address of the vserver

<b>Port (port)</b>
The port on which the service is running.

<b>Vserver protocol (Protocol)</b>
Protocol associated with the vserver

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>total ACTIVE services (actSvcs)</b>
number of ACTIVE services bound to a vserver

<b>Vserver hits (Hits)</b>
Total vserver hits

<b>Requests (Req)</b>
Total number of requests received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Responses (Rsp)</b>
Number of responses received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Request bytes (Reqb)</b>
Total number of request bytes received on this service or virtual server.

<b>Response bytes (Rspb)</b>
Number of response bytes received by this service or virtual server.

<b>Total Packets rcvd (PktRx)</b>
Total number of packets received by this service or virtual server.

<b>Total Packets sent (PktTx)</b>
Total number of packets sent.

<b>Current client connections (ClntConn)</b>
Number of current client connections.

<b>Current server connections (SvrConn)</b>
Number of current connections to the actual servers behind the virtual server.

<b>Requests in surge queue (SurgeQ)</b>
Number of requests in the surge queue.

<b>Requests in service's surgeQs (SvcSurgeQ)</b>
Total number of requests in the surge queues of all the services bound to this LB-vserver.

<b>Spill Over Threshold (SOThresh)</b>
Spill Over Threshold set on the VServer.

<b>Spill Over Hits (NumSo )</b>
Number of times vserver experienced spill over.

<b>Labeled Connection (LblConn)</b>
Number of Labeled connection on this vserver

<b>Push Labeled Connection (PushLbl)</b>
Number of labels for this push vserver.

<b>Deferred Request (DefReq)</b>
Number of deferred request on this vserver

<b>Invalid Request/Response (IvldReqRsp)</b>
Number invalid requests/responses on this vserver

<b>Invalid Request/Response Dropped (IvldReqRspDrp)</b>
Number invalid requests/responses dropped on this vserver

<b>Current Server Est connections (SvrEstConn)</b>
Number of server connections in ESTABLISHED state.



##rename lb vserver

Renames a load balancing virtual server.


##Synopsys

rename lb vserver &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the virtual server.

<b>newName</b>
New name for the virtual server.



##Example

rename lb vserver http_vsvr http_vsvr_new

