#ns tcpParam

The following operations can be performed on "ns tcpParam":


[set](#set-ns-tcpparam) | [unset](#unset-ns-tcpparam) | [show](#show-ns-tcpparam)

##set ns tcpParam

Sets the TCP parameters for the NetScaler appliance.


##Synopsys

set ns tcpParam [-WS ( ENABLED | DISABLED )] [-WSVal &lt;positive_integer>] [-SACK ( ENABLED | DISABLED )] [-learnVsvrMSS ( ENABLED | DISABLED )] [-maxBurst &lt;positive_integer>] [-initialCwnd &lt;positive_integer>] [-delayedAck &lt;positive_integer>] [-downStateRST ( ENABLED | DISABLED )] [-nagle ( ENABLED | DISABLED )] [-limitedPersist ( ENABLED | DISABLED )] [-oooQSize &lt;positive_integer>] [-ackOnPush ( ENABLED | DISABLED )] [-maxPktPerMss &lt;integer>] [-pktPerRetx &lt;integer>] [-minRTO &lt;integer>] [-slowStartIncr &lt;integer>] [-maxDynServerProbes &lt;positive_integer>] [-synHoldFastGiveup &lt;positive_integer>] [-maxSynholdPerprobe &lt;positive_integer>] [-maxSynhold &lt;positive_integer>] [-mssLearnInterval &lt;positive_integer>] [-mssLearnDelay &lt;positive_integer>] [-maxTimeWaitConn &lt;positive_integer>] [-maxSynAckRetx &lt;positive_integer>] [-synAttackDetection ( ENABLED | DISABLED )] [-connFlushIfNoMem &lt;connFlushIfNoMem>] [-connFlushThres &lt;positive_integer>] [-mptcpConCloseOnPassiveSF ( ENABLED | DISABLED )] [-mptcpChecksum ( ENABLED | DISABLED )] [-mptcpSFtimeout &lt;secs>] [-mptcpSFReplaceTimeout &lt;secs>] [-mptcpMaxSF &lt;positive_integer>] [-mptcpMaxPendingSF &lt;positive_integer>] [-mptcpPendingJoinThreshold &lt;positive_integer>] [-mptcpRTOsToSwitchSF &lt;positive_integer>] [-mptcpUseBackupOnDSS ( ENABLED | DISABLED )] [-TcpMaxRetries &lt;positive_integer>] [-mptcpImmediateSFCloseOnFIN ( ENABLED | DISABLED )] [-mptcpCloseMptcpSessionOnLastSFClose ( ENABLED | DISABLED )]


##Arguments

<b>WS</b>
Enable or disable window scaling.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>WSVal</b>
Factor used to calculate the new window size.
This argument is needed only when the window scaling is enabled.
Default value: 4
Minimum value: 0
Maximum value: 14

<b>SACK</b>
Enable or disable Selective ACKnowledgement (SACK).
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>learnVsvrMSS</b>
Enable or disable maximum segment size (MSS) learning for virtual servers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxBurst</b>
Maximum number of TCP segments allowed in a burst.
Default value: 6
Minimum value: 1
Maximum value: 255

<b>initialCwnd</b>
Initial maximum upper limit on the number of TCP packets that can be outstanding on the TCP link to the server.
Default value: 4
Minimum value: 1
Maximum value: 44

<b>delayedAck</b>
Timeout for TCP delayed ACK, in milliseconds.
Default value: 100
Minimum value: 10
Maximum value: 300

<b>downStateRST</b>
Flag to switch on RST on down services.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nagle</b>
Enable or disable the Nagle algorithm on TCP connections.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>limitedPersist</b>
Limit the number of persist (zero window) probes.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>oooQSize</b>
Maximum size of out-of-order packets queue. A value of 0 means no limit.
Default value: 64
Minimum value: 0
Maximum value: 65535

<b>ackOnPush</b>
Send immediate positive acknowledgement (ACK) on receipt of TCP packets with PUSH flag.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxPktPerMss</b>
Maximum number of TCP packets allowed per maximum segment size (MSS).
Minimum value: 0
Maximum value: 1460

<b>pktPerRetx</b>
Maximum limit on the number of packets that should be retransmitted on receiving a partial ACK.
Default value: 1
Minimum value: 1
Maximum value: 100

<b>minRTO</b>
Minimum retransmission timeout, in milliseconds, specified in 10-millisecond increments (value must yield a whole number if divided by 10).
Default value: 1000
Minimum value: 10
Maximum value: 64000

<b>slowStartIncr</b>
Multiplier that determines the rate at which slow start increases the size of the TCP transmission window after each acknowledgement of successful transmission.
Default value: 2
Minimum value: 1
Maximum value: 100

<b>maxDynServerProbes</b>
Maximum number of probes that NetScaler can send out in 10 milliseconds, to dynamically learn a service. NetScaler probes for the existence of the origin in case of wildcard virtual server or services.
Default value: 7
Minimum value: 1
Maximum value: 65535

<b>synHoldFastGiveup</b>
Maximum threshold. After crossing this threshold number of outstanding probes for origin, the NetScaler reduces the number of connection retries for probe connections.
Default value: 1024
Minimum value: 256
Maximum value: 65535

<b>maxSynholdPerprobe</b>
Limit the number of client connections (SYN) waiting for status of single probe. Any new SYN packets will be dropped.
Default value: 128
Minimum value: 1
Maximum value: 255

<b>maxSynhold</b>
Limit the number of client connections (SYN) waiting for status of probe system wide. Any new SYN packets will be dropped.
Default value: 16384
Minimum value: 256
Maximum value: 65535

<b>mssLearnInterval</b>
Duration, in seconds, to sample the Maximum Segment Size (MSS) of the services. The NetScaler appliance determines the best MSS to set for the virtual server based on this sampling. The argument to enable maximum segment size (MSS) for virtual servers must be enabled.
Default value: 180
Minimum value: 1
Maximum value: 1048576

<b>mssLearnDelay</b>
Frequency, in seconds, at which the virtual servers learn the Maximum segment size (MSS) from the services. The argument to enable maximum segment size (MSS) for virtual servers must be enabled.
Default value: 3600
Minimum value: 1
Maximum value: 1048576

<b>maxTimeWaitConn</b>
Maximum number of connections to hold in the TCP TIME_WAIT state on a packet engine. New connections entering TIME_WAIT state are proactively cleaned up.
Default value: 7000
Minimum value: 1

<b>maxSynAckRetx</b>
When 'syncookie' is disabled in the TCP profile that is bound to the virtual server or service, and the number of TCP SYN+ACK retransmission by NetScaler for that virtual server or service crosses this threshold, the NetScaler appliance responds by using the TCP SYN-Cookie mechanism.
Default value: 100
Minimum value: 100
Maximum value: 1048576

<b>synAttackDetection</b>
Detect TCP SYN packet flood and send an SNMP trap.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>connFlushIfNoMem</b>
Flush an existing connection if no memory can be obtained for new connection.
HALF_CLOSED_AND_IDLE: Flush a connection that is closed by us but not by peer, or failing that, a connection that is past configured idle time.  New connection fails if no such connection can be found.
FIFO: If no half-closed or idle connection can be found, flush the oldest non-management connection, even if it is active.  New connection fails if the oldest few connections are management connections.
Note: If you enable this setting, you should also consider lowering the zombie timeout and half-close timeout, while setting the NetScaler timeout.
See Also: connFlushThres argument below.
Possible values: NONE, HALFCLOSED_AND_IDLE, FIFO
Default value: 5

<b>connFlushThres</b>
Flush an existing connection (as configured through -connFlushIfNoMem FIFO) if the system has more than specified number of connections, and a new connection is to be established.  Note: This value may be rounded down to be a whole multiple of the number of packet engines running.
Minimum value: 1

<b>mptcpConCloseOnPassiveSF</b>
Accept DATA_FIN/FAST_CLOSE on passive subflow
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>mptcpChecksum</b>
Use MPTCP DSS checksum
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>mptcpSFtimeout</b>
The timeout value in seconds for idle mptcp subflows. If this timeout is not set, idle subflows are cleared after cltTimeout of vserver
Default value: 0
Maximum value: 31536000

<b>mptcpSFReplaceTimeout</b>
The minimum idle time value in seconds for idle mptcp subflows after which the sublow is replaced by new incoming subflow if maximum subflow limit is reached. The priority for replacement is given to those subflow without any transaction
Default value: 10
Maximum value: 31536000

<b>mptcpMaxSF</b>
Maximum number of subflow connections supported in established state per mptcp connection.
Default value: 4
Minimum value: 2
Maximum value: 6

<b>mptcpMaxPendingSF</b>
Maximum number of subflow connections supported in pending join state per mptcp connection.
Default value: 4
Minimum value: 0
Maximum value: 4

<b>mptcpPendingJoinThreshold</b>
Maximum system level pending join connections allowed.
Default value: 0
Minimum value: 0
Maximum value: 4294967294

<b>mptcpRTOsToSwitchSF</b>
Number of RTO's at subflow level, after which MPCTP should start using other subflow.
Default value: 2
Minimum value: 1
Maximum value: 6

<b>mptcpUseBackupOnDSS</b>
When enabled, if NS receives a DSS on a backup subflow, NS will start using that subflow to send data. And if disabled, NS will continue to transmit on current chosen subflow. In case there is some error on a subflow (like RTO's/RST etc.) then NS can choose a backup subflow irrespective of this tunable.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>TcpMaxRetries</b>
Number of RTO's after which a connection should be freed.
Default value: 7
Minimum value: 1
Maximum value: 7

<b>mptcpImmediateSFCloseOnFIN</b>
Allow subflows to close immediately on FIN before the DATA_FIN exchange is completed at mptcp level.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpCloseMptcpSessionOnLastSFClose</b>
Allow to send DATA FIN or FAST CLOSE on mptcp connection while sending FIN or RST on the last subflow.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset ns tcpParam

Use this command to remove ns tcpParam settings.Refer to the set ns tcpParam command for meanings of the arguments.


##Synopsys

unset ns tcpParam [-WS] [-WSVal] [-SACK] [-learnVsvrMSS] [-maxBurst] [-initialCwnd] [-delayedAck] [-downStateRST] [-nagle] [-limitedPersist] [-oooQSize] [-ackOnPush] [-maxPktPerMss] [-pktPerRetx] [-minRTO] [-slowStartIncr] [-maxDynServerProbes] [-synHoldFastGiveup] [-maxSynholdPerprobe] [-maxSynhold] [-mssLearnInterval] [-mssLearnDelay] [-maxTimeWaitConn] [-maxSynAckRetx] [-synAttackDetection] [-connFlushIfNoMem] [-connFlushThres] [-mptcpConCloseOnPassiveSF] [-mptcpChecksum] [-mptcpSFtimeout] [-mptcpSFReplaceTimeout] [-mptcpMaxSF] [-mptcpMaxPendingSF] [-mptcpPendingJoinThreshold] [-mptcpRTOsToSwitchSF] [-mptcpUseBackupOnDSS] [-TcpMaxRetries] [-mptcpImmediateSFCloseOnFIN] [-mptcpCloseMptcpSessionOnLastSFClose]


##show ns tcpParam

Displays the TCP parameters configured on the NetScaler appliance.


##Synopsys

show ns tcpParam


##Outputs

<b>WS</b>
Enable or disable window scaling.

<b>WSVal</b>
Factor used to calculate the new window size.
This argument is needed only when the window scaling is enabled.

<b>SACK</b>
Enable or disable Selective ACKnowledgement (SACK).

<b>learnVsvrMSS</b>
Enable or disable maximum segment size (MSS) learning for virtual servers.

<b>maxBurst</b>
Maximum number of TCP segments allowed in a burst.

<b>initialCwnd</b>
Initial maximum upper limit on the number of TCP packets that can be outstanding on the TCP link to the server.

<b>recvBuffSize</b>
TCP Receive buffer size

<b>delayedAck</b>
Timeout for TCP delayed ACK, in milliseconds.

<b>downStateRST</b>
Flag to switch on RST on down services.

<b>nagle</b>
Enable or disable the Nagle algorithm on TCP connections.

<b>limitedPersist</b>
Limit the number of persist (zero window) probes.

<b>oooQSize</b>
Maximum size of out-of-order packets queue. A value of 0 means no limit.

<b>ackOnPush</b>
Immediate ACK on PUSH packet

<b>maxPktPerMss</b>
Maximum packets per MSS

<b>pktPerRetx</b>
Maximum packets per retransmission

<b>minRTO</b>
Minimum retransmission timeout, in milliseconds, specified in 10-millisecond increments (value must yield a whole number if divided by 10).

<b>slowStartIncr</b>
TCP slowstart increment factor

<b>maxDynServerProbes</b>
Maximum number of probes that NetScaler can send out in 10 milliseconds, to dynamically learn a service. NetScaler probes for the existence of the origin in case of wildcard virtual server or services.

<b>synHoldFastGiveup</b>
Maximum threshold. After crossing this threshold number of outstanding probes for origin, the NetScaler reduces the number of connection retries for probe connections.

<b>maxSynholdPerprobe</b>
Limit the number of client connections (SYN) waiting for status of single probe. Any new SYN packets will be dropped.

<b>maxSynhold</b>
Limit the number of client connections (SYN) waiting for status of probe system wide. Any new SYN packets will be dropped.

<b>mssLearnInterval</b>
Duration, in seconds, to sample the Maximum Segment Size (MSS) of the services. The NetScaler appliance determines the best MSS to set for the virtual server based on this sampling. The argument to enable maximum segment size (MSS) for virtual servers must be enabled.

<b>mssLearnDelay</b>
Frequency, in seconds, at which the virtual servers learn the Maximum segment size (MSS) from the services. The argument to enable maximum segment size (MSS) for virtual servers must be enabled.

<b>maxTimeWaitConn</b>
Maximum number of connections to hold in the TCP TIME_WAIT state on a packet engine. New connections entering TIME_WAIT state are proactively cleaned up.

<b>KAprobeUpdateLastactivity</b>
Update last activity for KA probes

<b>maxSynAckRetx</b>
When 'syncookie' is disabled in the TCP profile that is bound to the virtual server or service, and the number of TCP SYN+ACK retransmission by NetScaler for that virtual server or service crosses this threshold, the NetScaler appliance responds by using the TCP SYN-Cookie mechanism.

<b>synAttackDetection</b>
Detect TCP SYN packet flood and send an SNMP trap.

<b>connFlushIfNoMem</b>
Flush an existing connection if no memory can be obtained for new connection.
HALF_CLOSED_AND_IDLE: Flush a connection that is closed by us but not by peer, or failing that, a connection that is past configured idle time.  New connection fails if no such connection can be found.
FIFO: If no half-closed or idle connection can be found, flush the oldest non-management connection, even if it is active.  New connection fails if the oldest few connections are management connections.
Note: If you enable this setting, you should also consider lowering the zombie timeout and half-close timeout, while setting the NetScaler timeout.
See Also: connFlushThres argument below.

<b>connFlushThres</b>
Flush an existing connection (as configured through -connFlushIfNoMem FIFO) if the system has more than specified number of connections, and a new connection is to be established.  Note: This value may be rounded down to be a whole multiple of the number of packet engines running.

<b>mptcpConCloseOnPassiveSF</b>
Accept DATA_FIN/FAST_CLOSE on passive subflow

<b>mptcpChecksum</b>
Use MPTCP DSS checksum

<b>mptcpSFtimeout</b>
The timeout value in seconds for idle mptcp subflows. If this timeout is not set, idle subflows are cleared after cltTimeout of vserver

<b>mptcpSFReplaceTimeout</b>
The minimum idle time value in seconds for idle mptcp subflows after which the sublow is replaced by new incoming subflow if maximum subflow limit is reached. The priority for replacement is given to those subflow without any transaction

<b>mptcpMaxSF</b>
Maximum number of subflow connections supported in established state per mptcp connection.

<b>mptcpMaxPendingSF</b>
Maximum number of subflow connections supported in pending join state per mptcp connection.

<b>mptcpPendingJoinThreshold</b>
Maximum system level pending join connections allowed.

<b>mptcpRTOsToSwitchSF</b>
Number of RTO's at subflow level, after which MPCTP should start using other subflow.

<b>mptcpUseBackupOnDSS</b>
When enabled, if NS receives a DSS on a backup subflow, NS will start using that subflow to send data. And if disabled, NS will continue to transmit on current chosen subflow. In case there is some error on a subflow (like RTO's/RST etc.) then NS can choose a backup subflow irrespective of this tunable.

<b>TcpMaxRetries</b>
Number of RTO's after which a connection should be freed.

<b>mptcpImmediateSFCloseOnFIN</b>
Allow subflows to close immediately on FIN before the DATA_FIN exchange is completed at mptcp level.

<b>mptcpCloseMptcpSessionOnLastSFClose</b>
Allow to send DATA FIN or FAST CLOSE on mptcp connection while sending FIN or RST on the last subflow.

<b>builtin</b>
Flag to determine if the tcp param is built-in or not



