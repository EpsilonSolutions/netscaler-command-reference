#ns tcpProfile

The following operations can be performed on "ns tcpProfile":


[add](#add-ns-tcpprofile) | [rm](#rm-ns-tcpprofile) | [set](#set-ns-tcpprofile) | [unset](#unset-ns-tcpprofile) | [show](#show-ns-tcpprofile)

##add ns tcpProfile

Adds a TCP profile to the NetScaler appliance.


##Synopsys

add ns tcpProfile &lt;name> [-WS ( ENABLED | DISABLED )] [-SACK ( ENABLED | DISABLED )] [-WSVal &lt;positive_integer>] [-nagle ( ENABLED | DISABLED )] [-ackOnPush ( ENABLED | DISABLED )] [-mss &lt;positive_integer>] [-maxBurst &lt;positive_integer>] [-initialCwnd &lt;positive_integer>] [-delayedAck &lt;positive_integer>] [-oooQSize &lt;positive_integer>] [-maxPktPerMss &lt;positive_integer>] [-pktPerRetx &lt;positive_integer>] [-minRTO &lt;positive_integer>] [-slowStartIncr &lt;positive_integer>] [-bufferSize &lt;positive_integer>] [-synCookie ( ENABLED | DISABLED )] [-KAprobeUpdateLastactivity ( ENABLED | DISABLED )] [-flavor &lt;flavor>] [-dynamicReceiveBuffering ( ENABLED | DISABLED )] [-KA ( ENABLED | DISABLED )] [-KAconnIdleTime &lt;positive_integer>] [-KAmaxProbes &lt;positive_integer>] [-KAprobeInterval &lt;positive_integer>] [-sendBuffsize &lt;positive_integer>] [-mptcp ( ENABLED | DISABLED )] [-EstablishClientConn &lt;EstablishClientConn>] [-tcpSegOffload ( AUTOMATIC | DISABLED )] [-rstWindowAttenuate ( ENABLED | DISABLED )] [-rstMaxAck ( ENABLED | DISABLED )] [-spoofSynDrop ( ENABLED | DISABLED )] [-ecn ( ENABLED | DISABLED )] [-mptcpDropDataOnPreEstSF ( ENABLED | DISABLED )] [-mptcpFastOpen ( ENABLED | DISABLED )] [-mptcpSessionTimeout &lt;positive_integer>] [-TimeStamp ( ENABLED | DISABLED )] [-dsack ( ENABLED | DISABLED )] [-ackAggregation ( ENABLED | DISABLED )] [-frto ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for a TCP profile. Must begin with a letter, number, or the underscore \\(_\\) character. Other characters allowed, after the first character, are the hyphen \\(-\\), period \\(.\\), hash \\(\\#\\), space \\( \\), at \\(@\\), and equal \\(=\\) characters. The name of a TCP profile cannot be changed after it is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my tcp profile" or 'my tcp profile'\\).

<b>WS</b>
Enable or disable window scaling.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>SACK</b>
Enable or disable Selective ACKnowledgement (SACK).
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>WSVal</b>
Factor used to calculate the new window size.
This argument is needed only when window scaling is enabled.
Default value: 4
Maximum value: 14

<b>nagle</b>
Enable or disable the Nagle algorithm on TCP connections.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ackOnPush</b>
Send immediate positive acknowledgement (ACK) on receipt of TCP packets when doing Web 2.0 PUSH.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>mss</b>
Maximum number of octets to allow in a TCP data segment.
Maximum value: 9176

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

<b>oooQSize</b>
Maximum size of out-of-order packets queue. A value of 0 means no limit.
Default value: 64
Maximum value: 65535

<b>maxPktPerMss</b>
Maximum number of TCP packets allowed per maximum segment size (MSS).
Maximum value: 1460

<b>pktPerRetx</b>
Maximum limit on the number of packets that should be retransmitted on receiving a partial ACK.
Default value: 1
Minimum value: 1
Maximum value: 512

<b>minRTO</b>
Minimum retransmission timeout, in milliseconds.
Default value: 1000
Minimum value: 10
Maximum value: 64000

<b>slowStartIncr</b>
Multiplier that determines the rate at which slow start increases the size of the TCP transmission window after each acknowledgement of successful transmission.
Default value: 2
Minimum value: 1
Maximum value: 100

<b>bufferSize</b>
TCP buffering size, in bytes.
Default value: 8190
Minimum value: 8190
Maximum value: 4194304

<b>synCookie</b>
Enable or disable the SYNCOOKIE mechanism for TCP handshake with clients. Disabling SYNCOOKIE prevents SYN attack protection on the NetScaler appliance.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>KAprobeUpdateLastactivity</b>
Update last activity for the connection after receiving keep-alive (KA) probes.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>flavor</b>
Set TCP congestion control algorithm.
Possible values: Default, Westwood, BIC, CUBIC
Default value: NS_TCP_DEFAULT

<b>dynamicReceiveBuffering</b>
Enable or disable dynamic receive buffering. When enabled, allows the receive buffer to be adjusted dynamically based on memory and network conditions.
Note: The buffer size argument must be set for dynamic adjustments to take place.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>KA</b>
Send periodic TCP keep-alive (KA) probes to check if peer is still up.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>KAconnIdleTime</b>
Duration, in seconds, for the connection to be idle, before sending a keep-alive (KA) probe.
Default value: NSTCP_KA_DEFAULT_CONN_IDLETIME
Minimum value: 1
Maximum value: 4095

<b>KAmaxProbes</b>
Number of keep-alive (KA) probes to be sent when not acknowledged, before assuming the peer to be down.
Default value: NSTCP_KA_DEFAULT_PROBE_COUNT
Minimum value: 1
Maximum value: 255

<b>KAprobeInterval</b>
Time interval, in seconds, before the next keep-alive (KA) probe, if the peer does not respond.
Default value: NSTCP_KA_DEFAULT_INTERVAL
Minimum value: 1
Maximum value: 4095

<b>sendBuffsize</b>
TCP Send Buffer Size
Default value: 8190
Minimum value: 8190
Maximum value: 4194304

<b>mptcp</b>
Enable or disable Multipath TCP.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>EstablishClientConn</b>
Establishing Client Client connection on First data/ Final-ACK / Automatic
Possible values: AUTOMATIC, CONN_ESTABLISHED, ON_FIRST_DATA
Default value: NS_CONN_AUTOMATIC

<b>tcpSegOffload</b>
Offload TCP segmentation to the NIC. If set to AUTOMATIC, TCP segmentation will be offloaded to the NIC, if the NIC supports it.
Possible values: AUTOMATIC, DISABLED
Default value: ENABLED

<b>rstWindowAttenuate</b>
Enable or disable RST window attenuation to protect against spoofing. When enabled, will reply with corrective ACK when a sequence number is invalid.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rstMaxAck</b>
Enable or disable acceptance of RST that is out of window yet echoes highest ACK sequence number. Useful only in proxy mode.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>spoofSynDrop</b>
Enable or disable drop of invalid SYN packets to protect against spoofing. When disabled, established connections will be reset when a SYN packet is received.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>ecn</b>
Enable or disable TCP Explicit Congestion Notification.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpDropDataOnPreEstSF</b>
Enable or disable silently dropping the data on Pre-Established subflow. When enabled, DSS data packets are dropped silently instead of dropping the connection when data is received on pre established subflow.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpFastOpen</b>
Enable or disable Multipath TCP fastopen. When enabled, DSS data packets are accepted before receiving the third ack of SYN handshake.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpSessionTimeout</b>
MPTCP session timeout in seconds. If this value is not set, idle MPTCP sessions are flushed after vserver's client idle timeout.
Default value: 0
Minimum value: 0
Maximum value: 86400

<b>TimeStamp</b>
Enable or Disable TCP Timestamp option (RFC 1323)
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dsack</b>
Enable or disable DSACK.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>ackAggregation</b>
Enable or disable ACK Aggregation.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>frto</b>
Enable or disable FRTO (Forward RTO-Recovery).
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add tcpprofile &lt;profile name&gt; -WS ENABLED -WSVAL 4

##rm ns tcpProfile

Removes a TCP profile from the appliance.


##Synopsys

rm ns tcpProfile &lt;name>


##Arguments

<b>name</b>
Name of the TCP profile to be removed.



##Example

rm tcpprofile &lt;profile name&gt;

##set ns tcpProfile

Modifies the attributes of a TCP profile.


##Synopsys

set ns tcpProfile &lt;name> [-WS ( ENABLED | DISABLED )] [-SACK ( ENABLED | DISABLED )] [-WSVal &lt;positive_integer>] [-nagle ( ENABLED | DISABLED )] [-ackOnPush ( ENABLED | DISABLED )] [-mss &lt;positive_integer>] [-maxBurst &lt;positive_integer>] [-initialCwnd &lt;positive_integer>] [-delayedAck &lt;positive_integer>] [-oooQSize &lt;positive_integer>] [-maxPktPerMss &lt;positive_integer>] [-pktPerRetx &lt;positive_integer>] [-minRTO &lt;positive_integer>] [-slowStartIncr &lt;positive_integer>] [-bufferSize &lt;positive_integer>] [-synCookie ( ENABLED | DISABLED )] [-KAprobeUpdateLastactivity ( ENABLED | DISABLED )] [-flavor &lt;flavor>] [-dynamicReceiveBuffering ( ENABLED | DISABLED )] [-KA ( ENABLED | DISABLED )] [-KAconnIdleTime &lt;positive_integer>] [-KAmaxProbes &lt;positive_integer>] [-KAprobeInterval &lt;positive_integer>] [-sendBuffsize &lt;positive_integer>] [-mptcp ( ENABLED | DISABLED )] [-EstablishClientConn &lt;EstablishClientConn>] [-tcpSegOffload ( AUTOMATIC | DISABLED )] [-rstWindowAttenuate ( ENABLED | DISABLED )] [-rstMaxAck ( ENABLED | DISABLED )] [-spoofSynDrop ( ENABLED | DISABLED )] [-ecn ( ENABLED | DISABLED )] [-mptcpDropDataOnPreEstSF ( ENABLED | DISABLED )] [-mptcpFastOpen ( ENABLED | DISABLED )] [-mptcpSessionTimeout &lt;positive_integer>] [-TimeStamp ( ENABLED | DISABLED )] [-dsack ( ENABLED | DISABLED )] [-ackAggregation ( ENABLED | DISABLED )] [-frto ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the TCP profile to be modified.

<b>WS</b>
Enable or disable window scaling.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>SACK</b>
Enable or disable Selective ACKnowledgement (SACK).
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>WSVal</b>
Factor used to calculate the new window size.
This argument is needed only when window scaling is enabled.
Default value: 4
Maximum value: 14

<b>nagle</b>
Enable or disable the Nagle algorithm on TCP connections.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ackOnPush</b>
Send immediate positive acknowledgement (ACK) on receipt of TCP packets when doing Web 2.0 PUSH.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>mss</b>
Set Maximum Segment Size(MSS) to use for TCP Connection(0 forces use of global setting)
Maximum value: 9176

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

<b>oooQSize</b>
Maximum size of out-of-order packets queue. A value of 0 means no limit.
Default value: 64
Maximum value: 65535

<b>maxPktPerMss</b>
Maximum number of TCP packets allowed per maximum segment size (MSS).
Maximum value: 1460

<b>pktPerRetx</b>
Maximum limit on the number of packets that should be retransmitted on receiving a partial ACK.
Default value: 1
Minimum value: 1
Maximum value: 512

<b>minRTO</b>
Minimum retransmission timeout, in milliseconds.
Default value: 1000
Minimum value: 10
Maximum value: 64000

<b>slowStartIncr</b>
Multiplier that determines the rate at which slow start increases the size of the TCP transmission window after each acknowledgement of successful transmission.
Default value: 2
Minimum value: 1
Maximum value: 100

<b>bufferSize</b>
TCP buffering size, in bytes.
Default value: 8190
Minimum value: 8190
Maximum value: 4194304

<b>synCookie</b>
Enable or disable the SYNCOOKIE mechanism for TCP handshake with clients. Disabling SYNCOOKIE prevents SYN attack protection on the NetScaler appliance.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>KAprobeUpdateLastactivity</b>
Update last activity for the connection after receiving keep-alive (KA) probes.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>flavor</b>
Set TCP congestion control algorithm.
Possible values: Default, Westwood, BIC, CUBIC
Default value: NS_TCP_DEFAULT

<b>dynamicReceiveBuffering</b>
Enable or disable dynamic receive buffering. When enabled, allows the receive buffer to be adjusted dynamically based on memory and network conditions.
Note: The buffer size argument must be set for dynamic adjustments to take place.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>KA</b>
Send periodic TCP keep-alive (KA) probes to check if peer is still up.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>KAconnIdleTime</b>
Duration, in seconds, for the connection to be idle, before sending a keep-alive (KA) probe.
Default value: NSTCP_KA_DEFAULT_CONN_IDLETIME
Minimum value: 1
Maximum value: 4095

<b>KAmaxProbes</b>
Number of keep-alive (KA) probes to be sent when not acknowledged, before assuming the peer to be down.
Default value: NSTCP_KA_DEFAULT_PROBE_COUNT
Minimum value: 1
Maximum value: 255

<b>KAprobeInterval</b>
Time interval, in seconds, before the next keep-alive (KA) probe, if the peer does not respond.
Default value: NSTCP_KA_DEFAULT_INTERVAL
Minimum value: 1
Maximum value: 4095

<b>sendBuffsize</b>
TCP Send Buffer Size
Default value: 8190
Minimum value: 8190
Maximum value: 4194304

<b>mptcp</b>
Enable or disable Multipath TCP.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>EstablishClientConn</b>
Establishing Client Client connection on First data/ Final-ACK / Automatic
Possible values: AUTOMATIC, CONN_ESTABLISHED, ON_FIRST_DATA
Default value: NS_CONN_AUTOMATIC

<b>tcpSegOffload</b>
Offload TCP segmentation to the NIC. If set to AUTOMATIC, TCP segmentation will be offloaded to the NIC, if the NIC supports it.
Possible values: AUTOMATIC, DISABLED
Default value: ENABLED

<b>rstWindowAttenuate</b>
Enable or disable RST window attenuation to protect against spoofing. When enabled, will reply with corrective ACK when a sequence number is invalid.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rstMaxAck</b>
Enable or disable acceptance of RST that is out of window yet echoes highest ACK sequence number. Useful only in proxy mode.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>spoofSynDrop</b>
Enable or disable drop of invalid SYN packets to protect against spoofing. When disabled, established connections will be reset when a SYN packet is received.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>ecn</b>
Enable or disable TCP Explicit Congestion Notification.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpDropDataOnPreEstSF</b>
Enable or disable silently dropping the data on Pre-Established subflow. When enabled, DSS data packets are dropped silently instead of dropping the connection when data is received on pre established subflow.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpFastOpen</b>
Enable or disable Multipath TCP fastopen. When enabled, DSS data packets are accepted before receiving the third ack of SYN handshake.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mptcpSessionTimeout</b>
MPTCP session timeout in seconds. If this value is not set, idle MPTCP sessions are flushed after vserver's client idle timeout.
Default value: 0
Minimum value: 0
Maximum value: 86400

<b>TimeStamp</b>
Enable or Disable TCP Timestamp option (RFC 1323)
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dsack</b>
Enable or disable DSACK.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>ackAggregation</b>
Enable or disable ACK Aggregation.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>frto</b>
Enable or disable FRTO (Forward RTO-Recovery).
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set tcpprofile &lt;profile name&gt; -WS ENABLED -WSVAL 4

##unset ns tcpProfile

Removes the attributes of the TCP profile. Attributes for which a default value is available revert to their default values. Refer to the 'set ns tcpProfile' command for a description of the parameters..Refer to the set ns tcpProfile command for meanings of the arguments.


##Synopsys

unset ns tcpProfile &lt;name> [-WS] [-SACK] [-WSVal] [-nagle] [-ackOnPush] [-mss] [-maxBurst] [-initialCwnd] [-delayedAck] [-oooQSize] [-maxPktPerMss] [-pktPerRetx] [-minRTO] [-slowStartIncr] [-bufferSize] [-synCookie] [-KAprobeUpdateLastactivity] [-flavor] [-dynamicReceiveBuffering] [-KA] [-KAmaxProbes] [-KAconnIdleTime] [-KAprobeInterval] [-sendBuffsize] [-mptcp] [-EstablishClientConn] [-tcpSegOffload] [-rstWindowAttenuate] [-rstMaxAck] [-spoofSynDrop] [-ecn] [-mptcpDropDataOnPreEstSF] [-mptcpFastOpen] [-mptcpSessionTimeout] [-TimeStamp] [-dsack] [-ackAggregation] [-frto]


##show ns tcpProfile

Displays information about TCP profiles configured on the appliance.


##Synopsys

show ns tcpProfile [&lt;name>]


##Arguments

<b>name</b>
Name of the TCP profile to be displayed. If a name is not provided, information about all TCP profiles is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>WS</b>
Enable or disable window scaling.

<b>SACK</b>
Enable or disable Selective ACKnowledgement (SACK).

<b>WSVal</b>
Factor used to calculate the new window size.
This argument is needed only when window scaling is enabled.

<b>nagle</b>
Enable or disable the Nagle algorithm on TCP connections.

<b>ackOnPush</b>
Send immediate positive acknowledgement (ACK) on receipt of TCP packets when doing Web 2.0 PUSH.

<b>mss</b>
Maximum Segment Size(MSS) to use for TCP Connection(0 forces use of global setting)

<b>maxBurst</b>
Maximum number of TCP segments allowed in a burst.

<b>initialCwnd</b>
Initial maximum upper limit on the number of TCP packets that can be outstanding on the TCP link to the server.

<b>delayedAck</b>
Timeout for TCP delayed ACK, in milliseconds.

<b>oooQSize</b>
Maximum size of out-of-order packets queue. A value of 0 means no limit.

<b>maxPktPerMss</b>
Maximum packet per MSS value

<b>pktPerRetx</b>
Maximum limit on the number of packets that should be retransmitted on receiving a partial ACK.

<b>minRTO</b>
TCP minimum RTO (in millisec)

<b>slowStartIncr</b>
TCP slowstart increment factor

<b>bufferSize</b>
TCP Buffer size

<b>flavor</b>
TCP algorithm

<b>refCnt</b>
Number of entities using this profile

<b>synCookie</b>
Enable or disable the SYNCOOKIE mechanism for TCP handshake with clients. Disabling SYNCOOKIE prevents SYN attack protection on the NetScaler appliance.

<b>KAprobeUpdateLastactivity</b>
Update last activity for the connection after receiving keep-alive (KA) probes.

<b>dynamicReceiveBuffering</b>
Enable or disable dynamic receive buffering. When enabled, allows the receive buffer to be adjusted dynamically based on memory and network conditions.
Note: The buffer size argument must be set for dynamic adjustments to take place.

<b>KA</b>
Send periodic TCP keep-alive (KA) probes to check if peer is still up.

<b>KAconnIdleTime</b>
Duration, in seconds, for the connection to be idle, before sending a keep-alive (KA) probe.

<b>KAmaxProbes</b>
Number of keep-alive (KA) probes to be sent when not acknowledged, before assuming the peer to be down.

<b>KAprobeInterval</b>
Time interval, in seconds, before the next keep-alive (KA) probe, if the peer does not respond.

<b>sendBuffsize</b>
TCP Send Buffer size

<b>mptcp</b>
Enable/Disable Multi-Path TCP

<b>EstablishClientConn</b>
Allocating Client Conn on

<b>tcpSegOffload</b>
TCP Segmentation Offload

<b>rstWindowAttenuate</b>
RST Window Attenuation

<b>rstMaxAck</b>
accept RST with max ACK

<b>TimeStamp</b>
TCP Timestamp Option

<b>spoofSynDrop</b>
drop invalid SYN packets

<b>ecn</b>
Explicit Congestion Notification

<b>mptcpDropDataOnPreEstSF</b>
Enable or disable dropping data on pre established subflow.

<b>mptcpFastOpen</b>
Enable or disable MPTCP fastopen.

<b>mptcpSessionTimeout</b>
MPTCP session timeout.

<b>dsack</b>
Enable or disable DSACK.

<b>ackAggregation</b>
Enable or disable ACK Aggregation.

<b>frto</b>
Enable or disable FRTO (Forward RTO-Recovery).

<b>stateflag</b>
State flag

<b>devno</b>

<b>count</b>



##Example

show tcp profile [profile name]

