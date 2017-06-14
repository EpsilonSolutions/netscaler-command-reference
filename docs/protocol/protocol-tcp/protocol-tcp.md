#protocol tcp

The following operations can be performed on "protocol tcp":


##stat protocol tcp

Displays statistics of the TCP protocol.


##Synopsys

stat protocol tcp [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Server active connections (ActSvrCo)</b>
Connections to a server currently responding to requests.

<b>Opening server connections (SvrCxO)</b>
Server connections in the Opening state, which indicates that the handshakes are not yet complete.

<b>Opening client connections (CltCxO)</b>
Client connections in the Opening state, which indicates that the handshakes are not yet complete.

<b>Established client connections (CltCxE)</b>
Current client connections in the Established state, which indicates that data transfer can occur between the NetScaler and the client.

<b>Established server connections (SvrCxE)</b>
Current server connections in the Established state, which indicates that data transfer can occur between the NetScaler and the server.

<b>TCP packets received (TCPPktRx)</b>
TCP packets received.

<b>TCP bytes received (TCPbRx)</b>
Bytes of TCP data received.

<b>TCP packets transmitted (TCPPktTx)</b>
TCP packets transmitted.

<b>TCP bytes transmitted (TCPbTx)</b>
Bytes of TCP data transmitted.

<b>All client connections (CltCx)</b>
Client connections, including connections in the Opening, Established, and Closing state.

<b>Closing client connections (CltCxCl)</b>
Client connections in the Closing state, which indicates that the connection termination process has initiated but is not complete.

<b>Opened client connections (TotCltO)</b>
Client connections opened by the NetScaler since startup (after three-way handshake). This counter is reset when the NetScaler is restarted.

<b>All server connections (SvrCx)</b>
Server connections, including connections in the Opening, Established, and Closing state.

<b>Closing server connections (SvrCxCl)</b>
Server connections in the Closing state, which indicates that the connection termination process has initiated but is not complete.

<b>Opened server connections (TotSvrO)</b>
Server connections initiated by the NetScaler since startup. This counter is reset when the NetScaler is restarted.

<b>Surge queue (SQlen)</b>
Connections in the surge queue. When the NetScaler cannot open a connection to the server, for example when maximum connections have been reached, the NetScaler queues these requests.

<b>Spare connections (SpConn)</b>
Spare connections available. To save time and resources in establishing another connection for a new client, the connection on the server is not closed after completing the request from the first client and is available for serving future requests.

<b>Client idle flushed (ZomCltF)</b>
Client connections that are flushed because the client has been idle for some time.

<b>Client half opened flushed (ZCltFHo)</b>
Half-opened client connections that are flushed because the three-way handshakes are not complete.

<b>Client active half closed flushed (ZCltFAhc)</b>
Active half-closed client connections that are flushed because the client has closed the connection and there has been no activity on the connection.

<b>Client passive half closed flushed (ZCltFPhc)</b>
Passive half-closed client connections that are flushed because the NetScaler has closed the connection and there has been no activity on the connection.

<b>Server idle connections flushed (ZSvrF)</b>
Server connections that are flushed because there have been no client requests in the queue for some time.

<b>Server half opened flushed (ZSvrFHo)</b>
Half-opened server connections that are flushed because the three-way handshakes are not complete.

<b>Server active half closed flushed (ZSvrFAhc)</b>
Active half-closed server connections that are flushed because the server has closed the connection and there has been no activity on the connection.

<b>Server passive half closed flushed (ZSrvFPhc)</b>
Passive half-closed server connections that are flushed because the NetScaler has closed the connection and there has been no activity on the connection.

<b>Zombie cleanup calls (ZmbCall)</b>
Times the Zombie cleanup function is called. Every time a connection is flushed, it is marked for cleanup. The Zombie cleanup function clears all these connections at predefined intervals.

<b>SYN packets received (TCPSYN)</b>
SYN packets received

<b>Server probes (SYNProbe)</b>
Probes from the NetScaler to a server. The NetScaler sends a SYN packet to the server to check its availability and expects a SYN_ACK packet from the server before a specified response timeout.

<b>FIN packets from server (SvrFin)</b>
FIN packets received from the server.

<b>FIN packets from client (CltFin)</b>
FIN packets received from the clients.

<b>Time wait to SYN (WaToSyn)</b>
SYN packets (packets used to initiate a TCP connection) received on connections that are in the TIME_WAIT state. Packets cannot be transferred on a connection in this state.

<b>Data in TIME_WAIT (WaDat)</b>
Bytes of data received on connections that are in the TIME_WAIT state. Data cannot be transferred on a connection that is in this state.

<b>SYN packets held (SYNHeld)</b>
SYN packets held on the NetScaler that are waiting for a server connection.

<b>SYN packets flushed (SYNFlush)</b>
SYN packets flushed on the NetScaler because of no response from the server for three or more seconds.

<b>TIME_WAIT connections closed (FinWaitC)</b>
Connections closed on the NetScaler because the number of connections in the TIME_WAIT state has exceeded the default value of 7000.

<b>Bad TCP checksum (TCPBadCk)</b>
Packets received with a TCP checksum error.

<b>Data after FIN (TCPDtFin)</b>
Packets received following a connection termination request. This error is usually caused by a reordering of packets during transmission.

<b>SYN in SYN_RCVD state (TCPSYNRv)</b>
SYN packets received on a connection that is in the SYN_RCVD state. A connection goes into the SYN_RCVD state after receiving a SYN packet.

<b>SYN in ESTABLISHED state (TCPSYNEs)</b>
SYN packets received on a connection that is in the ESTABLISHED state. A SYN packet is not expected on an ESTABLISHED connection.

<b>SYN_SENT incorrect ACK packet (TCPBadAk)</b>
Incorrect ACK packets received on a connection that is in the SYN_SENT state. An incorrect ACK packet is the third packet in the three-way handshake that has an incorrect sequence number.

<b>RST packets received (TCPRST)</b>
Reset packets received from a client or a server.

<b>RST on not ESTABLISHED (TCPRSTNE)</b>
Reset packets received on a connection that is not in the ESTABLISHED state.

<b>RST out of window (TCPRSTOW)</b>
Reset packets received on a connection that is out of the current TCP window.

<b>RST in TIME_WAIT (TCPRSTTi)</b>
Reset packets received on a connection that is in the TIME_WAIT state. Packets cannot be transferred on a connection in the TIME_WAIT state.

<b>Server out of order packets (SvrOOO)</b>
Out of order TCP packets received from a server.

<b>Client out of order packets (CltOOO)</b>
Out of order TCP packets received from a client.

<b>TCP hole on client connection (CltHole)</b>
TCP holes created on a client connection. When out of order packets are received from a client, a hole is created on the NetScaler for each group of missing packets.

<b>TCP hole on server connection (SvrHole)</b>
TCP holes created on a server connection. When out of order packets are received from a server, a hole is created on the NetScaler for each group of missing packets.

<b>Seq number SYN cookie reject (CSeqRej)</b>
SYN cookie packets rejected because they contain an incorrect sequence number.

<b>Signature SYN cookie reject (CSigRej)</b>
SYN cookie packets rejected because they contain an incorrect signature.

<b>Seq number SYN cookie drop (CSigDrp)</b>
SYN cookie packets dropped because the sequence number specified in the packets is outside the current window.

<b>MSS SYN cookie reject (CMssRej)</b>
SYN cookie packets rejected because the maximum segment size (MSS) specified in the packets is incorrect.

<b>Any IP port allocation failure (PortFal)</b>
Port allocations that have failed on a mapped IP address because the maximum limit of 65536 has been exceeded.

<b>IP port allocation failure (PortFalI)</b>
Port allocations that have failed on a subnet IP address or vserver IP address because the maximum limit of 65536 has been exceeded.

<b>Stray packets (StrayPkt)</b>
Number of stray or misrouted packets.

<b>RST packets sent (SentRst)</b>
Reset packets sent to a client or a server.

<b>Bad state connections (BadConn)</b>
Connections that are not in a valid TCP state.

<b>RST threshold dropped (RstThre)</b>
Reset packets dropped because the default threshold of 100 resets per 10 milliseconds has been exceeded. This is a configurable value using the set rateControl command.

<b>Packets out of window (OOWPkt)</b>
Packets received that are out of the current advertised window.

<b>SYNs dropped (Congestion) (SynCng)</b>
SYN packets dropped because of network congestion.

<b>Client retransmissions (TCPCltRe)</b>
Packets retransmitted by a client. This usually occurs because the acknowledgement from the NetScaler has not reached the client.

<b>Full packet retransmissions (TCPFulRe)</b>
Full packets retransmitted by the client or the server.

<b>SYN packet retries (TCPSYNRe)</b>
SYN packets resent to a server.

<b>SYN packets timeout (TCPSYNG)</b>
Attempts to establish a connection on the NetScaler that timed out.

<b>TCP retransmission (Retr)</b>
TCP packets retransmitted. The NetScaler attempts to retransmit the packet up to seven times, after which it resets the other half of the TCP connection.

<b>1st retransmission (1stRetr)</b>
Packets retransmitted once by the NetScaler.

<b>3rd retransmission (3rdRetr)</b>
Packets retransmitted three times by the NetScaler.

<b>5th retransmission (5thRetr)</b>
Packets retransmitted five times by the NetScaler.

<b>7th retransmission (7thRetr)</b>
Packets retransmitted seven times by the NetScaler. If this fails, the NetScaler terminates the connection.

<b>Fast retransmits (FastRetr)</b>
TCP packets on which the NetScaler performs a fast retransmission in response to three duplicate acknowledgements or a partial acknowledgement.  The NetScaler assumes that the packet is lost and retransmits the packet before its time-out.

<b>Server retransmissions (TCPSvrRe)</b>
Packets retransmitted by a server. This usually occurs because the acknowledgement from the NetScaler has not reached the server.

<b>Partial packet retransmissions (TCPParRe)</b>
Partial packet retransmits by a client or server due to congestion on the connection. This usually occurs because the window advertised by the NetScaler is not big enough to hold the full packet.

<b>FIN packet retries (TCPFINRe)</b>
FIN packets resent to a server or a client.

<b>FIN packets timeout (TCPFING)</b>
Connections that were timed out by the NetScaler because of not receiving the ACK packet after retransmitting the FIN packet four times.

<b>2nd retransmission (2ndRetr)</b>
Packets retransmitted twice by the NetScaler.

<b>4th retransmission (4thRetr)</b>
Packets retransmitted four times by the NetScaler.

<b>6th retransmission (6thRetr)</b>
Packets retransmitted six times by the NetScaler.

<b>TCP retransmission giveup (RetrG)</b>
Number of times NetScaler terminates a connection after retransmitting the packet seven times on that connection.Retrasnmission happens when recieving end doesn't acknowledges the packet.

<b>TCP level cip failure (CltHdrEr)</b>
Number of times TCP level client header insertion failure



##Related Commands

<ul><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol http</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol ipv6</a></li><li><a href="../../../.html#stat-protocol-i/.html#stat-protocol-i">stat protocol icmpv6</a></li><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol udp</a></li></ul>



