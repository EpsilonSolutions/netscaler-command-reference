#ns timeout

The following operations can be performed on "ns timeout":


[set](#set-ns-timeout) | [unset](#unset-ns-timeout) | [show](#show-ns-timeout)

##set ns timeout

Sets timeout values for various aspects of the NetScaler appliance.Caution: Modifying these values can affect system performance.


##Synopsys

set ns timeout [-zombie &lt;positive_integer>] [-httpClient &lt;positive_integer>] [-httpServer &lt;positive_integer>] [-tcpClient &lt;positive_integer>] [-tcpServer &lt;positive_integer>] [-anyClient &lt;positive_integer>] [-anyServer &lt;positive_integer>] [-halfclose &lt;positive_integer>] [-nontcpZombie &lt;positive_integer>] [-ReducedFinTimeOut &lt;positive_integer>] [-ReducedRstTimeOut &lt;positive_integer>] [-NewConnIdleTimeOut &lt;positive_integer>]


##Arguments

<b>zombie</b>
Interval, in seconds, at which the NetScaler zombie cleanup process must run. This process cleans up inactive TCP connections.
Default value: 120
Minimum value: 1
Maximum value: 600

<b>client</b>
Client idle timeout (in seconds).  If zero, the service-type default value is taken when service is created.
Maximum value: 18000

<b>server</b>
Server idle timeout (in seconds).  If zero, the service-type default is taken when service is created.
Maximum value: 18000

<b>httpClient</b>
Global idle timeout, in seconds, for client connections of HTTP service type. This value is over ridden by the client timeout that is configured on individual entities.
Maximum value: 18000

<b>httpServer</b>
Global idle timeout, in seconds, for server connections of HTTP service type. This value is over ridden by the server timeout that is configured on individual entities.
Maximum value: 18000

<b>tcpClient</b>
Global idle timeout, in seconds, for non-HTTP client connections of TCP service type. This value is over ridden by the client timeout that is configured on individual entities.
Maximum value: 18000

<b>tcpServer</b>
Global idle timeout, in seconds, for non-HTTP server connections of TCP service type. This value is over ridden by the server timeout that is configured on entities.
Maximum value: 18000

<b>anyClient</b>
Global idle timeout, in seconds, for non-TCP client connections. This value is over ridden by the client timeout that is configured on individual entities.
Maximum value: 31536000

<b>anyServer</b>
Global idle timeout, in seconds, for non TCP server connections. This value is over ridden by the server timeout that is configured on individual entities.
Maximum value: 31536000

<b>halfclose</b>
Idle timeout, in seconds, for connections that are in TCP half-closed state.
Default value: 10
Minimum value: 1
Maximum value: 600

<b>nontcpZombie</b>
Interval at which the zombie clean-up process for non-TCP connections should run. Inactive IP NAT connections will be cleaned up.
Default value: 60
Minimum value: 1
Maximum value: 600

<b>ReducedFinTimeOut</b>
Alternative idle timeout for new TCP NATPCB connections.
Default value: 30
Minimum value: 1
Maximum value: 300

<b>ReducedRstTimeOut</b>
Timer interval(in seconds) for NATPCB for tcp flow
Default value: 30
Minimum value: 1
Maximum value: 300

<b>NewConnIdleTimeOut</b>
Timer interval(in seconds) for new NATPCB for tcp connections.
Default value: 4
Minimum value: 1
Maximum value: 120



##Example

set ns timeout -zombie 200

##unset ns timeout

Use this command to remove ns timeout settings.Refer to the set ns timeout command for meanings of the arguments.


##Synopsys

unset ns timeout [-zombie] [-httpClient] [-httpServer] [-tcpClient] [-tcpServer] [-anyClient] [-anyServer] [-halfclose] [-nontcpZombie] [-ReducedFinTimeOut] [-ReducedRstTimeOut] [-NewConnIdleTimeOut]


##show ns timeout

Displays the timeouts configured for various NetScaler entities.Note: The timeouts having default values are not displayed.


##Synopsys

show ns timeout


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>zombie</b>
Timer interval(in seconds) for zombie process that cleanup inactive TCP connections
Minimum value: 1
Maximum value: 600
Default value: 120

<b>client</b>
Client idle timeout (in seconds).  If zero, the service-type default value is taken when service is created.

<b>server</b>
Server idle timeout (in seconds).  If zero, the service-type default is taken when service is created.

<b>httpClient</b>
HTTP client idle timeout (in seconds)
Minimum value: 0
Maximum value: 18000

<b>httpServer</b>
HTTP server idle timeout (in seconds)
Minimum value: 0
Maximum value: 18000

<b>tcpClient</b>
TCP client idle timeout (in seconds)
Minimum value: 0
Maximum value: 18000

<b>tcpServer</b>
TCP server idle timeout (in seconds)
Minimum value: 0
Maximum value: 18000

<b>anyClient</b>
ANY client idle timeout (in seconds)
Minimum value: 0
Maximum value: 31536000

<b>anyServer</b>
ANY server idle timeout (in seconds)
Minimum value: 0
Maximum value: 31536000

<b>halfclose</b>
Half-closed connection timeout (in seconds)
Minimum value: 1
Maximum value: 600
Default value: 10

<b>nontcpZombie</b>
Timer interval(in seconds) for zombie process that cleanup inactive IP NAT connections
Minimum value: 1
Maximum value: 600
Default value: 60

<b>ReducedFinTimeOut</b>
Timer interval(in seconds) for NATPCB for tcp flow

<b>ReducedRstTimeOut</b>
Timer interval(in seconds) for NATPCB for tcp flow

<b>NewConnIdleTimeOut</b>
Timer interval(in seconds) for new NATPCB for tcp connections



##Example

show ns timeout

