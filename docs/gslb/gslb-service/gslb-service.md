#gslb service

The following operations can be performed on "gslb service":


[add](#add-gslb-service) | [rm](#rm-gslb-service) | [set](#set-gslb-service) | [unset](#unset-gslb-service) | [bind](#bind-gslb-service) | [unbind](#unbind-gslb-service) | [show](#show-gslb-service) | [stat](#stat-gslb-service) | [rename](#rename-gslb-service)

##add gslb service

Creates a global server load balancing (GSLB) service.


##Synopsys

add gslb service &lt;serviceName> (-cnameEntry &lt;string> | &lt;IP> | &lt;serverName> | &lt;serviceType> | &lt;port> | -publicIP &lt;ip_addr|ipv6_addr|*> | -publicPort &lt;port> | -sitePersistence &lt;sitePersistence> | -sitePrefix &lt;string>) [-maxClient &lt;positive_integer>] [-healthMonitor ( YES | NO )] -siteName &lt;string> [-state ( ENABLED | DISABLED )] [-cip ( ENABLED | DISABLED )  [&lt;cipHeader>]] [-cookieTimeout &lt;mins>] [-cltTimeout &lt;secs>] [-svrTimeout &lt;secs>] [-maxBandwidth &lt;positive_integer>] [-downStateFlush ( ENABLED | DISABLED )] [-maxAAAUsers &lt;positive_integer>] [-monThreshold &lt;positive_integer>] [-hashId &lt;positive_integer>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )]


##Arguments

<b>serviceName</b>
Name for the GSLB service. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the GSLB service is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my gslbsvc" or 'my gslbsvc').

<b>cnameEntry</b>
Canonical name of the GSLB service. Used in CNAME-based GSLB.

<b>IP</b>
IP address for the GSLB service. Should represent a load balancing, content switching, or VPN virtual server on the NetScaler appliance, or the IP address of another load balancing device.

<b>serverName</b>
Name of the server hosting the GSLB service.

<b>serviceType</b>
Type of service to create.
Possible values: HTTP, FTP, TCP, UDP, SSL, SSL_BRIDGE, SSL_TCP, NNTP, ANY, SIP_UDP, SIP_TCP, SIP_SSL, RADIUS, RDP, RTSP, MYSQL, MSSQL, ORACLE
Default value: NSSVC_SERVICE_UNKNOWN

<b>port</b>
Port on which the load balancing entity represented by this GSLB service listens.
Minimum value: 1

<b>publicIP</b>
The public IP address that a NAT device translates to the GSLB service's private IP address. Optional.

<b>publicPort</b>
The public port associated with the GSLB service's public IP address. The port is mapped to the service's private port number. Applicable to the local GSLB service. Optional.

<b>maxClient</b>
The maximum number of open connections that the service can support at any given time. A GSLB service whose connection count reaches the maximum is not considered when a GSLB decision is made, until the connection count drops below the maximum.
Minimum value: 0
Maximum value: 4294967294

<b>healthMonitor</b>
Monitor the health of the GSLB service.
Possible values: YES, NO
Default value: YES

<b>siteName</b>
Name of the GSLB site to which the service belongs.

<b>state</b>
Enable or disable the service.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cip</b>
In the request that is forwarded to the GSLB service, insert a header that stores the client's IP address. Client IP header insertion is used in connection-proxy based site persistence.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cipHeader</b>
Name for the HTTP header that stores the client's IP address. Used with the Client IP option. If client IP header insertion is enabled on the service and a name is not specified for the header, the NetScaler appliance uses the name specified by the cipHeader parameter in the set ns param command or, in the GUI, the Client IP Header parameter in the Configure HTTP Parameters dialog box.

<b>sitePersistence</b>
Use cookie-based site persistence. Applicable only to HTTP and SSL GSLB services.
Possible values: ConnectionProxy, HTTPRedirect, NONE

<b>cookieTimeout</b>
Timeout value, in minutes, for the cookie, when cookie based site persistence is enabled.
Maximum value: 1440

<b>sitePrefix</b>
The site's prefix string. When the service is bound to a GSLB virtual server, a GSLB site domain is generated internally for each bound service-domain pair by concatenating the site prefix of the service and the name of the domain. If the special string NONE is specified, the site-prefix string is unset. When implementing HTTP redirect site persistence, the NetScaler appliance redirects GSLB requests to GSLB services by using their site domains.

<b>cltTimeout</b>
Idle time, in seconds, after which a client connection is terminated. Applicable if connection proxy based site persistence is used.
Maximum value: 31536000

<b>svrTimeout</b>
Idle time, in seconds, after which a server connection is terminated. Applicable if connection proxy based site persistence is used.
Maximum value: 31536000

<b>maxBandwidth</b>
Integer specifying the maximum bandwidth allowed for the service. A GSLB service whose bandwidth reaches the maximum is not considered when a GSLB decision is made, until its bandwidth consumption drops below the maximum.
Minimum value: 0

<b>downStateFlush</b>
Flush all active transactions associated with the GSLB service when its state transitions from UP to DOWN. Do not enable this option for services that must complete their transactions. Applicable if connection proxy based site persistence is used.
Possible values: ENABLED, DISABLED

<b>maxAAAUsers</b>
Maximum number of SSL VPN users that can be logged on concurrently to the VPN virtual server that is represented by this GSLB service. A GSLB service whose user count reaches the maximum is not considered when a GSLB decision is made, until the count drops below the maximum.
Minimum value: 0
Maximum value: 65535

<b>monThreshold</b>
Monitoring threshold value for the GSLB service. If the sum of the weights of the monitors that are bound to this GSLB service and are in the UP state is not equal to or greater than this threshold value, the service is marked as DOWN.
Minimum value: 0
Maximum value: 65535

<b>hashId</b>
Unique hash identifier for the GSLB service, used by hash based load balancing methods.
Minimum value: 1

<b>comment</b>
Any comments that you might want to associate with the GSLB service.

<b>appflowLog</b>
Enable logging appflow flow information
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

add gslb service sj_svc 203.12.123.12 http 80 -site san_jos

##rm gslb service

Removes a global server load balancing (GSLB) service configured on the appliance.


##Synopsys

rm gslb service &lt;serviceName>


##Arguments

<b>serviceName</b>
Name of the GSLB service.



##Example

rm gslb service sj_svc

##set gslb service

Modifies the specified parameters of a global server load balancing (GSLB) service.


##Synopsys

set gslb service &lt;serviceName> [-IPAddress &lt;ip_addr|ipv6_addr|*>] [-publicIP &lt;ip_addr|ipv6_addr|*>] [-publicPort &lt;port>] [-cip ( ENABLED | DISABLED )  [&lt;cipHeader>]] [-sitePersistence &lt;sitePersistence>] [-sitePrefix &lt;string>] [-maxClient &lt;positive_integer>] [-healthMonitor ( YES | NO )] [-maxBandwidth &lt;positive_integer>] [-downStateFlush ( ENABLED | DISABLED )] [-maxAAAUsers &lt;positive_integer>] [-viewName &lt;string>  &lt;viewIP>] [-monThreshold &lt;positive_integer>] [-weight &lt;positive_integer>  &lt;monitorName>] [-hashId &lt;positive_integer>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )]


##Arguments

<b>serviceName</b>
Name of the GSLB service.

<b>IPAddress</b>
The new IP address of the service.

<b>publicIP</b>
The public IP address that a NAT device translates to the GSLB service's private IP address. Optional.

<b>publicPort</b>
The public port associated with the GSLB service's public IP address. The port is mapped to the service's private port number. Applicable to the local GSLB service. Optional.
Minimum value: 1

<b>cip</b>
In the request that is forwarded to the GSLB service, insert a header that stores the client's IP address. Client IP header insertion is used in connection-proxy based site persistence.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cipHeader</b>
Name for the HTTP header that stores the client's IP address. Used with the Client IP option. If client IP header insertion is enabled on the service and a name is not specified for the header, the NetScaler appliance uses the name specified by the cipHeader parameter in the set ns param command or, in the GUI, the Client IP Header parameter in the Configure HTTP Parameters dialog box.

<b>sitePersistence</b>
Use cookie-based site persistence. Applicable only to HTTP and SSL GSLB services.
Possible values: ConnectionProxy, HTTPRedirect, NONE

<b>sitePrefix</b>
The site's prefix string. When the service is bound to a GSLB virtual server, a GSLB site domain is generated internally for each bound service-domain pair by concatenating the site prefix of the service and the name of the domain. If the special string NONE is specified, the site-prefix string is unset. When implementing HTTP redirect site persistence, the NetScaler appliance redirects GSLB requests to GSLB services by using their site domains.

<b>maxClient</b>
The maximum number of open connections that the service can support at any given time. A GSLB service whose connection count reaches the maximum is not considered when a GSLB decision is made, until the connection count drops below the maximum.
Minimum value: 0
Maximum value: 4294967294

<b>healthMonitor</b>
Monitor the health of the GSLB service.
Possible values: YES, NO
Default value: YES

<b>maxBandwidth</b>
Maximum bandwidth.
Minimum value: 0

<b>downStateFlush</b>
Flush all active transactions associated with the GSLB service when its state transitions from UP to DOWN. Do not enable this option for services that must complete their transactions. Applicable if connection proxy based site persistence is used.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxAAAUsers</b>
Maximum number of SSL VPN users that can be logged on concurrently to the VPN virtual server that is represented by this GSLB service. A GSLB service whose user count reaches the maximum is not considered when a GSLB decision is made, until the count drops below the maximum.
Minimum value: 0
Maximum value: 65535

<b>viewName</b>
Name of the DNS view of the service. A DNS view is used in global server load balancing (GSLB) to return a predetermined IP address to a specific group of clients, which are identified by using a DNS policy.

<b>viewIP</b>
IP address to be used for the given view

<b>monThreshold</b>
Monitoring threshold value for the GSLB service. If the sum of the weights of the monitors that are bound to this GSLB service and are in the UP state is not equal to or greater than this threshold value, the service is marked as DOWN.
Minimum value: 0
Maximum value: 65535

<b>weight</b>
Weight to assign to the monitor-service binding. A larger number specifies a greater weight. Contributes to the monitoring threshold, which determines the state of the service.
Minimum value: 1
Maximum value: 100

<b>monitorName</b>
Name of the monitor to bind to the service.

<b>hashId</b>
Unique hash identifier for the GSLB service, used by hash based load balancing methods.
Minimum value: 1

<b>comment</b>
Any comments that you might want to associate with the GSLB service.

<b>appflowLog</b>
Enable logging appflow flow information
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set gslb service sj_svc  -sitePersistence ConnectionProxy

##unset gslb service

Use this command to remove gslb service settings.Refer to the set gslb service command for meanings of the arguments.


##Synopsys

unset gslb service &lt;serviceName> [-publicIP] [-publicPort] [-cip] [-cipHeader] [-sitePersistence] [-sitePrefix] [-maxClient] [-healthMonitor] [-maxBandwidth] [-downStateFlush] [-maxAAAUsers] [-monThreshold] [-hashId] [-comment] [-appflowLog]


##bind gslb service

Binds a DNS view or a monitor to a global server load balancing (GSLB) service.


##Synopsys

bind gslb service &lt;serviceName> ((-viewName &lt;string>  &lt;viewIP>) | (-monitorName &lt;string>@  [-monState ( ENABLED | DISABLED )]  [-weight &lt;positive_integer>]))


##Arguments

<b>serviceName</b>
Name of the GSLB service.

<b>viewName</b>
Name of the DNS view of the service. A DNS view is used in global server load balancing (GSLB) to return a predetermined IP address to a specific group of clients, which are identified by using a DNS policy.

<b>viewIP</b>
IP address for the specified DNS view.

<b>monitorName</b>
Name of the monitor to bind to the GSLB service.

<b>monState</b>
Initial state of the GSLB monitor.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>weight</b>
Weight to assign to the monitor-service binding. A larger number specifies a greater weight. Contributes to the monitoring threshold, which determines the state of the service.
Default value: 1
Minimum value: 1
Maximum value: 100



##Example

bind gslb service -viewName privateview 1.2.3.4

##unbind gslb service

Unbinds a DNS view or a monitor from a global server load balancing (GSLB) service.


##Synopsys

unbind gslb service &lt;serviceName> (-viewName &lt;string> | -monitorName &lt;string>@)


##Arguments

<b>serviceName</b>
Name of the GSLB service.

<b>viewName</b>
Name of the DNS view of the service. A DNS view specifies the IP address that must be returned to clients accessing the service from a specific location.

<b>monitorName</b>
Name of the monitor to unbind.



##Example

unbind gslb service -viewName privateview

##show gslb service

Displays the parameters of all the global server load balancing (GSLB) services configured on the appliance, or the parameters of just the specified service, and statistics related to the service. To display the parameters of all the GSLB services, do not specify a service name.


##Synopsys

show gslb service [&lt;serviceName>]show gslb service stats - alias for 'stat gslb service'


##Arguments

<b>serviceName</b>
Name of the GSLB service.



##Outputs

<b>gslb</b>

<b>IPAddress</b>
IP address of the service

<b>IP</b>
IP address of the service

<b>serverName</b>
Name of the server hosting the GSLB service.

<b>serviceType</b>
Service type.

<b>port</b>
Port number of the service.

<b>publicIP</b>
Public ip of the service

<b>publicPort</b>
Public port of the service

<b>maxClient</b>
Maximum number of clients.

<b>maxAAAUsers</b>
Maximum number of SSL VPN users that can be logged on concurrently to the VPN virtual server that is represented by this GSLB service. A GSLB service whose user count reaches the maximum is not considered when a GSLB decision is made, until the count drops below the maximum.

<b>siteName</b>
Name of the site to which the service belongs.

<b>svrState</b>
Server state.

<b>svrEffGslbState</b>
Effective state of the gslb svc

<b>gslbthreshold</b>
Indicates if gslb svc has reached threshold

<b>gslbsvcStats</b>
Indicates if gslb svc has stats of the primary or the whole chain

<b>state</b>
Enable or disable the service.

<b>monitorName</b>
Monitor name.

<b>monState</b>
The running state of the monitor on this service.

<b>cip</b>
Indicates if Client IP option is enabled

<b>cipHeader</b>
The client IP header used in the HTTP request.

<b>sitePersistence</b>
Indicates the type of cookie persistence set

<b>sitePrefix</b>
The site prefix string.

<b>cltTimeout</b>
Client timeout in seconds.

<b>svrTimeout</b>
Server timeout in seconds.

<b>totalfailedprobes</b>
The total number of failed probs.

<b>preferredLocation</b>
Prefered location.

<b>maxBandwidth</b>
Maximum bandwidth.

<b>downStateFlush</b>
Flush all active transactions associated with the GSLB service when its state transitions from UP to DOWN. Do not enable this option for services that must complete their transactions. Applicable if connection proxy based site persistence is used.

<b>cnameEntry</b>
Canonical name of the GSLB service. Used in CNAME-based GSLB.

<b>viewName</b>
Name of the DNS view of the service. A DNS view is used in global server load balancing (GSLB) to return a predetermined IP address to a specific group of clients, which are identified by using a DNS policy.

<b>viewIP</b>
IP address to be used for the given view

<b>weight</b>
The Weight of monitor

<b>monThreshold</b>
Monitoring threshold value for the GSLB service. If the sum of the weights of the monitors that are bound to this GSLB service and are in the UP state is not equal to or greater than this threshold value, the service is marked as DOWN.

<b>failedprobes</b>
Number of the current failed monitoring probes.

<b>monStatCode</b>
The code indicating the monitor response.

<b>monStatParam1</b>
First parameter for use with message code.

<b>monStatParam2</b>
Second parameter for use with message code.

<b>monStatParam3</b>
Third parameter for use with message code.

<b>responseTime</b>
Response time of this monitor.

<b>hashId</b>
Unique hash identifier for the GSLB service, used by hash based load balancing methods.

<b>comment</b>
Any comments that you might want to associate with the GSLB service.

<b>stateflag</b>
stateflag

<b>healthMonitor</b>
Monitor the health of the GSLB service.

<b>appflowLog</b>
Enable logging appflow flow information

<b>svccfgFlags</b>
Contains the information about config info like internal/configured service

<b>monitorTotalProbes</b>
Total number of probes sent to monitor this service.

<b>monitorTotalFailedProbes</b>
Total number of failed probes

<b>monitorCurrentFailedProbes</b>
Total number of currently failed probes

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>threshold</b>

<b>ClMonOwner</b>
Tells the mon owner of the gslb service.

<b>ClMonView</b>
Tells the view id of the monitoring owner.

<b>devno</b>

<b>count</b>



##Example

show gslb service sj_svc 

##stat gslb service

Displays the statistical data collected for a global server load balancing (GSLB) service.


##Synopsys

stat gslb service [&lt;serviceName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>serviceName</b>
Name of the GSLB service.

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

<b>IP address (IP)</b>
The IP address on which the service is running.

<b>Port (port)</b>
The port on which the service is running.

<b>Service type (Type)</b>
The service type of this service.Possible values are ADNS, DNS, MYSQL, RTSP, SSL_DIAMETER, ADNS_TCP, DNS_TCP, NNTP, SIP_UDP, SSL_TCP, ANY, FTP, RADIUS, SNMP, TCP, DHCPRA, HTTP, RDP, SSL, TFTP, DIAMETER, MSSQL, RPCSVR, SSL_BRIDGE, UDP

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>Request bytes (Reqb)</b>
Total number of request bytes received on this service or virtual server.

<b>Response bytes (Rspb)</b>
Number of response bytes received by this service or virtual server.

<b>Current load on the service (Load)</b>
Load on the service that is calculated from the bound load based monitor.

<b>Requests (Req)</b>
Total number of requests received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Responses (Rsp)</b>
Number of responses received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Current client connections (ClntConn)</b>
Number of current client connections.

<b>Current server connections (SvrConn)</b>
Number of current connections to the actual servers behind the virtual server.

<b>Service hits (Hits)</b>
Number of times that the service has been provided.

<b>Current Server Est connections (SvrEstConn)</b>
Number of server connections in ESTABLISHED state.



##Related Commands

<ul><li><a href="../../../-gslb/-gslb">stat gslb site</a></li><li><a href="../../../tat-gslb-vs/tat-gslb-vs">stat gslb vserver</a></li><li><a href="../../../at-gslb-d/at-gslb-d">stat gslb domain</a></li></ul>



##rename gslb service

Renames a global server load balancing (GSLB) service.


##Synopsys

rename gslb service &lt;serviceName>@ &lt;newName>@


##Arguments

<b>serviceName</b>
Existing name of the GSLB service.

<b>newName</b>
New name for the GSLB service.



##Example

rename gslb service gsl_svc gslb_svc_new

