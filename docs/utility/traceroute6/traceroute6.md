#traceroute6

The following operations can be performed on "traceroute6":


##traceroute6

Invokes the UNIX traceroute6 command. Traceroute6 attempts to track the route that the packets follow to reach the destination host.


##Synopsys

traceroute6 [-n] [I] [-r] [-v] [-m &lt;hoplimit>]	[-p &lt;port>] [-q &lt;probes>] [-s &lt;src_addr>] [-T &lt;td>]	[-w &lt;waittime>] &lt;target> [&lt;packetlen>]


##Arguments

<b>n</b>
Print hop addresses numerically rather than symbolically and numerically.

<b>I</b>
Use ICMP ECHO for probes.

<b>r</b>
Bypass normal routing tables and send directly to a host on an attached network. If the host is not on a directly attached network, an error is returned.

<b>v</b>
Verbose output. List received ICMP packets other than TIME_EXCEEDED and UNREACHABLE.

<b>m</b>
Maximum hop value for outgoing probe packets.
Default value: 64
Minimum value: 1
Maximum value: 255

<b>p</b>
Base port number used in probes.
Default value: 33434
Minimum value: 1
Maximum value: 65535

<b>q</b>
Number of probes per hop.
Default value: 3
Minimum value: 1
Maximum value: 65535

<b>s</b>
Source IP address to use in the outgoing query packets. If the IP address does not belong to this appliance,  an error is returned and nothing is sent.

<b>T</b>
Traffic Domain Id
Minimum value: 1
Maximum value: 4094

<b>w</b>
Time (in seconds) to wait for a response to a query.
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



##Example

traceroute6 2002::7

