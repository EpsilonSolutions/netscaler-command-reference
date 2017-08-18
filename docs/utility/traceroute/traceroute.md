#traceroute

The following operations can be performed on "traceroute":


##traceroute

Invokes the UNIX traceroute command. This command attempts to track the route that the packets follow to reach the destination host.


##Synopsys

traceroute [-S] [-n] [-r] [-v] [-M &lt;min_ttl] [-m &lt;max_ttl>]	[-P &lt;protocol>][-p &lt;portno>] [-q &lt;nqueries>] [-s &lt;src_addr>] [-T &lt;td>] [-t &lt;tos>]	[-w &lt;wait>] &lt;host> [&lt;packetlen>]


##Arguments

<b>S</b>
Print a summary of how many probes were not answered for each hop.

<b>n</b>
Print hop addresses numerically instead of symbolically and numerically.

<b>r</b>
Bypass normal routing tables and send directly to a host on an attached network. If the host is not on a directly attached network, an error is returned.

<b>v</b>
Verbose output. List received ICMP packets other than TIME_EXCEEDED and UNREACHABLE.

<b>M</b>
Minimum TTL value used in outgoing probe packets.
Default value: 1
Minimum value: 1
Maximum value: 255

<b>m</b>
Maximum TTL value used in outgoing probe packets. For Nitro API, default value is taken as 10.
Default value: 64
Minimum value: 1
Maximum value: 255

<b>P</b>
Send packets of specified IP protocol. The currently supported protocols are UDP and ICMP.

<b>p</b>
Base port number used in probes.
Default value: 33434
Minimum value: 1
Maximum value: 65535

<b>q</b>
Number of queries per hop. For Nitro API, defalut value is taken as 1.
Default value: 3
Minimum value: 1
Maximum value: 65535

<b>s</b>
Source IP address to use in the outgoing query packets. If the IP address does not belong to this appliance,  an error is returned and nothing is sent.

<b>T</b>
Traffic Domain Id
Minimum value: 1
Maximum value: 4094

<b>t</b>
Type-of-service in query packets.
Maximum value: 255

<b>w</b>
Time (in seconds) to wait for a response to a query. For Nitro API, defalut value is set to 3.
Default value: 5
Minimum value: 2
Maximum value: 86399

<b>host</b>
Destination host IP address or name.

<b>packetlen</b>
Length (in bytes) of the query packets.
Default value: 44
Minimum value: 44
Maximum value: 32768



##Outputs

<b>response</b>



##Example

traceroute 10.102.4.107

