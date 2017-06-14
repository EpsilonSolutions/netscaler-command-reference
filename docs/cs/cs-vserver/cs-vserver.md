#cs vserver

The following operations can be performed on "cs vserver":


[add](#add-cs-vserver) | [rm](#rm-cs-vserver) | [set](#set-cs-vserver) | [unset](#unset-cs-vserver) | [bind](#bind-cs-vserver) | [unbind](#unbind-cs-vserver) | [enable](#enable-cs-vserver) | [disable](#disable-cs-vserver) | [show](#show-cs-vserver) | [stat](#stat-cs-vserver) | [rename](#rename-cs-vserver)

##add cs vserver

Creates a content switching virtual server.


##Synopsys

add cs vserver &lt;name> [-td &lt;positive_integer>] &lt;serviceType> ((&lt;IPAddress>  [-range &lt;positive_integer>]) | (-IPPattern &lt;ippat>  -IPMask &lt;ipmask>)) &lt;port> [-state ( ENABLED | DISABLED )] [-stateupdate ( ENABLED | DISABLED )] [-cacheable ( YES | NO )] [-redirectURL &lt;URL>] [-cltTimeout &lt;secs>] [-precedence ( RULE | URL )] [-caseSensitive ( ON | OFF )] [-soMethod &lt;soMethod>] [-soPersistence ( ENABLED | DISABLED )] [-soPersistenceTimeOut &lt;positive_integer>] [-soThreshold &lt;positive_integer>] [-soBackupAction &lt;soBackupAction>] [-redirectPortRewrite ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-backupVServer &lt;string>] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-insertVserverIPPort &lt;insertVserverIPPort>  [&lt;vipHeader>] ] [-rtspNat ( ON | OFF )] [-AuthenticationHost &lt;string>] [-Authentication ( ON | OFF )] [-Listenpolicy &lt;expression>  [-Listenpriority &lt;positive_integer>]] [-authn401 ( ON | OFF )] [-authnVsName &lt;string>] [-push ( ENABLED | DISABLED )] [-pushVserver &lt;string>] [-pushLabel &lt;expression>] [-pushMultiClients ( YES | NO )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-dbProfileName &lt;string>] [-oracleServerVersion ( 10G | 11G )] [-comment &lt;string>] [-mssqlServerVersion &lt;mssqlServerVersion>] [-l2Conn ( ON | OFF )] [-mysqlProtocolVersion &lt;positive_integer>] [-mysqlServerVersion &lt;string>] [-mysqlCharacterSet &lt;positive_integer>] [-mysqlServerCapabilities &lt;positive_integer>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )] [-authnProfile &lt;string>]


##Arguments

<b>name</b>
Name for the content switching virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. 
Cannot be changed after the CS virtual server is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, \\?my server\\? or \\?my server\\?).

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>serviceType</b>
Protocol used by the virtual server.
Possible values: HTTP, SSL, TCP, FTP, RTSP, SSL_TCP, UDP, DNS, SIP_UDP, ANY, RADIUS, RDP, MYSQL, MSSQL, DIAMETER, SSL_DIAMETER, DNS_TCP, ORACLE

<b>IPAddress</b>
IP address of the content switching virtual server.

<b>IPPattern</b>
IP address pattern, in dotted decimal notation, for identifying packets to be accepted by the virtual server. The IP Mask parameter specifies which part of the destination IP address is matched against the pattern. Mutually exclusive with the IP Address parameter. 
For example, if the IP pattern assigned to the virtual server is 198.51.100.0 and the IP mask is 255.255.240.0 (a forward mask), the first 20 bits in the destination IP addresses are matched with the first 20 bits in the pattern. The virtual server accepts requests with IP addresses that range from 198.51.96.1 to 198.51.111.254. You can also use a pattern such as 0.0.2.2 and a mask such as 0.0.255.255 (a reverse mask).
If a destination IP address matches more than one IP pattern, the pattern with the longest match is selected, and the associated virtual server processes the request. For example, if the virtual servers, vs1 and vs2, have the same IP pattern, 0.0.100.128, but different IP masks of 0.0.255.255 and 0.0.224.255, a destination IP address of 198.51.100.128 has the longest match with the IP pattern of vs1. If a destination IP address matches two or more virtual servers to the same extent, the request is processed by the virtual server whose port number matches the port number in the request.

<b>range</b>
Number of consecutive IP addresses, starting with the address specified by the IP Address parameter, to include in a range of addresses assigned to this virtual server.
Default value: 1
Minimum value: 1
Maximum value: 254

<b>port</b>
Port number for content switching virtual server.
Minimum value: 1

<b>state</b>
Initial state of the load balancing virtual server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>stateupdate</b>
Enable state updates for a specific content switching virtual server. By default, the Content Switching virtual server is always UP, regardless of the state of the Load Balancing virtual servers bound to it. This parameter interacts with the global setting as follows:
Global Level | Vserver Level | Result
ENABLED      ENABLED        ENABLED
ENABLED      DISABLED       ENABLED
DISABLED     ENABLED        ENABLED
DISABLED     DISABLED       DISABLED
If you want to enable state updates for only some content switching virtual servers, be sure to disable the state update parameter.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cacheable</b>
Use this option to specify whether a virtual server, used for load balancing or content switching, routes requests to the cache redirection virtual server before sending it to the configured servers.
Possible values: YES, NO
Default value: NO

<b>redirectURL</b>
URL to which traffic is redirected if the virtual server becomes unavailable. The service type of the virtual server should be either HTTP or SSL.
Caution: Make sure that the domain in the URL does not match the domain specified for a content switching policy. If it does, requests are continuously redirected to the unavailable virtual server.

<b>cltTimeout</b>
Idle time, in seconds, after which the client connection is terminated. The default values are:
180 seconds for HTTP/SSL-based services.
9000 seconds for other TCP-based services.
120 seconds for DNS-based services.
120 seconds for other UDP-based services.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>precedence</b>
Type of precedence to use for both RULE-based and URL-based policies on the content switching virtual server. With the default (RULE) setting, incoming requests are evaluated against the rule-based content switching policies. If none of the rules match, the URL in the request is evaluated against the URL-based content switching policies.
Possible values: RULE, URL
Default value: CS_PRIORITY_RULE

<b>caseSensitive</b>
Consider case in URLs (for policies that use URLs instead of RULES). For example, with the ON setting, the URLs /a/1.html and /A/1.HTML are treated differently and can have different targets (set by content switching policies). With the OFF setting, /a/1.html and /A/1.HTML are switched to the same target.
Possible values: ON, OFF
Default value: ON

<b>soMethod</b>
Type of spillover used to divert traffic to the backup virtual server when the primary virtual server reaches the spillover threshold. Connection spillover is based on the number of connections. Bandwidth spillover is based on the total Kbps of incoming and outgoing traffic.
Possible values: CONNECTION, DYNAMICCONNECTION, BANDWIDTH, HEALTH, NONE

<b>soPersistence</b>
Maintain source-IP based persistence on primary and backup virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>soPersistenceTimeOut</b>
Time-out value, in minutes, for spillover persistence.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>soThreshold</b>
Depending on the spillover method, the maximum number of connections or the maximum total bandwidth (Kbps) that a virtual server can handle before spillover occurs.
Minimum value: 1
Maximum value: 4294967287

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists
Possible values: DROP, ACCEPT, REDIRECT

<b>redirectPortRewrite</b>
State of port rewrite while performing HTTP redirect.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>downStateFlush</b>
Flush all active transactions associated with a virtual server whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>backupVServer</b>
Name of the backup virtual server that you are configuring. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the backup virtual server is created. You can assign a different backup virtual server or rename the existing virtual server.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks.

<b>disablePrimaryOnDown</b>
Continue forwarding the traffic to backup virtual server even after the primary server comes UP from the DOWN state.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>insertVserverIPPort</b>
Insert the virtual server's VIP address and port number in the request header. Available values function as follows:
        VIPADDR - Header contains the vserver's IP address and port number without any translation.
        OFF     - The virtual IP and port header insertion option is disabled.
        V6TOV4MAPPING - Header contains the mapped IPv4 address corresponding to the IPv6 address of the vserver and the port number. An IPv6 address can be mapped to a user-specified IPv4 address using the set ns ip6 command.
Possible values: OFF, VIPADDR, V6TOV4MAPPING

<b>rtspNat</b>
Enable network address translation (NAT) for real-time streaming protocol (RTSP) connections.
Possible values: ON, OFF
Default value: OFF

<b>AuthenticationHost</b>
FQDN of the authentication virtual server. The service type of the virtual server should be either HTTP or SSL.

<b>Authentication</b>
Authenticate users who request a connection to the content switching virtual server.
Possible values: ON, OFF
Default value: OFF

<b>Listenpolicy</b>
String specifying the listen policy for the content switching virtual server. Can be either the name of an existing expression or an in-line expression.
Default value: "none"

<b>Listenpriority</b>
Integer specifying the priority of the listen policy. A higher number specifies a lower priority. If a request matches the listen policies of more than one virtual server the virtual server whose listen policy has the highest priority (the lowest priority number) accepts the request.
Default value: 101
Minimum value: 0
Maximum value: 100

<b>authn401</b>
Enable HTTP 401-response based authentication.
Possible values: ON, OFF
Default value: OFF

<b>authnVsName</b>
Name of authentication virtual server that authenticates the incoming user requests to this content switching virtual server.

<b>push</b>
Process traffic with the push virtual server that is bound to this content switching virtual server (specified by the Push VServer parameter). The service type of the push virtual server should be either HTTP or SSL.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>pushVserver</b>
Name of the load balancing virtual server, of type PUSH or SSL_PUSH, to which the server pushes updates received on the client-facing load balancing virtual server.

<b>pushLabel</b>
Expression for extracting the label from the response received from server. This string can be either an existing rule name or an inline expression. The service type of the virtual server should be either HTTP or SSL.
Default value: "none"

<b>pushMultiClients</b>
Allow multiple Web 2.0 connections from the same client to connect to the virtual server and expect updates.
Possible values: YES, NO
Default value: NO

<b>tcpProfileName</b>
Name of the TCP profile containing TCP configuration settings for the virtual server.

<b>httpProfileName</b>
Name of the HTTP profile containing HTTP configuration settings for the virtual server. The service type of the virtual server should be either HTTP or SSL.

<b>dbProfileName</b>
Name of the DB profile.

<b>oracleServerVersion</b>
Oracle server version
Possible values: 10G, 11G
Default value: ORACLE_SERVER_10G

<b>comment</b>
Information about this virtual server.

<b>mssqlServerVersion</b>
The version of the MSSQL server
Possible values: 70, 2000, 2000SP1, 2005, 2008, 2008R2, 2012
Default value: TDS_PROT_2008B

<b>l2Conn</b>
Use L2 Parameters to identify a connection
Possible values: ON, OFF

<b>mysqlProtocolVersion</b>
The protocol version returned by the mysql vserver.
Default value: 10

<b>mysqlServerVersion</b>
The server version string returned by the mysql vserver.
Default value: NSA_MYSQL_SERVER_VER_DEFAULT

<b>mysqlCharacterSet</b>
The character set returned by the mysql vserver.
Default value: 8

<b>mysqlServerCapabilities</b>
The server capabilities returned by the mysql vserver.
Default value: 41613

<b>appflowLog</b>
Enable logging appflow flow information
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
The name of the network profile.

<b>icmpVsrResponse</b>
Can be active or passive
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance, injects even if one virtual server set to ACTIVE is UP.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>authnProfile</b>
Name of the authentication profile to be used when authentication is turned on.



##Example

1.	You can use precedence when certain client attributes (e.g., browser type) require to be served with different content. All other clients can then be served from content distributed among the servers.If the precedence is configured as URL, the incoming request URL is evaluated against the content switching policies created with the -url argument. If none of the policies match, the request is applied against the content any switching policies created with the -rule argument.2.	Precedence can also be used when certain content (such as images) is the same for all clients, but other content (such as text) is different for different clients. In this case, the images will be served to all clients, but the text will be served to specific clients based on attributes such as Accept-Language.

##Related Commands

<ul><li><a href="../../../-p/-p">add cs policy</a></li></ul>



##rm cs vserver

Removes a content switching virtual server.


##Synopsys

rm cs vserver &lt;name>@ ...


##Arguments

<b>name</b>
Name of the virtual server to be removed.



##Example

rm vserver cs_vip

##set cs vserver

Modifies the configuration of a content switching virtual server.


##Synopsys

set cs vserver &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr|*>] [-IPPattern &lt;ippat>] [-IPMask &lt;ipmask>] [-stateupdate ( ENABLED | DISABLED )] [-precedence ( RULE | URL )] [-caseSensitive ( ON | OFF )] [-backupVServer &lt;string>] [-redirectURL &lt;URL>] [-cacheable ( YES | NO )] [-cltTimeout &lt;secs>] [-soMethod &lt;soMethod>] [-soPersistence ( ENABLED | DISABLED )] [-soPersistenceTimeOut &lt;positive_integer>] [-soThreshold &lt;positive_integer>] [-soBackupAction &lt;soBackupAction>] [-redirectPortRewrite ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-disablePrimaryOnDown ( ENABLED | DISABLED )] [-insertVserverIPPort &lt;insertVserverIPPort>  [&lt;vipHeader>] ] [-rtspNat ( ON | OFF )] [-AuthenticationHost &lt;string>] [-Authentication ( ON | OFF )] [-Listenpolicy &lt;expression>] [-Listenpriority &lt;positive_integer>] [-authn401 ( ON | OFF )] [-authnVsName &lt;string>] [-push ( ENABLED | DISABLED )] [-pushVserver &lt;string>] [-pushLabel &lt;expression>] [-pushMultiClients ( YES | NO )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-dbProfileName &lt;string>] [-comment &lt;string>] [-l2Conn ( ON | OFF )] [-mssqlServerVersion &lt;mssqlServerVersion>] [-mysqlProtocolVersion &lt;positive_integer>] [-oracleServerVersion ( 10G | 11G )] [-mysqlServerVersion &lt;string>] [-mysqlCharacterSet &lt;positive_integer>] [-mysqlServerCapabilities &lt;positive_integer>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-authnProfile &lt;string>] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )]


##Arguments

<b>name</b>
Identifies the virtual server name (created with the add cs vserver command).

<b>IPAddress</b>
The new IP address of the virtual server.

<b>IPPattern</b>
IP address pattern, in dotted decimal notation, for identifying packets to be accepted by the virtual server. The IP Mask parameter specifies which part of the destination IP address is matched against the pattern. Mutually exclusive with the IP Address parameter. 
For example, if the IP pattern assigned to the virtual server is 198.51.100.0 and the IP mask is 255.255.240.0 (a forward mask), the first 20 bits in the destination IP addresses are matched with the first 20 bits in the pattern. The virtual server accepts requests with IP addresses that range from 198.51.96.1 to 198.51.111.254. You can also use a pattern such as 0.0.2.2 and a mask such as 0.0.255.255 (a reverse mask).
If a destination IP address matches more than one IP pattern, the pattern with the longest match is selected, and the associated virtual server processes the request. For example, if the virtual servers, vs1 and vs2, have the same IP pattern, 0.0.100.128, but different IP masks of 0.0.255.255 and 0.0.224.255, a destination IP address of 198.51.100.128 has the longest match with the IP pattern of vs1. If a destination IP address matches two or more virtual servers to the same extent, the request is processed by the virtual server whose port number matches the port number in the request.

<b>IPMask</b>
IP mask, in dotted decimal notation, for the IP Pattern parameter. Can have leading or trailing non-zero octets (for example, 255.255.240.0 or 0.0.255.255). Accordingly, the mask specifies whether the first n bits or the last n bits of the destination IP address in a client request are to be matched with the corresponding bits in the IP pattern. The former is called a forward mask. The latter is called a reverse mask.

<b>stateupdate</b>
Enable state updates for a specific content switching virtual server. By default, the Content Switching virtual server is always UP, regardless of the state of the Load Balancing virtual servers bound to it. This parameter interacts with the global setting as follows:
Global Level | Vserver Level | Result
ENABLED      ENABLED        ENABLED
ENABLED      DISABLED       ENABLED
DISABLED     ENABLED        ENABLED
DISABLED     DISABLED       DISABLED
If you want to enable state updates for only some content switching virtual servers, be sure to disable the state update parameter.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>precedence</b>
The precedence on the content switching virtual server between rule-based and URL-based policies. The default precedence is set to RULE.
If the precedence is configured as RULE, the incoming request is applied against the content switching policies created with the -rule argument. If none of the rules match, then the URL in the request is applied against the content switching policies created with the -url option.
For example, this precedence can be used if certain client attributes (such as a specific type of browser) need to be served different content and all other clients can be served from the content distributed among the servers.
If the precedence is configured as URL, the incoming request URL is applied against the content switching policies created with the -url option. If none of the policies match, then the request is applied against the content switching policies created with the -rule option.
Also, this precedence can be used if some content (such as images) is the same for all clients, but other content (such as text) is different for different clients. In this case, the images will be served to all clients, but the text will be served to specific clients based on specific attributes, such as Accept-Language.
Possible values: RULE, URL
Default value: CS_PRIORITY_RULE

<b>caseSensitive</b>
The URL lookup case option on the content switching vserver.
If case sensitivity of a content switching virtual server is set to 'ON', the URLs /a/1.html and /A/1.HTML are treated differently and may have different targets (set by content switching policies).
If case sensitivity is set to 'OFF', the URLs /a/1.html and /A/1.HTML are treated the same, and will be switched to the same target.
Possible values: ON, OFF
Default value: ON

<b>backupVServer</b>
Name of the backup virtual server that you are configuring. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the backup virtual server is created. You can assign a different backup virtual server or rename the existing virtual server.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks.

<b>redirectURL</b>
The redirect URL for content switching.

<b>cacheable</b>
The option to specify whether a virtual server used for content switching will route requests to the cache redirection virtual server before sending it to the configured servers.
Possible values: YES, NO
Default value: NO

<b>cltTimeout</b>
Client timeout in seconds.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>soMethod</b>
The spillover factor. When traffic on the main virtual server reaches this threshold, additional traffic is sent to the backupvserver.
Possible values: CONNECTION, DYNAMICCONNECTION, BANDWIDTH, HEALTH, NONE

<b>soPersistence</b>
Maintain source-IP based persistence on primary and backup virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>soPersistenceTimeOut</b>
The spillover persistency entry timeout.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>soThreshold</b>
Depending on the spillover method, the maximum number of connections or the maximum total bandwidth (Kbps) that a virtual server can handle before spillover occurs.
Minimum value: 1
Maximum value: 4294967287

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists
Possible values: DROP, ACCEPT, REDIRECT

<b>redirectPortRewrite</b>
SSL redirect port rewrite.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>downStateFlush</b>
Flush all active transactions associated with a virtual server whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>disablePrimaryOnDown</b>
Continue forwarding the traffic to backup virtual server even after the primary server comes UP from the DOWN state.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>insertVserverIPPort</b>
The virtual IP and port header insertion option for the vserver.
* VIPADDR - Header contains the vserver's IP address and port number without any translation.
* OFF - The virtual IP and port header insertion option is disabled.
* V6TOV4MAPPING - Header contains the mapped IPv4 address that corresponds to the IPv6 address of the vserver and the port number. An IPv6 address can be mapped to a user-specified IPv4 address using the set ns ip6 command.
Possible values: OFF, VIPADDR, V6TOV4MAPPING

<b>rtspNat</b>
Enable network address translation (NAT) for real-time streaming protocol (RTSP) connections.
Possible values: ON, OFF
Default value: OFF

<b>AuthenticationHost</b>
FQDN of the authentication virtual server. The service type of the virtual server should be either HTTP or SSL.

<b>Authentication</b>
Authenticate users who request a connection to the content switching virtual server.
Possible values: ON, OFF
Default value: OFF

<b>Listenpolicy</b>
String specifying the listen policy for the content switching virtual server. Can be either the name of an existing expression or an in-line expression.
Default value: "none"

<b>Listenpriority</b>
Integer specifying the priority of the listen policy. A higher number specifies a lower priority. If a request matches the listen policies of more than one virtual server the virtual server whose listen policy has the highest priority (the lowest priority number) accepts the request.
Default value: 101
Minimum value: 0
Maximum value: 100

<b>authn401</b>
Enable HTTP 401-response based authentication.
Possible values: ON, OFF
Default value: OFF

<b>authnVsName</b>
Name of authentication virtual server that authenticates the incoming user requests to this content switching virtual server.

<b>push</b>
Process traffic with the push virtual server that is bound to this content switching virtual server (specified by the Push VServer parameter). The service type of the push virtual server should be either HTTP or SSL.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>pushVserver</b>
Name of the load balancing virtual server, of type PUSH or SSL_PUSH, to which the server pushes updates received on the client-facing load balancing virtual server.

<b>pushLabel</b>
Expression for extracting the label from the response received from server. This string can be either an existing rule name or an inline expression. The service type of the virtual server should be either HTTP or SSL.
Default value: "none"

<b>pushMultiClients</b>
Allow multiple Web 2.0 connections from the same client to connect to the virtual server and expect updates.
Possible values: YES, NO
Default value: NO

<b>tcpProfileName</b>
Name of the TCP profile containing TCP configuration settings for the virtual server.

<b>httpProfileName</b>
Name of the HTTP profile containing HTTP configuration settings for the virtual server. The service type of the virtual server should be either HTTP or SSL.

<b>dbProfileName</b>
Name of the DB profile.

<b>comment</b>
Information about this virtual server.

<b>l2Conn</b>
Use L2 Parameters to identify a connection
Possible values: ON, OFF

<b>mssqlServerVersion</b>
The version of the MSSQL server
Possible values: 70, 2000, 2000SP1, 2005, 2008, 2008R2, 2012
Default value: TDS_PROT_2008B

<b>mysqlProtocolVersion</b>
The protocol version returned by the mysql vserver.
Default value: 10

<b>oracleServerVersion</b>
Oracle server version
Possible values: 10G, 11G
Default value: ORACLE_SERVER_10G

<b>mysqlServerVersion</b>
The server version string returned by the mysql vserver.
Default value: NSA_MYSQL_SERVER_VER_DEFAULT

<b>mysqlCharacterSet</b>
The character set returned by the mysql vserver.
Default value: 8

<b>mysqlServerCapabilities</b>
The server capabilities returned by the mysql vserver.
Default value: 41613

<b>appflowLog</b>
Enable logging appflow flow information
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
The name of the network profile.

<b>authnProfile</b>
Name of the authentication profile to be used when authentication is turned on.

<b>icmpVsrResponse</b>
Can be active or passive
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance, injects even if one virtual server set to ACTIVE is UP.
Possible values: PASSIVE, ACTIVE
Default value: NS_VSR_PASSIVE



##Related Commands

<ul><li><a href="../../../-p/-p">add cs policy</a></li><li><a href="../../../s-p/s-p">show cs policy</a></li></ul>



##unset cs vserver

Unset the parameters of a content switching virtual server..Refer to the set cs vserver command for meanings of the arguments.


##Synopsys

unset cs vserver &lt;name> [-caseSensitive] [-backupVServer] [-cltTimeout] [-redirectURL] [-authn401] [-Authentication] [-AuthenticationHost] [-authnVsName] [-pushVserver] [-pushLabel] [-tcpProfileName] [-httpProfileName] [-dbProfileName] [-l2Conn] [-mysqlProtocolVersion] [-mysqlServerVersion] [-mysqlCharacterSet] [-mysqlServerCapabilities] [-appflowLog] [-netProfile] [-icmpVsrResponse] [-authnProfile] [-stateupdate] [-precedence] [-cacheable] [-soMethod] [-soPersistence] [-soPersistenceTimeOut] [-soThreshold] [-soBackupAction] [-redirectPortRewrite] [-downStateFlush] [-disablePrimaryOnDown] [-insertVserverIPPort] [-vipHeader] [-rtspNat] [-Listenpolicy] [-Listenpriority] [-push] [-pushMultiClients] [-comment] [-mssqlServerVersion] [-oracleServerVersion] [-RHIstate]


##Related Commands

<ul><li><a href="../../../-p/-p">add cs policy</a></li><li><a href="../../../s-p/s-p">show cs policy</a></li></ul>



##bind cs vserver

Binds a content switching virtual server to a content switching policy.


##Synopsys

bind cs vserver &lt;name> [-lbvserver &lt;string> | (-policyName &lt;string>  [-targetLBVserver &lt;string>]  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]  [-type ( REQUEST | RESPONSE )]  [-invoke  (&lt;labelType>  &lt;labelName>) ]  )]


##Arguments

<b>name</b>
Name of the content switching virtual server to which the content switching policy applies.

<b>lbvserver</b>
Name of the default Load Balancing vserver bound. If for a particular content none of the Content Switching policies is evaluated to TRUE, that traffic is switched to default Load Balancing vserver. .
Example: bind cs vserver cs1 -lbvserver lb1
Note: Use this parameter for default binding only.

<b>policyName</b>
Name of the content switching policy to bind to the content switching virtual server Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after a policy is created.
To bind a content switching policy, you need a content-based virtual server (content switching virtual server) and an address-based virtual server (load balancing virtual server). You can assign multiple policies to the virtual server pair. 
Note: When binding a CS virtual server to a default LB virtual server, the Policy Name parameter is optional.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my policy? or ?my policy?).

<b>targetVserver</b>
The virtual server name (created with the add lb vserver command) to which content will be switched.



##Example

	i)   bind cs vserver csw-vip1 -policyname csw-policy1 -priority 13	ii)  bind cs vserver csw-vip2 -policyname csw-ape-policy2 -priority 14 -gotoPriorityExpression NEXT	iii) bind cs vserver csw-vip3 -policyname rewrite-policy1 -priority 17 -gotoPriorityExpression 'HTTP.REQ.HEADER("a").COUNT' -flowtype REQUEST -invoke policylabel label1

##Related Commands

<ul><li><a href="../../../-p/-p">add cs policy</a></li><li><a href="../../../s-p/s-p">show cs policy</a></li></ul>



##unbind cs vserver

Unbinds the virtual server from the content switching policy.


##Synopsys

unbind cs vserver &lt;name> [(-policyName &lt;string>  [-type ( REQUEST | RESPONSE )]) | -lbvserver &lt;string>] [-priority &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the virtual server to unbind from the policy.

<b>policyName</b>
Name of the policy from which to unbind the content switching virtual server. Note: To unbind the content switching virtual server from the default policy, do not specify a value for this parameter.

<b>lbvserver</b>
The virtual server name (created with the add lb vserver command) to which content will be switched.
Default value: "default_lb"



##enable cs vserver

Enables a content switching virtual server.


##Synopsys

enable cs vserver &lt;name>@


##Arguments

<b>name</b>
Name of the content switching virtual server to enable.
Note: Virtual servers, when added, are enabled by default.



##Example

enable vserver cs_vip

##disable cs vserver

Disables a content switching virtual server.


##Synopsys

disable cs vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server to be disabled.



##Example

disable vserver cs_vip

##show cs vserver

Displays all existing content switching virtual servers, or just the specified virtual server.


##Synopsys

show cs vserver [&lt;name>]show cs vserver stats - alias for 'stat cs vserver'


##Arguments

<b>name</b>
Name of a content switching virtual server for which to display information, including the policies bound to the virtual server. To display a list of all configured Content Switching virtual servers, do not specify a value for this parameter.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>insertVserverIPPort</b>
The virtual IP and port header insertion option for the vserver.

<b>vipHeader</b>
The name of virtual IP and port header.

<b>IPAddress</b>
IP address of the content switching virtual server.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>IPPattern</b>
The IP address of the virtual server.

<b>IPMask</b>
The IP address mask of the virtual server.

<b>stateflag</b>

<b>value</b>
The ssl card status for the transparent ssl cs vserver.

<b>port</b>
Port number for content switching virtual server.

<b>range</b>
Number of consecutive IP addresses, starting with the address specified by the IP Address parameter, to include in a range of addresses assigned to this virtual server.

<b>serviceType</b>
Protocol used by the virtual server.

<b>ngname</b>
Nodegroup devno to which this csvserver belongs to

<b>type</b>
The bindpoint to which the policy is bound

<b>vsvrcfgflags</b>
Contains the config info of vserver to be used at validation

<b>state</b>
Initial state of the load balancing virtual server.

<b>sc</b>
The state of SureConnect the specified virtual server.

<b>stateupdate</b>
Enable state updates for a specific content switching virtual server. By default, the Content Switching virtual server is always UP, regardless of the state of the Load Balancing virtual servers bound to it. This parameter interacts with the global setting as follows:
Global Level | Vserver Level | Result
ENABLED      ENABLED        ENABLED
ENABLED      DISABLED       ENABLED
DISABLED     ENABLED        ENABLED
DISABLED     DISABLED       DISABLED
If you want to enable state updates for only some content switching virtual servers, be sure to disable the state update parameter.

<b>status</b>
Status.

<b>cacheType</b>
Cache type.

<b>redirect</b>
Redirect URL string.

<b>precedence</b>
Type of precedence to use for both RULE-based and URL-based policies on the content switching virtual server. With the default (RULE) setting, incoming requests are evaluated against the rule-based content switching policies. If none of the rules match, the URL in the request is evaluated against the URL-based content switching policies.

<b>redirectURL</b>
The redirect URL for content switching.

<b>Authentication</b>
Authentication.

<b>authn401</b>
HTTP 401 response based authentication.

<b>authnVsName</b>
Name of authentication virtual server that authenticates the incoming user requests to this content switching virtual server.

<b>caseSensitive</b>
Consider case in URLs (for policies that use URLs instead of RULES). For example, with the ON setting, the URLs /a/1.html and /A/1.HTML are treated differently and can have different targets (set by content switching policies). With the OFF setting, /a/1.html and /A/1.HTML are switched to the same target.

<b>homePage</b>
Home page.

<b>dnsVserverName</b>
DNS vserver name.

<b>domain</b>
Domain.

<b>rule</b>
Rule.

<b>policyName</b>
Policies bound to this vserver.

<b>hits</b>
Number of hits.

<b>piPolicyhits</b>
Number of hits.

<b>serviceName</b>
Service name.

<b>weight</b>
Weight for this service.

<b>cacheVserver</b>
Cache vserver name.

<b>targetVserver</b>
target vserver name.

<b>backupVServer</b>
Name of the backup virtual server that you are configuring. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the backup virtual server is created. You can assign a different backup virtual server or rename the existing virtual server.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks.

<b>priority</b>
Priority for the policy.

<b>cltTimeout</b>
Idle time, in seconds, after which the client connection is terminated. The default values are:
180 seconds for HTTP/SSL-based services.
9000 seconds for other TCP-based services.
120 seconds for DNS-based services.
120 seconds for other UDP-based services.

<b>Listenpolicy</b>
The string is listenpolicy configured for lb vserver

<b>Listenpriority</b>
This parameter is the priority for listen policy of LB Vserver.

<b>soMethod</b>
Type of spillover used to divert traffic to the backup virtual server when the primary virtual server reaches the spillover threshold. Connection spillover is based on the number of connections. Bandwidth spillover is based on the total Kbps of incoming and outgoing traffic.

<b>soPersistence</b>
Maintain source-IP based persistence on primary and backup virtual servers.

<b>soPersistenceTimeOut</b>
Time-out value, in minutes, for spillover persistence.

<b>soThreshold</b>
Depending on the spillover method, the maximum number of connections or the maximum total bandwidth (Kbps) that a virtual server can handle before spillover occurs.

<b>soBackupAction</b>
Action to be performed if spillover is to take effect, but no backup chain to spillover is usable or exists

<b>cacheable</b>
The state of caching.

<b>url</b>
URL string.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>redirectPortRewrite</b>
Redirect port rewrite.

<b>downStateFlush</b>
Flush all active transactions associated with a virtual server whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.

<b>disablePrimaryOnDown</b>
Tells whether traffic will continue reaching backup vservers even after primary comes UP from DOWN state.

<b>invoke</b>
Invoke flag.

<b>labelType</b>
The invocation type.

<b>labelName</b>
Name of the label invoked.

<b>gt2GB</b>
This argument has no effect.

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>stateChangeTimemSec</b>
Time at which last state change happened. Milliseconds part.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>rtspNat</b>
Enable network address translation (NAT) for real-time streaming protocol (RTSP) connections.

<b>AuthenticationHost</b>
FQDN of the authentication virtual server. The service type of the virtual server should be either HTTP or SSL.

<b>push</b>
Process traffic with the push virtual server that is bound to this content switching virtual server (specified by the Push VServer parameter). The service type of the push virtual server should be either HTTP or SSL.

<b>pushVserver</b>
Name of the load balancing virtual server, of type PUSH or SSL_PUSH, to which the server pushes updates received on the client-facing load balancing virtual server.

<b>pushLabel</b>
Expression for extracting the label from the response received from server. This string can be either an existing rule name or an inline expression. The service type of the virtual server should be either HTTP or SSL.

<b>pushMultiClients</b>
Allow multiple Web 2.0 connections from the same client to connect to the virtual server and expect updates.

<b>tcpProfileName</b>
Name of the TCP profile containing TCP configuration settings for the virtual server.

<b>httpProfileName</b>
Name of the HTTP profile containing HTTP configuration settings for the virtual server. The service type of the virtual server should be either HTTP or SSL.

<b>dbProfileName</b>
Name of the DB profile.

<b>comment</b>
Information about this virtual server.

<b>appfwPolicyFlag</b>

<b>flags</b>

<b>policySubType</b>

<b>oracleServerVersion</b>
Oracle server version

<b>mssqlServerVersion</b>
The version of the MSSQL server

<b>l2Conn</b>
Use L2 Parameters to identify a connection

<b>mysqlProtocolVersion</b>
The protocol version returned by the mysql vserver.

<b>mysqlServerVersion</b>
The server version string returned by the mysql vserver.

<b>mysqlCharacterSet</b>
The character set returned by the mysql vserver.

<b>mysqlServerCapabilities</b>
The server capabilities returned by the mysql vserver.

<b>appflowLog</b>
Enable logging appflow flow information

<b>netProfile</b>
The name of the network profile.

<b>icmpVsrResponse</b>
Can be active or passive

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance, injects even if one virtual server set to ACTIVE is UP.

<b>lbvserver</b>
Name of the default lb vserver bound. Use this param for Default binding only. For Example: bind cs vserver cs1 -lbvserver lb1

<b>targetLBVserver</b>
target vserver name.

<b>contentVsvrFlag</b>

<b>authnProfile</b>
Name of the authentication profile to be used when authentication is turned on.

<b>devno</b>

<b>count</b>



##Related Commands

<ul><li><a href="../../../s-p/s-p">show cs policy</a></li></ul>



##stat cs vserver

Displays statistics of all content switching virtual servers, or statistics for just the specified content switching virtual server.


##Synopsys

stat cs vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the content switching virtual server for which to display statistics. To display statistics for all configured Content Switching virtual servers, do not specify a value for this parameter.

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

<b>IP address (IP)</b>
The IP address on which the service is running.

<b>Port (port)</b>
The port on which the service is running.

<b>Vserver protocol (Protocol)</b>
Protocol associated with the vserver

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

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



##rename cs vserver

Renames a content switching virtual server.


##Synopsys

rename cs vserver &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the content switching virtual server.

<b>newName</b>
New name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my name? or ?my name?).



##Example

rename cs vserver cs1 cs2

