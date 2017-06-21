#lsn dslite

The following operations can be performed on "lsn dslite":


##stat lsn dslite

Display Large Scale NAT DS-Lite statistics.


##Synopsys

stat lsn dslite [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>DS-Lite Received Packets (DSLiteRxPkts)</b>
Total number of LSN DS-Lite rx pkts.

<b>DS-Lite Received Bytes (DSLiteRxBytes)</b>
Total number of LSN DS-Lite rx bytes.

<b>DS-Lite Transmitted Packets (DSLiteTxPkts)</b>
Total number of LSN DS-Lite tx pkts.

<b>DS-Lite Transmitted Bytes (DSLiteTxBytes)</b>
Total number of LSN DS-Lite tx bytes.

<b>DS-Lite TCP Received Packets (DSLiteTcpRxPkts)</b>
Number of LSN DS-Lite TCP Received packets.

<b>DS-Lite TCP Received Bytes (DSLiteTcpRxBytes)</b>
Number of LSN DS-Lite TCP Received bytes.

<b>DS-Lite TCP Transmitted Packets (DSLiteTcpTxPkts)</b>
Number of LSN DS-Lite TCP Transmitted packets.

<b>DS-Lite TCP Transmitted Bytes (DSLiteTcpTxBytes)</b>
Number of LSN DS-Lite TCP Transmitted bytes.

<b>DS-Lite TCP Dropped Packets (DSLiteTcpDrpPkts)</b>
Number of LSN DS-Lite TCP Dropped packets.

<b>DS-Lite TCP Current Sessions (DSLiteTcpSess)</b>
Number of LSN DS-Lite TCP Current Sessions.

<b>DS-Lite UDP Received Packets (DSLiteUdpRxPkts)</b>
Number of LSN DS-Lite UDP Received packets.

<b>DS-Lite UDP Received Bytes (DSLiteUdpRxBytes)</b>
Number of LSN DS-Lite UDP Received bytes.

<b>DS-Lite UDP Transmitted Packets (DSLiteUdpTxPkts)</b>
Number of LSN DS-Lite UDP Transmitted packets.

<b>DS-Lite UDP Transmitted Bytes (DSLiteUdpTxBytes)</b>
Number of LSN DS-Lite UDP Transmitted bytes.

<b>DS-Lite UDP Dropped Packets (DSLiteUdpDrpPkts)</b>
Number of LSN DS-Lite UDP Dropped packets.

<b>DS-Lite UDP Current Sessions (DSLiteUdpSess)</b>
Number of LSN DS-Lite UDP Current Sessions.

<b>DS-Lite ICMP Received Packets (DSLiteIcmpRxPkts)</b>
Number of LSN DS-Lite ICMP Received packets.

<b>DS-Lite ICMP Received Bytes (DSLiteIcmpRxBytes)</b>
Number of LSN DS-Lite ICMP Received bytes.

<b>DS-Lite ICMP Transmitted Packets (DSLiteIcmpTxPkts)</b>
Number of LSN DS-Lite ICMP Transmitted packets.

<b>DS-Lite ICMP Transmitted Bytes (DSLiteIcmpTxBytes)</b>
Number of LSN DS-Lite ICMP Transmitted bytes.

<b>DS-Lite ICMP Dropped Packets (DSLiteIcmpDrpPkts)</b>
Number of LSN DS-Lite ICMP Dropped packets.

<b>DS-Lite ICMP Current Sessions (DSLiteIcmpSess)</b>
Number of LSN DS-Lite ICMP Current Sessions.

<b>DS-Lite Sessions (DSLiteSession)</b>
Current number of LSN DS-Lite sessions.

<b>DS-Lite Subscribers (DSLiteSubscr)</b>
Current number of LSN DS-Lite subscribers.



##Related Commands

<ul><li><a href="../../..//">stat lsn</a></li><li><a href="../../../lsn-/lsn-">stat lsn group</a></li></ul>



