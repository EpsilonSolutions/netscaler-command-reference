#lsn nat64

The following operations can be performed on "lsn nat64":


##stat lsn nat64

Display Large Scale NAT64 statistics.


##Synopsys

stat lsn nat64 [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>LSN NAT64 Sessions (NAT64Session)</b>
Current number of LSN NAT64 sessions.

<b>LSN NAT64 Subscribers (NAT64Subscr)</b>
Current number of LSN NAT64 subscribers.

<b>LSN NAT64 Received Packets (NAT64RxPkts)</b>
Total number of LSN NAT64 rx pkts.

<b>LSN NAT64 Received Bytes (NAT64RxBytes)</b>
Total number of LSN NAT64 rx bytes.

<b>LSN NAT64 Transmitted Packets (NAT64TxPkts)</b>
Total number of LSN NAT64 tx pkts.

<b>LSN NAT64 Transmitted Bytes (NAT64TxBytes)</b>
Total number of LSN NAT64 tx bytes.

<b>LSN NAT64 TCP Current Sessions (NAT64TCPSess)</b>
Number of LSN NAT64 TCP Current Sessions.

<b>LSN NAT64 TCP Received Packets (NAT64TcpRxPkts)</b>
Number of LSN NAT64 TCP Received packets.

<b>LSN NAT64 TCP Received Bytes (NAT64TCPRxBytes)</b>
Number of LSN NAT64 TCP Received bytes.

<b>LSN NAT64 TCP Transmitted Packets (NAT64TcpTxPkts)</b>
Number of LSN NAT64 TCP Transmitted packets.

<b>LSN NAT64 TCP Transmitted Bytes (NAT64TCPTxBytes)</b>
Number of LSN NAT64 TCP Transmitted bytes.

<b>LSN NAT64 TCP Dropped Packets (NAT64TCPDrpPkts)</b>
Number of LSN NAT64 TCP Dropped packets.

<b>LSN NAT64 UDP Current Sessions (NAT64UDPSess)</b>
Number of LSN NAT64 UDP Current Sessions.

<b>LSN NAT64 UDP Received Packets (NAT64UDPRxPkts)</b>
Number of LSN NAT64 UDP Received packets.

<b>LSN NAT64 UDP Received Bytes (NAT64UDPRxBytes)</b>
Number of LSN NAT64 UDP Received bytes.

<b>LSN NAT64 UDP Transmitted Packets (NAT64UDPTxPkts)</b>
Number of LSN NAT64 UDP Transmitted packets.

<b>LSN NAT64 UDP Transmitted Bytes (NAT64UDPTxBytes)</b>
Number of LSN NAT64 UDP Transmitted bytes.

<b>LSN NAT64 UDP Dropped Packets (NAT64UDPDrpPkts)</b>
Number of LSN NAT64 UDP Dropped packets.

<b>LSN NAT64 ICMP Current Sessions (NAT64ICMPSess)</b>
Number of LSN NAT64 ICMP Current Sessions.

<b>LSN NAT64 ICMP Received Packets (NAT64ICMPRxPkts)</b>
Number of LSN NAT64 ICMP Received packets.

<b>LSN NAT64 ICMP Received Bytes (NAT64ICMPRxBytes)</b>
Number of LSN NAT64 ICMP Received bytes.

<b>LSN NAT64 ICMP Transmitted Packets (NAT64ICMPTxPkts)</b>
Number of LSN NAT64 ICMP Transmitted packets.

<b>LSN NAT64 ICMP Transmitted Bytes (NAT64ICMPTxBytes)</b>
Number of LSN NAT64 ICMP Transmitted bytes.

<b>LSN NAT64 ICMP Dropped Packets (NAT64ICMPDrpPkts)</b>
Number of LSN NAT64 ICMP Dropped packets.



##Related Commands

<ul><li><a href="../../..//">stat lsn</a></li><li><a href="../../../lsn-/lsn-">stat lsn group</a></li><li><a href="../../../-lsn-d/-lsn-d">stat lsn dslite</a></li></ul>



