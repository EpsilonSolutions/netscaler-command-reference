#serviceGroupMember

The following operations can be performed on "serviceGroupMember":


##stat serviceGroupMember

Display statistics of a service group member.


##Synopsys

stat serviceGroupMember &lt;serviceGroupName> (&lt;IP> | &lt;serverName>) &lt;port> [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>serviceGroupName</b>
Displays statistics for the specified service group.Name of the service group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. 
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my servicegroup" or 'my servicegroup').

<b>IP</b>
IP address of the service group. Mutually exclusive with the server name parameter.

<b>serverName</b>
Name of the server. Mutually exclusive with the IP address parameter.

<b>port</b>
Port number of the service group member.

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

<b>Total transactions for server TTLB (totSvrTTLBTransactions)</b>
Total transactions where server TTLB is calculated.

<b>Tolerating TTLB Transactions (toleratingTTLBTransactions)</b>
Tolerable transactions based on APDEX threshold (>T && &lt;4T).

<b>Frustrating TTLB Transactions (frustratingTTLBTransactions)</b>
Frustrating transactions based on APDEX threshold (>4T).



