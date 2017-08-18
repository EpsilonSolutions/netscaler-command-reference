#protocol udp

The following operations can be performed on "protocol udp":


##stat protocol udp

Displays statistics of the UDP protocol.


##Synopsys

stat protocol udp [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>Packets received (UDPPktRx)</b>
Total number of UDP packets received.

<b>Bytes received (UDPbRx)</b>
Total number of UDP data received in bytes.

<b>Packets transmitted (UDPPktTx)</b>
Total number of UDP packets transmitted.

<b>Bytes transmitted (UDPbTx)</b>
Total number of UDP data transmitted in bytes.

<b>Current rate threshold (UDPThs)</b>
Limit for UDP packets handled every 10 milliseconds. Default value, 0, applies no limit.
This is a configurable value using the set rateControl command.

<b>Unknown service (UDPUnSvc)</b>
Stray UDP packets dropped due to no configured listening  service.

<b>Bad UDP checksum (UDPBadCkSum)</b>
Packets received with a UDP checksum error.

<b>Rate threshold exceeded (UDPRtEx)</b>
Number of times the UDP rate threshold is exceeded. If this counter continuously increases, first make sure the UDP packets received are genuine. 
	If they are, increase the current rate threshold. This is a configurable value using the set rateControl command.



##Related Commands

<ul><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol tcp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol http</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol ipv6</a></li><li><a href="../../../.html#stat-protocol-i/.html#stat-protocol-i">stat protocol icmpv6</a></li><li><a href="../../../html#stat-protocol-/html#stat-protocol-">stat protocol mptcp</a></li></ul>



