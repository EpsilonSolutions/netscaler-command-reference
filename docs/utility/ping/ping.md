#ping

The following operations can be performed on "ping":


##ping

Invokes the UNIX ping command. The hostName parameter must be used if the name is in the /etc/hosts file directory or is otherwise known in DNS.


##Synopsys

ping [-c &lt;count>] [-i &lt;interval>] [-I &lt;interface>] [-n]	[-p &lt;pattern>] [-q] [-s &lt;size>] [-S &lt;src_addr>] [-T &lt;td>] [-t &lt;timeout>] &lt;hostname>


##Arguments

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

<b>n</b>
Numeric output only. No name resolution.

<b>p</b>
Pattern to fill in packets.  Can be up to 16 bytes, useful for diagnosing data-dependent problems.

<b>q</b>
Quiet output. Only the summary is printed.

<b>s</b>
Data size, in bytes. The default value is 56.
Minimum value: 0
Maximum value: 65507

<b>S</b>
Source IP address to be used in the outgoing query packets. If the IP addrESS does not belongs to this appliance, an error is returned and nothing is sent.

<b>T</b>
Traffic Domain Id
Minimum value: 1
Maximum value: 4094

<b>t</b>
Time-out, in seconds, before ping exits.
Minimum value: 1
Maximum value: 3600

<b>hostName</b>
Address of host to ping.



##Example

ping -p ff -c 4 10.102.4.107

