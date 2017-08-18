#user vserver

The following operations can be performed on "user vserver":


[add](#add-user-vserver) | [rm](#rm-user-vserver) | [set](#set-user-vserver) | [unset](#unset-user-vserver) | [show](#show-user-vserver) | [stat](#stat-user-vserver)

##add user vserver

Creates an user defined load balancing virtual server.Example: add user protocol MQTT -transporttype TCP -extension mqtt_logic


##Synopsys

add user vserver &lt;name>@ &lt;userProtocol> &lt;IPAddress>@ &lt;port> -defaultLB &lt;string> [-params &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').

<b>userProtocol</b>
User protocol uesd by the service.

<b>IPAddress</b>
IPv4 or IPv6 address to assign to the virtual server.

<b>port</b>
Port number for the virtual server.

<b>defaultLB</b>
Name of the default Load Balancing virtual server used for load balancing of services. The protocol type of default Load Balancing virtual server should be a user type.

<b>params</b>
Any comments associated with the protocol.

<b>comment</b>
Any comments that you might want to associate with the virtual server.



##rm user vserver

Removes an user defined virtual server from the NetScaler appliance.


##Synopsys

rm user vserver &lt;name>


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').



##set user vserver

Modifies the specified parameters of an user defined virtual server.


##Synopsys

set user vserver &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr|*>@] [-defaultLB &lt;string>] [-params &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').

<b>IPAddress</b>
IPv4 or IPv6 address to assign to the virtual server.

<b>defaultLB</b>
Name of the default Load Balancing virtual server used for load balancing of services. The protocol type of default Load Balancing virtual server should be a user type.

<b>params</b>
Any comments associated with the protocol.

<b>comment</b>
Any comments that you might want to associate with the virtual server.



##unset user vserver

Use this command to remove user vserver settings.Refer to the set user vserver command for meanings of the arguments.


##Synopsys

unset user vserver &lt;name> [-params] [-comment]


##show user vserver

Displays information about the user defined virtual server.


##Synopsys

show user vserver [&lt;name>]


##Arguments

<b>name</b>
Name for the virtual server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my vserver" or 'my vserver').



##Outputs

<b>userProtocol</b>
User protocol uesd by the service.

<b>IPAddress</b>
IPv4 or IPv6 address to assign to the virtual server.

<b>port</b>
Port number for the virtual server.

<b>defaultLB</b>
Name of the default Load Balancing virtual server used for load balancing of services. The protocol type of default Load Balancing virtual server should be a user type.

<b>params</b>
Any comments associated with the protocol.

<b>comment</b>
Any comments that you might want to associate with the virtual server.

<b>stateflag</b>

<b>state</b>
Current user vserver state.

<b>value</b>
SSL status.

<b>stateChangeTimeSec</b>
Time when last state change happened. Seconds part.

<b>stateChangeTimemSec</b>
Time at which last state change happened. Milliseconds part.

<b>ticksSinceLastStateChange</b>
Time in 10 millisecond ticks since the last state change.

<b>devno</b>

<b>count</b>



##stat user vserver

Displays the statistical data collected for an user defined load balancing virtual server.


##Synopsys

stat user vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )] [-sortBy Hits  [&lt;sortOrder>]]


##Arguments

<b>name</b>
Name of the user defined virtual server. If no name is provided, statistical data of all configured user defined virtual servers is displayed.

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

<b>sortBy</b>
use this argument to sort by specific key
Possible values: Hits

<b>sortOrder</b>
use this argument to specify sort order
Possible values: ascending, descending
Default value: SORT_DESCENDING



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

<b>Vserver IP address (vsvrIP)</b>
IP address of the vserver

<b>Port (port)</b>
The port on which the service is running.

<b>Vserver protocol name (Protocol)</b>
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

<b>Invalid Request/Response (IvldReqRsp)</b>
Number invalid requests/responses on this vserver

<b>Invalid Request/Response Dropped (IvldReqRspDrp)</b>
Number invalid requests/responses dropped on this vserver

<b>Current Server Est connections (SvrEstConn)</b>
Number of server connections in ESTABLISHED state.



