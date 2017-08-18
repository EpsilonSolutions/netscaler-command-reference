#ns connectiontable

The following operations can be performed on "ns connectiontable":


##show ns connectiontable

Displays the current TCP/IP connection table.


##Synopsys

show ns connectiontable [&lt;filterexpression>] [-detail &lt;detail> ...] [-Listen]


##Arguments

<b>filterexpression</b>
The maximum length of filter expression is 255 and it can be of following format:
  &lt;expression&gt; [&lt;relop&gt; &lt;expression&gt;]
    &lt;relop&gt; = ( && | || )
    &lt;expression&gt; =:
    CONNECTION.&lt;qualifier&gt;.&lt;qualifier-method&gt;.(&lt;qualifier-value&gt;)
    &lt;qualifier&gt; = SRCIP
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid IPv4 address
    example = CONNECTION.SRCIP.EQ(127.0.0.1)
    &lt;qualifier&gt; = DSTIP
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid IPv4 address.
    example = CONNECTION.DSTIP.EQ(127.0.0.1)
    &lt;qualifier&gt; = IP
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid IPv4 address.
    example = CONNECTION.IP.EQ(127.0.0.1)
    &lt;qualifier&gt; = SRCIPv6
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid IPv6 address.
    example = CONNECTION.SRCIPv6.EQ(2001:db8:0:0:1::1)
    &lt;qualifier&gt; = DSTIPv6
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid IPv6 address.
    example = CONNECTION.DSTIPv6.EQ(2001:db8:0:0:1::1)
    &lt;qualifier&gt; = IPv6
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid IPv6 address.
    example = CONNECTION.IPv6.EQ(2001:db8:0:0:1::1)
    &lt;qualifier&gt; = SRCPORT
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid port number.
    example = CONNECTION.SRCPORT.EQ(80)
    &lt;qualifier&gt; = DSTPORT
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid port number.
    example = CONNECTION.DSTPORT.EQ(80)
    &lt;qualifier&gt; = PORT
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid port number.
    example = CONNECTION.PORT.EQ(80)
    &lt;qualifier&gt; = SVCNAME
    &lt;qualifier-method&gt; = [ EQ | NE | CONTAINS | STARTSWITH
                        | ENDSWITH ]
    &lt;qualifier-value&gt;  = service name.
    example = CONNECTION.SVCNAME.EQ("name")
    &lt;qualifier&gt; = LB_VSERVER.NAME
    &lt;qualifier-method&gt; = [ EQ | NE | CONTAINS | STARTSWITH
                        | ENDSWITH ]
    &lt;qualifier-value&gt;  = LB vserver name.
    example = CONNECTION.LB_VSERVER.NAME.EQ("name")
    &lt;qualifier&gt; = CS_VSERVER.NAME
    &lt;qualifier-method&gt; = [ EQ | NE | CONTAINS | STARTSWITH
                        | ENDSWITH ]
    &lt;qualifier-value&gt;  = CS vserver name.
    example = CONNECTION.CS_VSERVER.NAME.EQ("name")
    &lt;qualifier&gt; = INTF
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = A valid interface id in the form of
                x/y (n/x/y in case of cluster interface).
    examle = CONNECTION.INTF.EQ("0/1/1")
    &lt;qualifier&gt; = VLANID
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid VLAN ID.
    example = CONNECTION.VLANID.EQ(0)
    &lt;qualifier&gt; = CONNID
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid PCB dev number.
    example = CONNECTION.CONNID.EQ(0)
    &lt;qualifier&gt; = PPEID
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid core ID.
      example = CONNECTION.PPEID.EQ(0)
    &lt;qualifier&gt; = IDLETIME
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A positive integer indicating the
                   idletime.
    example = CONNECTION.IDLETIME.LT(100)
    &lt;qualifier&gt; = TCPSTATE
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = ( CLOSE_WAIT | CLOSED | CLOSING |
           ESTABLISHED | FIN_WAIT_1 | FIN_WAIT_2 | LAST_ACK |
        LISTEN | SYN_RECEIVED | SYN_SENT | TIME_WAIT |
        NOT_APPLICABLE)
    example = CONNECTION.TCPSTATE.EQ(LISTEN)
    &lt;qualifier&gt; = SERVICE_TYPE
    &lt;qualifier-method&gt; = [ EQ | NE ]
    &lt;qualifier-value&gt;  = ( SVC_HTTP | FTP | TCP | UDP | SSL |
        SSL_BRIDGE | SSL_TCP | NNTP | RPCSVR | RPCSVRS |
        RPCCLNT | SVC_DNS | ADNS | SNMP | RTSP | DHCPRA | NAT | ANY |
        MONITOR | MONITOR_UDP | MONITOR_PING | SIP_UDP |
        SVC_MYSQL | SVC_MSSQL | SERVICE_UNKNOWN )
    example = CONNECTION.SERVICE_TYPE.EQ(ANY)
    &lt;qualifier&gt; = TRAFFIC_DOMAIN_ID
    &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                        | BETWEEN ]
    &lt;qualifier-value&gt;  = A valid traffic domain ID.
    example = CONNECTION.TRAFFIC_DOMAIN_ID.EQ(0)
    common usecases:
    Filtering out loopback connections and view present
    connections through netsclaer
    show connectiontable "CONNECTION.IP.NEQ(127.0.0.1) &&
    CONNECTION.TCPSTATE.EQ(ESTABLISHED)" -detail full
    show connections from a particular sourceip and targeted
    to port 80
    show connectiontable "CONNECTION.SRCIP.EQ(10.102.1.91) &&
    CONNECTION.DSTPORT.EQ(80)"
    show connection particular to a service and its linked
    client connections
    show connectiontable "CONNECTION.SVCNAME.EQ("S1")"
    -detail link
    show connections for a particular servicetype(e.g.http)
    show connectiontable "CONNECTION.SERVICE_TYPE.EQ(TCP)"
    viewing connections that have been idle for a long time
    show connectiontable "CONNECTION.IDLETIME.GT(100)"
    show connections for a particular interface and vlan
    show connectiontable "CONNECTION.INTF.EQ("1/1") &&
    CONNECTION.VLANID.EQ(1)"

<b>detail</b>
Specify display options for the connection table.
* LINK - Displays the linked PCB (Protocol Control Block).
* NAME - Displays along with the service name.
* CONNFAILOVER - Displays PCB with connection failover.
* FULL - Displays all available details.

<b>Listen</b>
Display listening services only



##Outputs

<b>SOURCEIP</b>
Source IP of the connection.

<b>SOURCEPORT</b>
Source port of the connection.

<b>DESTIP</b>
Destination IP of the connection.

<b>DESTPORT</b>
Destination port of the connection.

<b>SVCTYPE</b>
Protocol supported by the connection.

<b>IDLETIME</b>
Time since last activity was detected on the connection.

<b>STATE</b>
Current TCP/IP state of the connection.

<b>linkSourceIP</b>
Source IP of the link connection.

<b>linkSourcePort</b>
Source port of the link connection.

<b>linkDestIP</b>
Destination IP of the link connection.

<b>linkDestPort</b>
Destination port of the link connection.

<b>linkServiceType</b>
Protocol supported by the link connection.

<b>linkIdleTime</b>
Time since last activity was detected on link connection.

<b>linkState</b>
TCP/IP current state of link connection.

<b>entityName</b>
NetScaler entity name for the connection.

<b>linkEntityName</b>
NetScaler entity name for link connection.

<b>connectionNumber</b>
Connection number

<b>linkConnectionNumber</b>
Link connection number

<b>connid</b>
Unique transaction number for the connection.

<b>linkConnid</b>
Unique transaction number for the peer connection.

<b>connProperties</b>
flags used to store connection properties like client, server etc.

<b>optionFlags</b>
flags used to store TCP options like Sack, WS

<b>nsWSvalue</b>
netscaler window scaling value

<b>peerWSvalue</b>
peer window scaling value

<b>mss</b>
Client side MSS for the connection - used in server SYN.

<b>retxRetryCnt</b>
Retransmission retry count for the connection.

<b>rcvWnd</b>
Received Advertised Window for the connection.

<b>advWnd</b>
Sent advertised window for the connection.

<b>sndCwnd</b>
sent congestion window for the connection.

<b>iss</b>
Initial send sequence number for the connection.

<b>irs</b>
Initial receive sequence number for the connection.

<b>rcvNxt</b>
next expecting seq number for the connection.

<b>maxAck</b>
current running max ack sent for the connection.

<b>sndNxt</b>
next bytes seq number for the connection.

<b>sndUnAck</b>
Most recently received ACK for the connection.

<b>httpEndSeq</b>
HTTP parsing tracking seq number for the connection.

<b>httpState</b>
HTTP Protocol  state for the connection.

<b>trCount</b>
Max reuests allowed per connection.

<b>priority</b>
priority of the connection.

<b>httpReqVer</b>
current HTTP request version on the connection.

<b>httpRequest</b>
current HTTP request type on the connection.

<b>httpRspCode</b>
current response type on the connection.

<b>rttSmoothed</b>
smoothed RTT value of the connection.

<b>rttVariance</b>
RTT variance for the connection.

<b>outoforderPkts</b>
held packets on the connection.

<b>count</b>

<b>linkOptionFlag</b>
Link connection's TCP option flag for Sack and WS

<b>linknsWSvalue</b>
Link connection-s netscaler window scaling value

<b>linkpeerWSvalue</b>
Link connection-s peer netscaler window scaling value

<b>linkMSS</b>
Client side MSS for the Link connection - used in server SYN

<b>linkRetxRetryCnt</b>
Retransmission retry count for the Link connection.

<b>linkRcvWnd</b>
Received Advertised Window for the Link connection.

<b>linkAdvWnd</b>
Sent advertised window for the Link connection.

<b>linkSndCwnd</b>
Send congestion window for the Link connection.

<b>linkISS</b>
Initial send seq number for the Link connection.

<b>linkIRS</b>
Initial receive seq number for the Link connection.

<b>linkRcvNxt</b>
Next expecting seq number on the Link connection.

<b>linkMaxAck</b>
Current running maximum ack sent on the Link connection.

<b>linkSndNxt</b>
Next bytes seq number for the Link connection.

<b>linkSndUnAck</b>
Most recently received ACK on the Link connection.

<b>linkHttpEndSeq</b>
HTTP parsing tracking seq number on the Link connection.

<b>linkHttpState</b>
HTTP protocol state on the Link connection.

<b>linkTrCount</b>
Max requests per connection for Link connection.

<b>linkPriority</b>
Priority for the Link connection.

<b>linkHttpReqVer</b>
HTTP current request version on Link connection.

<b>linkHttpReq</b>
HTTP current request type on Link connection.

<b>linkHttpRspCode</b>
Current response type on link connection.

<b>linkRttSmoothed</b>
Smoothed RTT value on link connection.

<b>linkRttVariance</b>
RTT variance on Link connection.

<b>linkHeldPkts</b>
Held packets on Link connection.

<b>targetnodeidnnm</b>
NNM connection target node ID.

<b>sourcenodeidnnm</b>
NNM connection source node ID.

<b>channelidnnm</b>
NNM connection channel ID.

<b>msgversionnnm</b>
nnm message version.

<b>td</b>
Traffic Domain Id.

<b>maxRcvbuf</b>
Maximum receive window that application advertizes to peer.

<b>linkmaxRcvbuf</b>
Maximum receive window that application advertizes to peer in linked connection.

<b>RxQsize</b>
Total number of bytes in Netscaler receive buffer. This includes bytes being processed / policy related data / stored in application buffer.

<b>linkRxQsize</b>
Total number of bytes in Netscaler receive buffer for linked connection. This includes bytes being processed / policy related data / stored in application buffer.

<b>maxSndbuf</b>
Maximum send window that application can process and send.

<b>linkmaxSndbuf</b>
Maximum send window that application can process and send in linked connection.

<b>TxQsize</b>
Total number of bytes in Netscaler send buffer. This includes both inflight and queued bytes in netscaler.

<b>linkTxQsize</b>
Total number of bytes in Netscaler send buffer for linked connection. This includes both inflight and queued bytes in netscaler.

<b>flavor</b>
TCP congestion control algorithm.

<b>linkflavor</b>
TCP congestion control algorithm for a linked connection.

<b>bwEstimate</b>
TCP Bandwidth Estimate

<b>linkbwEstimate</b>
TCP Bandwidth Estimate for a linked connection

<b>rttMin</b>
Minimum Round Trip Time for the connection.

<b>linkrttMin</b>
Minimum Round Trip Time for linked connection.

<b>name</b>
Name of TCP profile attached to the connection.

<b>linkName</b>
Name of TCP profile attached to the connection.

<b>tcpmode</b>
TCP Optimization modes TRANSPARENT / ENDPOINT.

<b>linktcpmode</b>
TCP Optimization modes TRANSPARENT / ENDPOINT for linked connection.

<b>realTimeRtt</b>
Real Time / Instantaneous round trip time.

<b>linkrealTimeRtt</b>
Real Time / Instantaneous round trip time for linked connection.

<b>sndBuf</b>
send buffer size.

<b>linksndBuf</b>
Send buffer size for linked connection.

<b>nsbTcpwaitQ</b>
Number of packets in TCP wait queue.

<b>linknsbTcpwaitQ</b>
Number of packets in wait queue for linked connection.

<b>nsbRetxQ</b>
Number of packets in retransmission queue.

<b>linknsbRetxQ</b>
Number of packets in retransmission queue for linked connection.

<b>sackblocks</b>
Number of sack blocks attached to the connection.

<b>linksackblocks</b>
Number of sack blocks attached in linked connection.

<b>congstate</b>
TCP congestion state.

<b>linkcongstate</b>
TCP congestion state for a linked connection.

<b>sndrecoverle</b>
Sequence Number denoting end of fast recovery.

<b>linksndrecoverle</b>
Sequence Number denoting end of fast recovery for linked connection.

<b>creditsInBytes</b>
Connections current credits in Bytes/ms.

<b>linkcredits</b>
Link connections current credits in Bytes/ms.

<b>rateInBytes</b>
Connections current rate in Bytes/ms

<b>linkrateInBytes</b>
Link connections current rate in Bytes/ms

<b>rateSchedulerQueue</b>
Bytes that are queued in the rate scheduler for this connection

<b>linkrateSchedulerQueue</b>
Bytes that are queued in the rate scheduler for link connection

<b>burstRateControl</b>
TCP Burst Rate Control DISABLED/FIXED/DYNAMIC.

<b>linkburstRateControl</b>
TCP Burst Rate Control DISABLED/FIXED/DYNAMIC.

<b>devno</b>

<b>stateflag</b>



