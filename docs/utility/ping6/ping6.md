#ping6

The following operations can be performed on "ping6":


##ping6

Invokes the UNIX ping6 command. The hostName parameter must be used if the name is in the /etc/hosts file directory or is otherwise known in DNS.


##Synopsys

ping6 [-b &lt;bufsiz>] [-c &lt;count>] [-i &lt;interval>] [-I &lt;interface>]  [-m] [-n]	[-p &lt;pattern>] [-q] [-S sourceaddr] [-V  &lt;vlanid>] [-T &lt;td>] [-s &lt;size>] Hostname 


##Arguments

<b>b</b>
Set socket buffer size. If used, should be used with roughly +100 then the datalen (-s option). The default value is 8192.
Minimum value: 132
Maximum value: 131071

<b>c</b>
Number of packets to send. The default value is infinite.
Minimum value: 1
Maximum value: 65535

<b>i</b>
Waiting time, in seconds. The default value is 1 second.
Minimum value: 0
Maximum value: 65535

<b>I</b>
Network interface on which to ping, if you have multiple interfaces.

<b>m</b>
By default, ping6 asks the kernel to fragment packets to fit into the minimum IPv6 MTU.The -m option will suppress the behavior for unicast packets.

<b>n</b>
Numeric output only. No name resolution.

<b>p</b>
Pattern to fill in packets. Can be up to 16 bytes, useful for diagnosing data-dependent problems.

<b>q</b>
Quiet output. Only summary is printed.

<b>s</b>
Data size, in bytes. The default value is 32.
Minimum value: 0
Maximum value: 65527

<b>V</b>
VLAN ID for link local address.
Minimum value: 1
Maximum value: 4094

<b>S</b>
Source IP address to be used in the outgoing query packets.

<b>T</b>
Traffic Domain Id
Minimum value: 1
Maximum value: 4094

<b>hostName</b>
Address of host to ping.



##Example

ping6 -p ff -I 1/1 -c 4 2002::1

