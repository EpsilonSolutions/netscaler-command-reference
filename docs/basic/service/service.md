#service

The following operations can be performed on "service":


[add](#add-service) | [rm](#rm-service) | [set](#set-service) | [unset](#unset-service) | [bind](#bind-service) | [unbind](#unbind-service) | [enable](#enable-service) | [disable](#disable-service) | [show](#show-service) | [rename](#rename-service) | [stat](#stat-service)

##add service

Creates a service on the NetScaler appliance. If the service is domain based, before you create the service, create the server entry by using the add server command. Then, in this command, specify the Server parameter.


##Synopsys

add service &lt;name>@ (&lt;IP>@ | &lt;serverName>@) &lt;serviceType> &lt;port> [-clearTextPort &lt;port>] [-cacheType &lt;cacheType>] [-maxClient &lt;positive_integer>] [-healthMonitor ( YES | NO )] [-maxReq &lt;positive_integer>] [-cacheable ( YES | NO )] [-cip ( ENABLED | DISABLED )  [&lt;cipHeader>]] [-usip ( YES | NO )] [-pathMonitor ( YES | NO )] [-pathMonitorIndv ( YES | NO )] [-useproxyport ( YES | NO )] [-sc ( ON | OFF )] [-sp ( ON | OFF )] [-rtspSessionidRemap ( ON | OFF )] [-cltTimeout &lt;secs>] [-svrTimeout &lt;secs>] [-CustomServerID &lt;string>] [-CKA ( YES | NO )] [-TCPB ( YES | NO )] [-CMP ( YES | NO )] [-maxBandwidth &lt;positive_integer>] [-accessDown ( YES | NO )] [-monThreshold &lt;positive_integer>] [-state ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-hashId &lt;positive_integer>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-td &lt;positive_integer>] [-processLocal ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the service. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the service has been created.

<b>IP</b>
IP to assign to the service.

<b>serverName</b>
Name of the server that hosts the service.

<b>serviceType</b>
Protocol in which data is exchanged with the service.
Possible values: HTTP, FTP, TCP, UDP, SSL, SSL_BRIDGE, SSL_TCP, DTLS, NNTP, RPCSVR, DNS, ADNS, SNMP, RTSP, DHCPRA, ANY, SIP_UDP, DNS_TCP, ADNS_TCP, MYSQL, MSSQL, ORACLE, RADIUS, RDP, DIAMETER, SSL_DIAMETER, TFTP

<b>port</b>
Port number of the service.

<b>clearTextPort</b>
Port to which clear text data must be sent after the appliance decrypts incoming SSL traffic. Applicable to transparent SSL services.
Minimum value: 1

<b>cacheType</b>
Cache type supported by the cache server.
Possible values: TRANSPARENT, REVERSE, FORWARD

<b>maxClient</b>
Maximum number of simultaneous open connections to the service.
Maximum value: 4294967294

<b>healthMonitor</b>
Monitor the health of this service. Available settings function as follows:
YES - Send probes to check the health of the service.
NO - Do not send probes to check the health of the service. With the NO option, the appliance shows the service as UP at all times.
Possible values: YES, NO
Default value: YES

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service. 
Note: Connection requests beyond this value are rejected.
Maximum value: 65535

<b>cacheable</b>
Use the transparent cache redirection virtual server to forward requests to the cache server.
Note: Do not specify this parameter if you set the Cache Type parameter.
Possible values: YES, NO
Default value: NO

<b>cip</b>
Before forwarding a request to the service, insert an HTTP header with the client's IPv4 or IPv6 address as its value. Used if the server needs the client's IP address for security, accounting, or other purposes, and setting the Use Source IP parameter is not a viable option.
Possible values: ENABLED, DISABLED

<b>cipHeader</b>
Name for the HTTP header whose value must be set to the IP address of the client. Used with the Client IP parameter. If you set the Client IP parameter, and you do not specify a name for the header, the appliance uses the header name specified for the global Client IP Header parameter (the cipHeader parameter in the set ns param CLI command or the Client IP Header parameter in the Configure HTTP Parameters dialog box at System &gt; Settings &gt; Change HTTP parameters). If the global Client IP Header parameter is not specified, the appliance inserts a header with the name "client-ip."

<b>usip</b>
Use the client's IP address as the source IP address when initiating a connection to the server. When creating a service, if you do not set this parameter, the service inherits the global Use Source IP setting (available in the enable ns mode and disable ns mode CLI commands, or in the System &gt; Settings &gt; Configure modes &gt; Configure Modes dialog box). However, you can override this setting after you create the service.
Possible values: YES, NO

<b>pathMonitor</b>
Path monitoring for clustering
Possible values: YES, NO

<b>pathMonitorIndv</b>
Individual Path monitoring decisions
Possible values: YES, NO

<b>useproxyport</b>
Use the proxy port as the source port when initiating connections with the server. With the NO setting, the client-side connection port is used as the source port for the server-side connection. 
Note: This parameter is available only when the Use Source IP (USIP) parameter is set to YES.
Possible values: YES, NO

<b>sc</b>
State of SureConnect for the service.
Possible values: ON, OFF
Default value: OFF

<b>sp</b>
Enable surge protection for the service.
Possible values: ON, OFF

<b>rtspSessionidRemap</b>
Enable RTSP session ID mapping for the service.
Possible values: ON, OFF
Default value: OFF

<b>cltTimeout</b>
Time, in seconds, after which to terminate an idle client connection.
Maximum value: 31536000

<b>svrTimeout</b>
Time, in seconds, after which to terminate an idle server connection.
Maximum value: 31536000

<b>CustomServerID</b>
Unique identifier for the service. Used when the persistency type for the virtual server is set to Custom Server ID.
Default value: "None"

<b>serverID</b>
The  identifier for the service. This is used when the persistency type is set to Custom Server ID.

<b>CKA</b>
Enable client keep-alive for the service.
Possible values: YES, NO

<b>TCPB</b>
Enable TCP buffering for the service.
Possible values: YES, NO

<b>CMP</b>
Enable compression for the service.
Possible values: YES, NO

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, allocated to the service.
Maximum value: 4294967287

<b>accessDown</b>
Use Layer 2 mode to bridge the packets sent to this service if it is marked as DOWN. If the service is DOWN, and this parameter is disabled, the packets are dropped.
Possible values: YES, NO
Default value: NO

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.
Maximum value: 65535

<b>state</b>
Initial state of the service.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>downStateFlush</b>
Flush all active transactions associated with a service whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tcpProfileName</b>
Name of the TCP profile that contains TCP configuration settings for the service.

<b>httpProfileName</b>
Name of the HTTP profile that contains HTTP configuration settings for the service.

<b>hashId</b>
A numerical identifier that can be used by hash based load balancing methods. Must be unique for each service.
Minimum value: 1

<b>comment</b>
Any information about the service.

<b>appflowLog</b>
Enable logging of AppFlow information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Network profile to use for the service.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>processLocal</b>
By turning on this option packets destined to a service in a cluster will not under go any steering. Turn this option for single packet request response mode or when the upstream device is performing a proper RSS for connection based distribution.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add service http_svc 10.102.1.112 http 80	The below command adds the service web_svc1 for the server web_serv1, web_svc2 for web_serv2 and web_svc3 for web_serv3.	add service web_svc[1-3] web_serv[1-3] http 80 

##rm service

Removes a service.


##Synopsys

rm service &lt;name>@


##Arguments

<b>name</b>
Name of the service.



##Example

rm service http_svc	To remove services svc1, svc2 and svc3 in one go use the following command:	rm service svc[1-3]

##set service

Modifies the parameters of an existing service.


##Synopsys

set service &lt;name>@ [-IPAddress &lt;ip_addr|ipv6_addr|*>@] [-maxClient &lt;positive_integer>] [-maxReq &lt;positive_integer>] [-cacheable ( YES | NO )] [-cip ( ENABLED | DISABLED )  [&lt;cipHeader>]] [-usip ( YES | NO )] [-pathMonitor ( YES | NO )] [-pathMonitorIndv ( YES | NO )] [-useproxyport ( YES | NO )] [-sc ( ON | OFF )] [-sp ( ON | OFF )] [-rtspSessionidRemap ( ON | OFF )] [-healthMonitor ( YES | NO )] [-cltTimeout &lt;secs>] [-svrTimeout &lt;secs>] [-CustomServerID &lt;string>] [-CKA ( YES | NO )] [-TCPB ( YES | NO )] [-CMP ( YES | NO )] [-maxBandwidth &lt;positive_integer>] [-accessDown ( YES | NO )] [-monThreshold &lt;positive_integer>] [-weight &lt;positive_integer>  &lt;monitorName>] [-downStateFlush ( ENABLED | DISABLED )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-hashId &lt;positive_integer>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-processLocal ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the service for which to modify parameters.

<b>IPAddress</b>
The new IP address of the service.

<b>maxClient</b>
Maximum number of simultaneous open connections to the service.
Maximum value: 4294967294

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service. 
Note: Connection requests beyond this value are rejected.
Maximum value: 65535

<b>cacheable</b>
Use the transparent cache redirection virtual server to forward requests to the cache server.
Note: Do not specify this parameter if you set the Cache Type parameter.
Possible values: YES, NO
Default value: NO

<b>cip</b>
Before forwarding a request to the service, insert an HTTP header with the client's IPv4 or IPv6 address as its value. Used if the server needs the client's IP address for security, accounting, or other purposes, and setting the Use Source IP parameter is not a viable option.
Possible values: ENABLED, DISABLED

<b>usip</b>
Use the client's IP address as the source IP address when initiating a connection to the server. When creating a service, if you do not set this parameter, the service inherits the global Use Source IP setting (available in the enable ns mode and disable ns mode CLI commands, or in the System &gt; Settings &gt; Configure modes &gt; Configure Modes dialog box). However, you can override this setting after you create the service.
Possible values: YES, NO

<b>pathMonitor</b>
Path monitoring for clustering
Possible values: YES, NO

<b>pathMonitorIndv</b>
Individual Path monitoring decisions
Possible values: YES, NO

<b>useproxyport</b>
Use the proxy port as the source port when initiating connections with the server. With the NO setting, the client-side connection port is used as the source port for the server-side connection. 
Note: This parameter is available only when the Use Source IP (USIP) parameter is set to YES.
Possible values: YES, NO

<b>sc</b>
State of SureConnect for the service.
Possible values: ON, OFF
Default value: OFF

<b>sp</b>
Enable surge protection for the service.
Possible values: ON, OFF

<b>rtspSessionidRemap</b>
Enable RTSP session ID mapping for the service.
Possible values: ON, OFF
Default value: OFF

<b>healthMonitor</b>
Monitor the health of this service. Available settings function as follows:
YES - Send probes to check the health of the service.
NO - Do not send probes to check the health of the service. With the NO option, the appliance shows the service as UP at all times.
Possible values: YES, NO
Default value: YES

<b>cltTimeout</b>
Time, in seconds, after which to terminate an idle client connection.
Maximum value: 31536000

<b>svrTimeout</b>
Time, in seconds, after which to terminate an idle server connection.
Maximum value: 31536000

<b>CustomServerID</b>
Unique identifier for the service. Used when the persistency type for the virtual server is set to Custom Server ID.
Default value: "None"

<b>serverID</b>
The  identifier for the service. This is used when the persistency type is set to Custom Server ID.

<b>CKA</b>
Enable client keep-alive for the service.
Possible values: YES, NO

<b>TCPB</b>
Enable TCP buffering for the service.
Possible values: YES, NO

<b>CMP</b>
Enable compression for the service.
Possible values: YES, NO

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, allocated to the service.
Maximum value: 4294967287

<b>accessDown</b>
Use Layer 2 mode to bridge the packets sent to this service if it is marked as DOWN. If the service is DOWN, and this parameter is disabled, the packets are dropped.
Possible values: YES, NO
Default value: NO

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.
Maximum value: 65535

<b>weight</b>
Weight to assign to the monitor-service binding. When a monitor is UP, the weight assigned to its binding with the service determines how much the monitor contributes toward keeping the health of the service above the value configured for the Monitor Threshold parameter.
Minimum value: 1
Maximum value: 100

<b>downStateFlush</b>
Flush all active transactions associated with a service whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tcpProfileName</b>
Name of the TCP profile that contains TCP configuration settings for the service.

<b>httpProfileName</b>
Name of the HTTP profile that contains HTTP configuration settings for the service.

<b>hashId</b>
A numerical identifier that can be used by hash based load balancing methods. Must be unique for each service.
Minimum value: 1

<b>comment</b>
Any information about the service.

<b>appflowLog</b>
Enable logging of AppFlow information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Network profile to use for the service.

<b>processLocal</b>
By turning on this option packets destined to a service in a cluster will not under go any steering. Turn this option for single packet request response mode or when the upstream device is performing a proper RSS for connection based distribution.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set service http_svc -maxClient 100	The following command sets IP address 10.102.27.53 for service svc1, 10.102.27.54 for svc2 and 10.102.27.55 for svc3.	set service svc[1-3] -IPAddress 10.102.27.[53-55]

##unset service

Removes the parameter settings of the specified service. Attributes for which a default value is available revert to their default values..Refer to the set  service command for meanings of the arguments.


##Synopsys

unset service &lt;name>@ [-maxClient] [-maxReq] [-cacheable] [-cip] [-usip] [-pathMonitor] [-pathMonitorIndv] [-useproxyport] [-sc] [-sp] [-rtspSessionidRemap] [-CustomServerID] [-CKA] [-TCPB] [-CMP] [-maxBandwidth] [-accessDown] [-monThreshold] [-cltTimeout] [-riseApbrStatsMsgCode] [-svrTimeout] [-tcpProfileName] [-httpProfileName] [-hashId] [-appflowLog] [-netProfile] [-processLocal] [-cipHeader] [-healthMonitor] [-downStateFlush] [-comment]


##Example

unset service http_svc -maxClient	To unset maxclients for services svc1, svc2 and svc3, the following command can be used:	unset service svc[1-3] -maxClient

##bind service

Binds a policy or a monitor to a service.


##Synopsys

bind service &lt;name>@ (-policyName &lt;string> | (-monitorName &lt;string>@  [-monState ( ENABLED | DISABLED )]  [-weight &lt;positive_integer>]  [-passive]))


##Arguments

<b>name</b>
Name of the service to which to bind a policy or monitor.

<b>policyName</b>
Name of the policy to bind to the service.

<b>monitorName</b>
Name of the monitor to bind to the service.



##Example

bind service svc1 -policyName pol1	To bind svc1, svc2 and svc3 to the policy pol1 you can use the following command:	bind service svc[1-3] -policyName pol1

##unbind service

Unbinds a policy or monitor from the specified service.


##Synopsys

unbind service &lt;name>@ (-policyName &lt;string> | -monitorName &lt;string>@)


##Arguments

<b>name</b>
Name of the service from which to unbind a policy or monitor.

<b>policyName</b>
Name of the policy to unbind.

<b>monitorName</b>
Name of the monitor assigned to the service.



##Example

unbind service http_svc -policyName pol1	To unbind a policy called pol1 on services svc1, svc2 and svc3, use the following command:	unbind service svc[1-3] -policyName pol1

##enable service

Enables a service.


##Synopsys

enable service &lt;name>@


##Arguments

<b>name</b>
Name of the service.



##Example

enable service http_svc	To enable svc1, svc2 and svc3 in one go use the following command:	enable service svc[1-3]

##disable service

Disables a service.


##Synopsys

disable service &lt;name>@ [&lt;delay>] [-graceFul ( YES | NO )]


##Arguments

<b>name</b>
Name of the service.

<b>delay</b>
Time, in seconds, allocated to the NetScaler appliance for a graceful shutdown of the service. During this period, new requests are sent to the service only for clients who already have persistent sessions on the appliance. Requests from new clients are load balanced among other available services. After the delay time expires, no requests are sent to the service, and the service is marked as unavailable (OUT OF SERVICE).

<b>graceFul</b>
Shut down gracefully, not accepting any new connections, and disabling the service when all of its connections are closed.
Possible values: YES, NO
Default value: NO



##Example

disable service http_svc 10	To disable svc1, svc2 and svc3 in one go use the following command:	disable service svc[1-3] 10

##show service

Displays a list of all services configured on the NetScaler appliance, or the configuration details of the specified service.


##Synopsys

show service [&lt;name> | -all | -internal]show service bindings - alias for 'show svcbindings'


##Arguments

<b>name</b>
Name of the service for which to display configuration details.

<b>all</b>
Display both user-configured and dynamically learned services.

<b>internal</b>
Display only dynamically learned services.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>numOfconnections</b>
This will tell the number of client side connections are still open.

<b>serverName</b>
The name of the server for which a service has created.

<b>policyName</b>
The name of the policyname for which this service is bound

<b>serviceType</b>
The type of service

<b>serviceConfTpye</b>
The configuration type of the serviceNOTE: This attribute is deprecated.This will no longer show the correct information. Use the serviceConfType option instead.

<b>serviceConfType</b>
The configuration type of the serviceNOTE: This attribute is deprecated.This will no longer show the correct information. Use the serviceConfType2 option instead.

<b>serviceConfType2</b>
The configuration type of the service (Internal/Dynamic/Configured).

<b>port</b>
Port number of the service.

<b>value</b>
SSL status.

<b>clearTextPort</b>
The clear-text port number where clear-text data is sent. Used with SSL offload service

<b>gslb</b>
The GSLB option for the corresponding virtual server.

<b>cacheType</b>
Cache type supported by the cache server.

<b>maxClient</b>
Maximum number of simultaneous open connections to the service.

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service. 
Note: Connection requests beyond this value are rejected.

<b>cacheable</b>
Use the transparent cache redirection virtual server to forward requests to the cache server.
Note: Do not specify this parameter if you set the Cache Type parameter.

<b>cip</b>
Before forwarding a request to the service, insert an HTTP header with the client's IPv4 or IPv6 address as its value. Used if the server needs the client's IP address for security, accounting, or other purposes, and setting the Use Source IP parameter is not a viable option.

<b>cipHeader</b>
The client IP header.

<b>usip</b>
The use of client's IP Address option.

<b>pathMonitor</b>
Path monitoring for clustering

<b>pathMonitorIndv</b>
Individual Path monitoring for decisions.

<b>useproxyport</b>
The use of client's Port.

<b>sc</b>
The state of SureConnect for the service.

<b>weight</b>
The weight for the specified monitor.

<b>state</b>
Initial state of the service.

<b>sp</b>
Enable surge protection for the service.

<b>rtspSessionidRemap</b>
Enable RTSP session ID mapping for the service.

<b>failedprobes</b>
Number of the current failed monitoring probes.

<b>cltTimeout</b>
The idle time in seconds after which the client connection is terminated.

<b>totalprobes</b>
The total number of probs sent.

<b>svrTimeout</b>
The idle time in seconds after which the server connection is terminated.

<b>totalfailedprobes</b>
The total number of failed probs.

<b>publicIP</b>
public ip

<b>publicPort</b>
public port

<b>CustomServerID</b>
The  identifier for the service. Used when the persistency type is set to Custom Server ID.

<b>serverID</b>
The  identifier for the service. This is used when the persistency type is set to Custom Server ID.NOTE: This attribute is deprecated.Instead of integer now serverId will be a string and you can use -customserverid instead of -serverID.

<b>CKA</b>
Enable client keep-alive for the service.

<b>TCPB</b>
Enable TCP buffering for the service.

<b>processLocal</b>
By turning on this option packets destined to a service in a cluster will not under go any steering. Turn this option for single packet request response mode or when the upstream device is performing a proper RSS for connection based distribution.

<b>CMP</b>
Enable compression for the service.

<b>maxBandwidth</b>
The maximum bandwidth in kbps allowed for the service

<b>accessDown</b>
The option to allow access to disabled or down services. If enabled, all packets to the service are bridged; if disabled, they are dropped.

<b>svrState</b>
The state of the service

<b>delay</b>
The remaining time in seconds for the service to be disabled

<b>IPAddress</b>
The IP address of the server.

<b>monitorName</b>
The monitor Names.

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.

<b>monState</b>
The running state of the monitor on this service.

<b>monStatCode</b>
The code indicating the monitor response.

<b>lastresponse</b>
The string form of monstatcode.

<b>responseTime</b>
Response time of this monitor.

<b>riseApbrStatsMsgCode</b>
The code indicating the rise apbr status.

<b>riseApbrStatsMsgCode2</b>
The code indicating other rise stats.

<b>monStatParam1</b>
First parameter for use with message code.

<b>monStatParam2</b>
Second parameter for use with message code.

<b>monStatParam3</b>
Third parameter for use with message code.

<b>downStateFlush</b>
Flush all active transactions associated with a service whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>stateChangeTimemSec</b>
Time at which last state change happened. Milliseconds part.

<b>timeSinceLastStateChange</b>
Time in milliseconds since the last state change.NOTE: This attribute is deprecated.This will no longer show the correct information. Use the ticksSinceLastStateChange option instead.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>StateUpdateReason</b>
Checks state update reason on the secondary node.

<b>ClMonOwner</b>
Tells the mon owner of the service.

<b>ClMonView</b>
Tells the view id of the monitoring owner.

<b>tcpProfileName</b>
Name of the TCP profile.

<b>httpProfileName</b>
Name of the HTTP profile that contains HTTP configuration settings for the service.

<b>hashId</b>
A numerical identifier that can be used by hash based load balancing methods. Must be unique for each service.

<b>graceFul</b>
Indicates graceful shutdown of the service. System will wait for all outstanding connections to this service to be closed before disabling the service.

<b>comment</b>
Comments associated with this service.

<b>monitorTotalProbes</b>
Total number of probes sent to monitor this service.

<b>monitorTotalFailedProbes</b>
Total number of failed probes

<b>monitorCurrentFailedProbes</b>
Total number of currently failed probes

<b>stateflag</b>
stateflag

<b>healthMonitor</b>
Monitor the health of this service. Available settings function as follows:
YES - Send probes to check the health of the service.
NO - Do not send probes to check the health of the service. With the NO option, the appliance shows the service as UP at all times.

<b>appflowLog</b>
Enable logging of AppFlow information.

<b>netProfile</b>
Network profile to use for the service.

<b>svccfgFlags</b>
Contains the information about config info like internal/configured service

<b>serviceIPstr</b>
This field has been intorduced to show the dbs services ip

<b>svcMonFlags</b>
to store the flags of monitor bound to it

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>passive</b>
Indicates if load monitor is passive. A passive load monitor does not remove service from LB decision when threshold is breached.

<b>oracleServerVersion</b>
Oracle server version

<b>devno</b>

<b>count</b>



##Example

The following is sample output of the show service -all command:4 configured services:1)      svc1 (10.124.99.12:80) - HTTP        State: UP     Max Conn: 0     Max Req: 0      Use Source IP: NO     Client Keepalive(CKA): NO    TCP Buffering(TCPB): NO    HTTP Compression(CMP): NO    Idle timeout: Client: 180 sec   Server: 360 sec    Client IP: DISABLED2)  svc_3 (10.100.100.3:53) - DNS   State: UP    Max Conn: 0     Max Req: 0      Use Source IP: NO    Client Keepalive(CKA): NO    TCP Buffering(TCPB): NO    HTTP Compression(CMP): NO    Idle timeout: Client: 180 sec   Server: 360 sec    Client IP: DISABLED3)  tsvc1 (77.45.32.45:80) - HTTP   State: UP    Max Conn: 0     Max Req: 0      Use Source IP: NO    Client Keepalive(CKA): NO    TCP Buffering(TCPB): NO    HTTP Compression(CMP): NO    Idle timeout: Client: 180 sec   Server: 360 sec    Client IP: DISABLED4)  foosvc (10.124.99.13:7979) - HTTP  State: UP    Max Conn: 0     Max Req: 0      Use Source IP: NO    Client Keepalive(CKA): NO    TCP Buffering(TCPB): NO    HTTP Compression(CMP): NO    Idle timeout: Client: 180 sec   Server: 360 sec    Client IP: DISABLED

##rename service

Renames a service.


##Synopsys

rename service &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the service to be renamed.

<b>newName</b>
New name for the service. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

rename service svc1 svcnew

##stat service

Displays statistics that have been collected for the specified service.


##Synopsys

stat service [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the service.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Throughput (Mbps) (Throughput)</b>
Number of bytes received or sent by this service (Mbps).

<b>Average server TTFB (SvrTTFB)</b>
Average TTFB between the NetScaler appliance and the server.TTFB is the time interval between sending the request packet to a service and receiving the first response from the service

<b>IP address (IP)</b>
The IP address on which the service is running.

<b>Port (port)</b>
The port on which the service is running.

<b>Service type (Type)</b>
The service type of this service.Possible values are ADNS, DNS, MYSQL, RTSP, SSL_DIAMETER, ADNS_TCP, DNS_TCP, NNTP, SIP_UDP, SSL_TCP, ANY, FTP, RADIUS, SNMP, TCP, DHCPRA, HTTP, RDP, SSL, TFTP, DIAMETER, MSSQL, RPCSVR, SSL_BRIDGE, UDP

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

<b>Current client connections (ClntConn)</b>
Number of current client connections.

<b>Requests in surge queue (SurgeQ)</b>
Number of requests in the surge queue.

<b>Current server connections (SvrConn)</b>
Number of current connections to the actual servers behind the virtual server.

<b>Current Server Est connections (SvrEstConn)</b>
Number of server connections in ESTABLISHED state.

<b>Connections in reuse pool (ReuseP)</b>
Number of requests in the idle queue/reuse pool.

<b>Maximum server connections (MaxConn)</b>
Maximum open connections allowed on this service.

<b>Current load on the service (Load)</b>
Load on the service that is calculated from the bound load based monitor.

<b>Current flags on the service (CurtFlags)</b>
Current flags on the service for internal use in display handlers.

<b>Service hits (Hits)</b>
Number of times that the service has been provided.

<b>ActvTrans</b>
Number of active transactions handled by this service. (Including those in the surge queue.)
    Active Transaction means number of transactions currently served by the server including those waiting in the SurgeQ

<b>Total Packets rcvd (PktRx)</b>
Total number of packets received by this service or virtual server.

<b>Total Packets sent (PktTx)</b>
Total number of packets sent.



