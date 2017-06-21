#server

The following operations can be performed on "server":


[add](#add-server) | [rm](#rm-server) | [set](#set-server) | [unset](#unset-server) | [enable](#enable-server) | [disable](#disable-server) | [show](#show-server) | [rename](#rename-server)

##add server

Creates a server entry on the NetScaler appliance. The NetScaler appliance supports two types of servers: IP address based servers and domain based servers.


##Synopsys

add server &lt;name>@ (&lt;IPAddress>@ | (&lt;domain>@  [-domainResolveRetry &lt;integer>]  [-IPv6Address ( YES | NO )]) | (-translationIp &lt;ip_addr>  -translationMask &lt;netmask>)) [-state ( ENABLED | DISABLED )] [-comment &lt;string>] [-td &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the server. 
Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
Can be changed after the name is created.

<b>IPAddress</b>
IPv4 or IPv6 address of the server. If you create an IP address based server, you can specify the name of the server, instead of its IP address, when creating a service. Note: If you do not create a server entry, the server IP address that you enter when you create a service becomes the name of the server.

<b>domain</b>
Domain name of the server. For a domain based configuration, you must create the server first.

<b>translationIp</b>
IP address used to transform the server's DNS-resolved IP address.

<b>translationMask</b>
The netmask of the translation ip

<b>domainResolveRetry</b>
Time, in seconds, for which the NetScaler appliance must wait, after DNS resolution fails, before sending the next DNS query to resolve the domain name.
Default value: 5
Minimum value: 5
Maximum value: 20939

<b>state</b>
Initial state of the server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>IPv6Address</b>
Support IPv6 addressing mode. If you configure a server with the IPv6 addressing mode, you cannot use the server in the IPv4 addressing mode.
Possible values: YES, NO
Default value: NO

<b>comment</b>
Any information about the server.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

add server web_serv 10.102.27.150	To add multiple servers you can use the following command:	add server serv[1-3] 10.102.27.[151-153]	The above command adds three servers: serv1 with IP 10.102.27.151, serv2 with IP 10.102.27.152 and serv3 with IP 10.102.27.153.

##rm server

Removes a server entry from the NetScaler appliance.


##Synopsys

rm server &lt;name>@ ...


##Arguments

<b>name</b>
Name of the server entry to remove.



##Example

rm server web_svr	To remove the servers named serv1, serv2 and serv3 at once you can use the following command:	rm server serv[1-3]

##set server

Modifies the specified parameters of a server entry.


##Synopsys

set server &lt;name>@ [-IPAddress &lt;ip_addr|ipv6_addr|*>@ | -domainResolveRetry &lt;integer> | -translationIp &lt;ip_addr> | -translationMask &lt;netmask> | -domainResolveNow] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the server whose parameters you are configuring.

<b>IPAddress</b>
Name of the server whose parameters you are configuring.

<b>domainResolveRetry</b>
Time, in seconds, for which the NetScaler appliance must wait, after DNS resolution fails, before sending the next DNS query to resolve the domain name.
Default value: 5
Minimum value: 5
Maximum value: 20939

<b>translationIp</b>
IP address used to transform the server's DNS-resolved IP address.

<b>translationMask</b>
The netmask of the translation ip

<b>domainResolveNow</b>
Immediately send a DNS query to resolve the server's domain name.

<b>comment</b>
Any information about the server.



##Example

set server http_svr -IPAddress 10.102.1.112	To set multiple servers IP addresses at once you can use the following command:	setserver serv[1-3] -IPAddress 10.102.27.[1-3]	The above command sets the IP address of serv1 to 10.102.27.1, serv2 to 10.102.27.2 and serv3 to 10.102.27.3.

##unset server

Use this command to remove  server settings.Refer to the set  server command for meanings of the arguments.


##Synopsys

unset server &lt;name>@ -comment


##enable server

Enables all services on the specified server.


##Synopsys

enable server &lt;name>@


##Arguments

<b>name</b>
Name of the server to enable.



##Example

enable server web_serv	To enable all the services configured on servers named serv1, serv2 and serv3 at once, use the following command:	enable server serv[1-3]

##disable server

Disables all services on the server. When a server is disabled, all services on the server are disabled.


##Synopsys

disable server &lt;name>@ [&lt;delay>] [-graceFul ( YES | NO )]


##Arguments

<b>name</b>
Name of the server to disable.

<b>delay</b>
Time, in seconds, after which all the services configured on the server are disabled.

<b>graceFul</b>
Shut down gracefully, without accepting any new connections, and disabling each service when all of its connections are closed.
Possible values: YES, NO
Default value: NO



##Example

disable server web_svr  30	To disable all the services configured on servers named serv1, serv2 and serv3 at once, use the following command:	disable server serv[1-3]

##show server

Displays the parameters of all the server entries on the appliance, or the parameters of the specified server entry.


##Synopsys

show server [&lt;name> | -internal]


##Arguments

<b>name</b>
Name of the server for which to display parameters.

<b>internal</b>
Display names of the servers that have been created for internal use.



##Outputs

<b>IPAddress</b>
The IP Address of server.

<b>state</b>
The State of the server.

<b>domain</b>
The domain name of the server.

<b>domainResolveRetry</b>
Time, in seconds, for which the NetScaler appliance must wait, after DNS resolution fails, before sending the next DNS query to resolve the domain name.

<b>serviceName</b>
The services attatched to the server.

<b>serviceGroupName</b>
servicegroups bind to this server

<b>translationIp</b>
IP address used to transform the server's DNS-resolved IP address.

<b>translationMask</b>
The netmask of the translation ip

<b>comment</b>
Any information about the server.

<b>stateflag</b>
stateflag

<b>serviceType</b>
service type of the service.

<b>serviceIPAddress</b>
The IP address of the bound service

<b>serviceIPstr</b>
This field has been intorduced to show the dbs services ip

<b>port</b>
port of the service.

<b>svrState</b>
The state of the bound service

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>IPv6Address</b>
Support IPv6 addressing mode. If you configure a server with the IPv6 addressing mode, you cannot use the server in the IPv4 addressing mode.

<b>svrcfgFlags</b>
service flags to denote its a db enabled.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>autoScale</b>
Auto scale option for a servicegroup

<b>CustomServerID</b>
A positive integer to identify the service. Used when the persistency type is set to Custom Server ID.

<b>monThreshold</b>
Minimum sum of weights of the monitors that are bound to this service. Used to determine whether to mark a service as UP or DOWN.

<b>maxClient</b>
Maximum number of simultaneous open connections for the service group.

<b>maxReq</b>
Maximum number of requests that can be sent on a persistent connection to the service group. 
           Note: Connection requests beyond this value are rejected.

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, allocated for all the services in the service group.

<b>usip</b>
Use the client's IP address as the source IP address when initiating a connection to the server. When creating a service, if you do not set this parameter, the service inherits the global Use Source IP setting (available in the enable ns mode and disable ns mode CLI commands, or in the System > Settings > Configure modes > Configure Modes dialog box). However, you can override this setting after you create the service.

<b>CKA</b>
Enable client keep-alive for the service group.

<b>TCPB</b>
Enable TCP buffering for the service group.

<b>CMP</b>
Enable compression for the specified service.

<b>cltTimeout</b>
Time, in seconds, after which to terminate an idle client connection.

<b>svrTimeout</b>
Time, in seconds, after which to terminate an idle server connection.

<b>cipHeader</b>
Name of the HTTP header whose value must be set to the IP address of the client. Used with the Client IP parameter. If client IP insertion is enabled, and the client IP header is not specified, the value of Client IP Header parameter or the value set by the set ns config command is used as client's IP header name.

<b>cip</b>
Before forwarding a request to the service, insert an HTTP header with the client's IPv4 or IPv6 address as its value. Used if the server needs the client's IP address for security, accounting, or other purposes, and setting the Use Source IP parameter is not a viable option.

<b>cacheable</b>
Use the transparent cache redirection virtual server to forward the request to the cache server.

<b>sc</b>
State of the SureConnect feature for the service group.

<b>sp</b>
Enable surge protection for the service group.

<b>downStateFlush</b>
Perform delayed clean-up of connections to all services in the service group.

<b>appflowLog</b>
Enable logging of AppFlow information for the specified service group.

<b>boundTD</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>devno</b>

<b>count</b>



##Example

&gt; show server web_svr1	Name:             web_svr1      State:ENABLED	IPAddress:   10.102.27.154&gt; show server web_svr1	Name:             web_svr2      State:ENABLED	Domain: www.abc.com      Resolve Retry: 30 Secs	Translation IP:   10.102.27.153  Translation Mask:   255.255.255.0

##rename server

Renames a server.


##Synopsys

rename server &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the server.

<b>newName</b>
New name for the server. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

rename server s1 s1-new

