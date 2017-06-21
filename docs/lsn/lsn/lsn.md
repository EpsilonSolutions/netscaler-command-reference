#lsn

The following operations can be performed on "lsn":


##stat lsn

Display Large Scale NAT statistics.


##Synopsys

stat lsn [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>LSN TCP Received Packets (TcpRxPkts)</b>
Number of LSN TCP Received packets.

<b>LSN TCP Received Bytes (TcpRxBytes)</b>
Number of LSN TCP Received bytes.

<b>LSN TCP Transmitted Packets (TcpTxPkts)</b>
Number of LSN TCP Transmitted packets.

<b>LSN TCP Transmitted Bytes (TcpTxBytes)</b>
Number of LSN TCP Transmitted bytes.

<b>LSN TCP Dropped Packets (TcpDrpPkts)</b>
Number of LSN TCP Dropped packets.

<b>LSN TCP Current Sessions (TcpSess)</b>
Number of LSN TCP Current Sessions.

<b>LSN UDP Received Packets (UdpRxPkts)</b>
Number of LSN UDP Received packets.

<b>LSN UDP Received Bytes (UdpRxBytes)</b>
Number of LSN UDP Received bytes.

<b>LSN UDP Transmitted Packets (UdpTxPkts)</b>
Number of LSN UDP Transmitted packets.

<b>LSN UDP Transmitted Bytes (UdpTxBytes)</b>
Number of LSN UDP Transmitted bytes.

<b>LSN UDP Dropped Packets (UdpDrpPkts)</b>
Number of LSN UDP Dropped packets.

<b>LSN UDP Current Sessions (UdpSess)</b>
Number of LSN UDP Current Sessions.

<b>LSN ICMP Received Packets (IcmpRxPkts)</b>
Number of LSN ICMP Received packets.

<b>LSN ICMP Received Bytes (IcmpRxBytes)</b>
Number of LSN ICMP Received bytes.

<b>LSN ICMP Transmitted Packets (IcmpTxPkts)</b>
Number of LSN ICMP Transmitted packets.

<b>LSN ICMP Transmitted Bytes (IcmpTxBytes)</b>
Number of LSN ICMP Transmitted bytes.

<b>LSN ICMP Dropped Packets (IcmpDrpPkts)</b>
Number of LSN ICMP Dropped packets.

<b>LSN ICMP Current Sessions (IcmpSess)</b>
Number of LSN ICMP Current Sessions.

<b>LSN sessions (Session)</b>
Current number of LSN sessions.

<b>LSN Subscribers (Subscr)</b>
Current number of LSN subscribers.



##Related Commands

<ul><li><a href="../../../lsn-/lsn-">stat lsn group</a></li><li><a href="../../../-lsn-d/-lsn-d">stat lsn dslite</a></li></ul>



