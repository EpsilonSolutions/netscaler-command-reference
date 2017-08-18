#protocol icmpv6

The following operations can be performed on "protocol icmpv6":


##stat protocol icmpv6

Displays statistics of the ICMPv6 protocol.


##Synopsys

stat protocol icmpv6 [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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

<b>ICMPv6 packets received (icmpv6RxPkts)</b>
ICMPv6 packets received.

<b>ICMPv6 bytes received (icmpv6RxBytes)</b>
Bytes of ICMPv6 data received.

<b>ICMPv6 packets transmitted (icmpv6TxPkts)</b>
ICMPv6 packets transmitted.

<b>ICMPv6 bytes transmitted (icmpv6TxBytes)</b>
Bytes of ICMPv6 data transmitted.

<b>ICMPv6 NA packets received (icmpv6RxNa)</b>
ICMPv6 neighbor advertisement packets received. These packets are received in response to a neighbor solicitation message sent out by this node, or if the link layer address of a neighbor has changed.

<b>ICMPv6 NS packets received (icmpv6RxNs)</b>
ICMPv6 neighbor solicitation packets received. These packets are received if the link layer address of a neighbor has changed, or in response to a neighbor solicitation message sent out by this node.

<b>ICMPv6 RA packets received (icmpv6RxRa)</b>
ICMPv6 router advertisement packets received. These are received at defined intervals or in response to a router solicitation message.

<b>ICMPv6 RS packets received (icmpv6RxRs)</b>
ICMPv6 router solicitation packets received. These could be sent by a neighboring router to initiate address resolution.

<b>ICMPv6 Echo Request packets received (icmpv6RxEchoReq)</b>
ICMPv6 Ping Echo Request packets received.

<b>ICMPv6 Echo Reply packets received (icmpv6RxEchoReply)</b>
ICMPv6 Ping Echo Reply packets received.

<b>ICMPv6 NA packets transmitted (icmpv6TxNa)</b>
ICMPv6 neighbor advertisement packets transmitted. These packets are sent in response to a neighbor solicitation packet, or if the link layer address of this node has changed.

<b>ICMPv6 NS packets transmitted (icmpv6TxNs)</b>
ICMPv6 neighbor solicitation packets transmitted. These packets are sent to get the link layer addresses of neighboring nodes or to confirm that they are reachable.

<b>ICMPv6 RA packets transmitted (icmpv6TxRa)</b>
ICMPv6 router advertisement packets transmitted. These packets are sent at regular intervals or in response to a router solicitation packet from a neighbor.

<b>ICMPv6 RS packets transmitted (icmpv6TxRs)</b>
ICMPv6 router solicitation packets transmitted. These packets are sent to request neighboring routers to generate router advertisements immediately rather than wait for the next defined time.

<b>ICMPv6 Echo Request packets transmitted (icmpv6TxEchoReq)</b>
ICMPv6 Ping Echo Request packets transmitted.

<b>ICMPv6 Echo Reply packets transmitted (icmpv6TxEchoReply)</b>
ICMP Ping Echo Reply packets transmitted.

<b>ICMPv6 RA error packets (Error in RA packet)</b>
ICMPv6 router advertisement error packets received that contain an error in the header, such as an incorrect source IP address, destination IP address, or packet length.

<b>ICMPv6 NA error packets (Error in NA packet)</b>
ICMPv6 neighbor advertisement error packets received that contain an error in the header, such as an incorrect source IP address, destination IP address, or packet length.

<b>ICMPv6 NS error packets (Error in NS packet)</b>
ICMPv6 neighbor solicitation error packets received that contain an error in the header, such as an incorrect source IP address, destination IP address, or packet length.

<b>ICMPv6 bad checksum (Cksumerr)</b>
Packets received with an ICMPv6 checksum error.

<b>unsupported ICMPv6 packets (icmpv6Unspt)</b>
ICMPv6 packets received that are not supported by the NetScaler.

<b>Rate threshold exceeded packets (icmpv6thsld)</b>
Packets dropped because the default threshold of 100 requests per 10 milliseconds has been exceeded.
This is a configurable value using the set rateControl command.



##Related Commands

<ul><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol tcp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol http</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol ipv6</a></li><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol udp</a></li><li><a href="../../../html#stat-protocol-/html#stat-protocol-">stat protocol mptcp</a></li></ul>



