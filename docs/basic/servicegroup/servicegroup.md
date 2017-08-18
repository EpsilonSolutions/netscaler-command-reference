#serviceGroup

The following operations can be performed on "serviceGroup":


[add](#add-servicegroup) | [rm](#rm-servicegroup) | [set](#set-servicegroup) | [unset](#unset-servicegroup) | [bind](#bind-servicegroup) | [unbind](#unbind-servicegroup) | [enable](#enable-servicegroup) | [disable](#disable-servicegroup) | [show](#show-servicegroup) | [stat](#stat-servicegroup) | [rename](#rename-servicegroup)

##add serviceGroup

Creates a service group. You can group similar services into a service group and use them as a single entity.


##Synopsys

add serviceGroup &lt;serviceGroupName>@ &lt;serviceType> [-cacheType &lt;cacheType>] [-td &lt;positive_integer>] [-maxClient &lt;positive_integer>] [-maxReq &lt;positive_integer>] [-cacheable ( YES | NO )] [-cip ( ENABLED | DISABLED )  [&lt;cipHeader>]] [-usip ( YES | NO )] [-pathMonitor ( YES | NO )] [-pathMonitorIndv ( YES | NO )] [-useproxyport ( YES | NO )] [-healthMonitor ( YES | NO )] [-sp ( ON | OFF )] [-rtspSessionidRemap ( ON | OFF )] [-cltTimeout &lt;secs>] [-svrTimeout &lt;secs>] [-CKA ( YES | NO )] [-TCPB ( YES | NO )] [-CMP ( YES | NO )] [-maxBandwidth &lt;positive_integer>] [-monThreshold &lt;positive_integer>] [-state ( ENABLED | DISABLED )] [-downStateFlush ( ENABLED | DISABLED )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-autoScale &lt;autoScale>  -memberPort &lt;port>] [-monConnectionClose ( RESET | FIN )]


##Arguments

<b>serviceGroupName</b>
Name of the service group. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the name is created.

<b>serviceType</b>
Protocol used to exchange data with the service.
Possible values: HTTP, FTP, TCP, UDP, SSL, SSL_BRIDGE, SSL_TCP, DTLS, NNTP, RPCSVR, DNS, ADNS, SNMP, RTSP, DHCPRA, ANY, SIP_UDP, SIP_TCP, SIP_SSL, DNS_TCP, ADNS_TCP, MYSQL, MSSQL, ORACLE, RADIUS, RADIUSListener, RDP, DIAMETER, SSL_DIAMETER, TFTP, SMPP, PPTP, GRE, SYSLOGTCP, SYSLOGUDP, FIX, SSL_FIX, USER_TCP, USER_SSL_TCP

<b>cacheType</b>
Cache type supported by the cache server.
Possible values: TRANSPARENT, REVERSE, FORWARD

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>maxClient</b>
Maximum number of simultaneous open connections for the service group.
Minimum value: 0
Maximum value: 4294967294

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service group. 
Note: Connection requests beyond this value are rejected.
Minimum value: 0
Maximum value: 65535

<b>cacheable</b>
Use the transparent cache redirection virtual server to forward the request to the cache server.
Note: Do not set this parameter if you set the Cache Type.
Possible values: YES, NO
Default value: NO

<b>cip</b>
Insert the Client IP header in requests forwarded to the service.
Possible values: ENABLED, DISABLED

<b>cipHeader</b>
Name of the HTTP header whose value must be set to the IP address of the client. Used with the Client IP parameter. If client IP insertion is enabled, and the client IP header is not specified, the value of Client IP Header parameter or the value set by the set ns config command is used as client's IP header name.

<b>usip</b>
Use client's IP address as the source IP address when initiating connection to the server. With the NO setting, which is the default, a mapped IP (MIP) address or subnet IP (SNIP) address is used as the source IP address to initiate server side connections.
Possible values: YES, NO

<b>pathMonitor</b>
Path monitoring for clustering
Possible values: YES, NO

<b>pathMonitorIndv</b>
Individual Path monitoring decisions.
Possible values: YES, NO

<b>useproxyport</b>
Use the proxy port as the source port when initiating connections with the server. With the NO setting, the client-side connection port is used as the source port for the server-side connection. 
Note: This parameter is available only when the Use Source IP (USIP) parameter is set to YES.
Possible values: YES, NO

<b>healthMonitor</b>
Monitor the health of this service.  Available settings function as follows:
YES - Send probes to check the health of the service.
NO - Do not send probes to check the health of the service. With the NO option, the appliance shows the service as UP at all times.
Possible values: YES, NO
Default value: YES

<b>sp</b>
Enable surge protection for the service group.
Possible values: ON, OFF
Default value: OFF

<b>rtspSessionidRemap</b>
Enable RTSP session ID mapping for the service group.
Possible values: ON, OFF
Default value: OFF

<b>cltTimeout</b>
Time, in seconds, after which to terminate an idle client connection.
Maximum value: 31536000

<b>svrTimeout</b>
Time, in seconds, after which to terminate an idle server connection.
Maximum value: 31536000

<b>CKA</b>
Enable client keep-alive for the service group.
Possible values: YES, NO

<b>TCPB</b>
Enable TCP buffering for the service group.
Possible values: YES, NO

<b>CMP</b>
Enable compression for the specified service.
Possible values: YES, NO

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, allocated for all the services in the service group.
Minimum value: 0
Maximum value: 4294967287

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.
Minimum value: 0
Maximum value: 65535

<b>state</b>
Initial state of the service group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>downStateFlush</b>
Flush all active transactions associated with all the services in the service group whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tcpProfileName</b>
Name of the TCP profile that contains TCP configuration settings for the service group.

<b>httpProfileName</b>
Name of the HTTP profile that contains HTTP configuration settings for the service group.

<b>comment</b>
Any information about the service group.

<b>appflowLog</b>
Enable logging of AppFlow information for the specified service group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Network profile for the service group.

<b>autoScale</b>
Auto scale option for a servicegroup
Possible values: DISABLED, DNS, POLICY
Default value: DISABLED

<b>memberPort</b>
member port

<b>monConnectionClose</b>
Close monitoring connections by sending the service a connection termination message with the specified bit set.
Possible values: RESET, FIN
Default value: NONE



##Example

add servicegroup http_svc_group http	To add service groups sgrp1, sgrp2 and sgrp3 at one go use the following command:	add servicegroup sgrp[1-3] http

##rm serviceGroup

Removes a service group.


##Synopsys

rm serviceGroup &lt;serviceGroupName>@


##Arguments

<b>serviceGroupName</b>
Name of the service group.



##Example

rm servicegroup http_svc_group	To remove multiple servicegroups at once, the following command can be used:	rm servicegroup http_svc_group[1-3]

##set serviceGroup

Modifies the specified parameters of a service group.


##Synopsys

set serviceGroup &lt;serviceGroupName>@ [(&lt;serverName>@  &lt;port>  [-weight &lt;positive_integer>]  [-CustomServerID &lt;string>]  [-hashId &lt;positive_integer>]) | -maxClient &lt;positive_integer> | -maxReq &lt;positive_integer> | -cacheable ( YES | NO ) | -cip ( ENABLED | DISABLED ) | &lt;cipHeader> | -usip ( YES | NO ) | -useproxyport ( YES | NO ) | -sp ( ON | OFF ) | -rtspSessionidRemap ( ON | OFF ) | -cltTimeout &lt;secs> | -svrTimeout &lt;secs> | -CKA ( YES | NO ) | -TCPB ( YES | NO ) | -CMP ( YES | NO ) | -maxBandwidth &lt;positive_integer> | -monThreshold &lt;positive_integer> | -downStateFlush ( ENABLED | DISABLED )] [-monitorName &lt;string>  -weight &lt;positive_integer>] [-healthMonitor ( YES | NO )] [-pathMonitor ( YES | NO )] [-pathMonitorIndv ( YES | NO )] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-netProfile &lt;string>] [-monConnectionClose ( RESET | FIN )]


##Arguments

<b>serviceGroupName</b>
Name of the service group.

<b>serverName</b>
Name of the server to which to bind the service group.

<b>port</b>
Server port number.

<b>weight</b>
weight of the monitor that is bound to servicegroup.
Minimum value: 1

<b>CustomServerID</b>
The identifier for this IP:Port pair. Used when the persistency type is set to Custom Server ID.
Default value: "None"

<b>hashId</b>
The hash identifier for the service. This must be unique for each service. This parameter is used by hash based load balancing methods.
Minimum value: 1

<b>monitorName</b>
Name of the monitor bound to the service group. Used to assign a weight to the monitor.

<b>maxClient</b>
Maximum number of simultaneous open connections for the service group.
Minimum value: 0
Maximum value: 4294967294

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service group. 
Note: Connection requests beyond this value are rejected.
Minimum value: 0
Maximum value: 65535

<b>healthMonitor</b>
Monitor the health of this service.  Available settings function as follows:
YES - Send probes to check the health of the service.
NO - Do not send probes to check the health of the service. With the NO option, the appliance shows the service as UP at all times.
Possible values: YES, NO
Default value: YES

<b>cacheable</b>
Use the transparent cache redirection virtual server to forward the request to the cache server.
Note: Do not set this parameter if you set the Cache Type.
Possible values: YES, NO
Default value: NO

<b>cip</b>
Insert the Client IP header in requests forwarded to the service.
Possible values: ENABLED, DISABLED

<b>cipHeader</b>
CIP Header.

<b>usip</b>
Use client's IP address as the source IP address when initiating connection to the server. With the NO setting, which is the default, a mapped IP (MIP) address or subnet IP (SNIP) address is used as the source IP address to initiate server side connections.
Possible values: YES, NO

<b>pathMonitor</b>
Path monitoring for clustering
Possible values: YES, NO

<b>pathMonitorIndv</b>
Individual Path monitoring decisions.
Possible values: YES, NO

<b>useproxyport</b>
Use the proxy port as the source port when initiating connections with the server. With the NO setting, the client-side connection port is used as the source port for the server-side connection. 
Note: This parameter is available only when the Use Source IP (USIP) parameter is set to YES.
Possible values: YES, NO

<b>sp</b>
Enable surge protection for the service group.
Possible values: ON, OFF
Default value: OFF

<b>rtspSessionidRemap</b>
Enable RTSP session ID mapping for the service group.
Possible values: ON, OFF
Default value: OFF

<b>cltTimeout</b>
Time, in seconds, after which to terminate an idle client connection.
Maximum value: 31536000

<b>svrTimeout</b>
Time, in seconds, after which to terminate an idle server connection.
Maximum value: 31536000

<b>CKA</b>
Enable client keep-alive for the service group.
Possible values: YES, NO

<b>TCPB</b>
Enable TCP buffering for the service group.
Possible values: YES, NO

<b>CMP</b>
Enable compression for the specified service.
Possible values: YES, NO

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, allocated for all the services in the service group.
Minimum value: 0
Maximum value: 4294967287

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.
Minimum value: 0
Maximum value: 65535

<b>downStateFlush</b>
Flush all active transactions associated with all the services in the service group whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tcpProfileName</b>
Name of the TCP profile that contains TCP configuration settings for the service group.

<b>httpProfileName</b>
Name of the HTTP profile that contains HTTP configuration settings for the service group.

<b>comment</b>
Any information about the service group.

<b>appflowLog</b>
Enable logging of AppFlow information for the specified service group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>netProfile</b>
Network profile for the service group.

<b>monConnectionClose</b>
Close monitoring connections by sending the service a connection termination message with the specified bit set.
Possible values: RESET, FIN
Default value: NONE



##Example

set servicegroup http_svc_group -maxClient 100	To set the attribute maxclient for multiple servicegroups at once, use the following command:	set servicegroup http_svc_group[1-3] -maxClient 100

##unset serviceGroup

Removes the attributes of the specified service group. Attributes for which a default value is available revert to their default values..Refer to the set  serviceGroup command for meanings of the arguments.


##Synopsys

unset serviceGroup &lt;serviceGroupName>@ [&lt;serverName>@  &lt;port>  [-weight]  [-CustomServerID]  [-hashId]  [-riseApbrStatsMsgCode]] [-maxClient] [-maxReq] [-cacheable] [-cip] [-usip] [-useproxyport] [-sp] [-rtspSessionidRemap] [-cltTimeout] [-svrTimeout] [-CKA] [-TCPB] [-CMP] [-maxBandwidth] [-monThreshold] [-tcpProfileName] [-httpProfileName] [-appflowLog] [-netProfile] [-monitorName] [-weight] [-healthMonitor] [-cipHeader] [-pathMonitor] [-pathMonitorIndv] [-downStateFlush] [-comment] [-monConnectionClose]


##Example

unset servicegroup http_svc_group -maxClient

##bind serviceGroup

Binds a service to a service group.


##Synopsys

bind serviceGroup &lt;serviceGroupName> ((&lt;IP>@  &lt;port>) | &lt;serverName>@ | ((-monitorName &lt;string>@  [-monState ( ENABLED | DISABLED )]  [-passive]) | -CustomServerID &lt;string> | -state ( ENABLED | DISABLED ) | -hashId &lt;positive_integer> | |)) [-weight &lt;positive_integer>]


##Arguments

<b>serviceGroupName</b>
Name of the service group.

<b>IP</b>
IP address of the server that hosts the service. Mutually exclusive with the Server Name parameter.

<b>serverName</b>
Name of the server that hosts the service. Mutually exclusive with the IP address parameter.

<b>port</b>
Port number of the service. Each service must have a unique port number.

<b>monitorName</b>
The name of the service or a service group to which the monitor is to be bound.

<b>monState</b>
Administrative state assigned to the monitor and service group binding. If set to disabled, the service group is not monitored.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>passive</b>
Indicates if load monitor is passive. A passive load monitor does not remove service from LB decision when threshold is breached.

<b>weight</b>

<b>CustomServerID</b>
Unique service identifier. Used when the persistency type for the virtual server is set to Custom Server ID.
Default value: "None"

<b>state</b>
Initial state of the service after binding.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>hashId</b>
Unique numerical identifier used by hash based load balancing methods to identify a service.
Minimum value: 1



##Example

bind servicegroup http_svc_group 10.102.27.153 80	To bind multiple servers to a servicegroup, following command can be used:	bind servicegroup http_svc_group 10.102.27.[153-155] 80

##unbind serviceGroup

Unbinds a service or a monitor from a service group.


##Synopsys

unbind serviceGroup &lt;serviceGroupName> ((&lt;IP>@  &lt;port>) | &lt;serverName>@ | -monitorName &lt;string>@)


##Arguments

<b>serviceGroupName</b>
Name of the service group.

<b>IP</b>
IP address of the server that hosts the service. Mutually exclusive with the Server Name parameter.

<b>serverName</b>
Name of the server that hosts the service. Mutually exclusive with the IP Address parameter.

<b>port</b>
Port number of the service.

<b>monitorName</b>
Name of the monitor to bind to the service group.



##Example

unbind servicegroup http_svc_group 10.102.27.153 80	To unbind multiple servers following command can be used:	unbind servicegroup http_svc_group 10.102.27.[153-155] 80

##enable serviceGroup

Enables a service group or a member of the service group.


##Synopsys

enable serviceGroup &lt;serviceGroupName>@ [&lt;serverName>@  &lt;port>]


##Arguments

<b>serviceGroupName</b>
Name of the service group.

<b>serverName</b>
Name of the server that hosts the service.

<b>port</b>
Port number of the service to be enabled.



##Example

enable servicegroup http_svc_group	To enable multiple service groups at one go use the following command:	enable servicegroup http_svc_group[1-3]

##disable serviceGroup

Disables a service group or a member of a service group. To disable a service group, provide only the service group name. To disable only a member of a service group, in addition to the service group name, provide the name of the server that hosts the service, and the port number of the service.


##Synopsys

disable serviceGroup &lt;serviceGroupName>@ [&lt;serverName>@  &lt;port>] [-delay &lt;secs>] [-graceFul ( YES | NO )]


##Arguments

<b>serviceGroupName</b>
Name of the service group.

<b>serverName</b>
Name of the server that hosts the service.

<b>port</b>
Port number of the service.

<b>delay</b>
Time, in seconds, allocated for a shutdown of the services in the service group. During this period, new requests are sent to the service only for clients who already have persistent sessions on the appliance. Requests from new clients are load balanced among other available services. After the delay time expires, no requests are sent to the service, and the service is marked as unavailable (OUT OF SERVICE).

<b>graceFul</b>
Wait for all existing connections to the service to terminate before shutting down the service.
Possible values: YES, NO
Default value: NO



##Example

disable servicegroup http_svc_group 10.102.27.153 80 -delay 10	To disable multiple servicegroups use the following command:	disable servicegroup http_svc_group[1-3] 10.102.27.[153-155] 80 -delay 30

##show serviceGroup

Displays the specified service group's binding information.


##Synopsys

show serviceGroup [&lt;serviceGroupName> | -includeMembers]


##Arguments

<b>serviceGroupName</b>
Name of the service group.

<b>includeMembers</b>
Display the members of the listed service groups in addition to their settings. Can be specified when no service group name is provided in the command. In that case, the details displayed for each service group are identical to the details displayed when a service group name is provided, except that bound monitors are not displayed.



##Outputs

<b>numOfconnections</b>
This will tell the number of client side connections are still open.

<b>serviceType</b>
Protocol used to exchange data with the service.

<b>port</b>
The port number of the service to be enabled.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>serviceConfTpye</b>

<b>serviceConfType</b>
The configuration type of the service group.

<b>value</b>
SSL Status.

<b>cacheType</b>
Cache type supported by the cache server.

<b>maxClient</b>
Maximum number of simultaneous open connections for the service group.

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service group. 
Note: Connection requests beyond this value are rejected.

<b>cacheable</b>
The state of cache on the service.

<b>cip</b>
Insert the Client IP header in requests forwarded to the service.

<b>cipHeader</b>
CIP Header.

<b>usip</b>
Use client's IP address as the source IP address when initiating connection to the server. With the NO setting, which is the default, a mapped IP (MIP) address or subnet IP (SNIP) address is used as the source IP address to initiate server side connections.

<b>pathMonitor</b>
Path monitoring for clustering

<b>pathMonitorIndv</b>
Individual Path monitoring decisions.

<b>useproxyport</b>
The use of client's Port.

<b>monweight</b>
weight of the monitor that is bound to servicegroup.

<b>sc</b>
Whether SureConnect is enabled on this service or not.

<b>sp</b>
Enable surge protection for the service group.

<b>rtspSessionidRemap</b>
Enable RTSP session ID mapping for the service group.

<b>cltTimeout</b>
Time, in seconds, after which to terminate an idle client connection.

<b>svrTimeout</b>
Time, in seconds, after which to terminate an idle server connection.

<b>CKA</b>
Enable client keep-alive for the service group.

<b>TCPB</b>
Enable TCP buffering for the service group.

<b>CMP</b>
Enable compression for the specified service.

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, allocated for all the services in the service group.

<b>state</b>
Monitor state.

<b>svrState</b>
The state of the service

<b>delay</b>
The remaning time in seconds for the service to be disabled

<b>IP</b>
IP Address.

<b>serverName</b>
The name of the server to be changed.

<b>monitorName</b>
Monitor name.

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.

<b>monState</b>
The running state of the monitor on this service.

<b>weight</b>
weight of the monitor that is bound to servicegroup.

<b>CustomServerID</b>
The identifier for this IP:Port pair. Used when the persistency type is set to Custom Server ID.

<b>serverID</b>
The  identifier for the service. This is used when the persistency type is set to Custom Server ID.

<b>monStatCode</b>
The code indicating the monitor response.

<b>monStatParam1</b>
First parameter for use with message code.

<b>monStatParam2</b>
Second parameter for use with message code.

<b>monStatParam3</b>
Third parameter for use with message code.

<b>monitorTotalProbes</b>
Total number of probes sent to monitor this service.

<b>monitorTotalFailedProbes</b>
Total number of failed probes

<b>monitorCurrentFailedProbes</b>
Total number of currently failed probes

<b>downStateFlush</b>
Flush all active transactions associated with all services in the service group whose state transitions from UP to DOWN. Do not enable this option for applications that must complete their transactions.

<b>lastresponse</b>
The string form of monstatcode.

<b>stateChangeTimeSec</b>
Time when last state change occurred. Seconds part.

<b>stateChangeTimemSec</b>
Time when last state change occurred. Milliseconds part.

<b>timeSinceLastStateChange</b>
Time in milliseconds since the last state change.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>StateUpdateReason</b>
Checks state update reason on the secondary node.

<b>ClMonOwner</b>
Tells the mon owner of the service.

<b>ClMonView</b>
Tells the view id of the monitoring owner.

<b>groupCount</b>
Servicegroup Count

<b>comment</b>
Any information about the service group.

<b>tcpProfileName</b>
Name of the TCP profile that contains TCP configuration settings for the service group.

<b>httpProfileName</b>
Name of the HTTP profile that contains HTTP configuration settings for the service group.

<b>hashId</b>
The hash identifier for the service. This must be unique for each service. This parameter is used by hash based load balancing methods.

<b>riseApbrStatsMsgCode</b>
The code indicating the rise apbr status.

<b>riseApbrStatsMsgCode2</b>
The code indicating other rise stats.

<b>graceFul</b>
Indicates graceful shutdown of the service. System will wait for all outstanding connections to this service to be closed before disabling the service.

<b>healthMonitor</b>
Monitor the health of this service.  Available settings function as follows:
YES - Send probes to check the health of the service.
NO - Do not send probes to check the health of the service. With the NO option, the appliance shows the service as UP at all times.

<b>appflowLog</b>
Enable logging of AppFlow information for the specified service group.

<b>netProfile</b>
Network profile for the service group.

<b>autoScale</b>
Auto scale option for a servicegroup

<b>memberPort</b>
member port

<b>serviceIPstr</b>
This field has been intorduced to show the dbs services ip

<b>serviceGroupEntName2</b>

<b>passive</b>
Indicates if load monitor is passive. A passive load monitor does not remove service from LB decision when threshold is breached.

<b>serviceGroupeffectivestate</b>
Indicates the effective servicegroup state based on the state of the bound service items.If all services are UP the effective state is UP, if all are DOWN its DOWN,if all are OFS its OFS.If atleast one serviceis UP and rest are either DOWN or OFS, the effective state is PARTIAL-UP.If atleast one bound service is DOWN and rest are OFS the effective state is PARTIAL DOWN.

<b>monConnectionClose</b>
Close monitoring connections by sending the service a connection termination message with the specified bit set.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##stat serviceGroup

Displays configuration statistics of the specified service group or all the service groups configured on the appliance.


##Synopsys

stat serviceGroup [&lt;serviceGroupName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>serviceGroupName</b>
Name of the service group for which to display settings.

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

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>Service type (Type)</b>
The service type of this service.Possible values are ADNS, DNS, MYSQL, RTSP, SSL_DIAMETER, ADNS_TCP, DNS_TCP, NNTP, SIP_UDP, SSL_TCP, ANY, FTP, RADIUS, SNMP, TCP, DHCPRA, HTTP, RDP, SSL, TFTP, DIAMETER, MSSQL, RPCSVR, SSL_BRIDGE, UDP



##rename serviceGroup

Renames a service group.


##Synopsys

rename serviceGroup &lt;serviceGroupName>@ &lt;newName>@


##Arguments

<b>serviceGroupName</b>
Existing name of the service group.

<b>newName</b>
New name for the service group.



##Example

rename service svcgrp1 svcgrp-new1

