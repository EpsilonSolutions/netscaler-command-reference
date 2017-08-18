#protocol mptcp

The following operations can be performed on "protocol mptcp":


##stat protocol mptcp

Displays statistics of the MPTCP protocol.


##Synopsys

stat protocol mptcp [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>MPTCP sessions created (TotSess)</b>
MPTCP total sessions created

<b>Subflow connections created (subCon)</b>
MPTCP total Subflow connections created

<b>Current MPTCP sessions</b>
The number of current mptcp sessions.

<b>Current Subflow connections</b>
The number of current mptcp subflow connections.

<b>Pending subflow connections</b>
The number of current mptcp subflow connections in pending state.

<b>Sessions without any subflows</b>
Current Multipath TCP sessions without any subflows

<b>MP_CAPABLE SYN received (MPSYN)</b>
MPTCP total MP_CAPABLE received

<b>MP_CAPABLE sessions steered (ConSter)</b>
Total MP_CAPABLE sessions steered

<b>MP_CAPABLE sessions created (ConReq)</b>
Total MP_CAPABLE sessions created.

<b>MP_CAPABLE SYN/ACKs sent (SYNACK)</b>
Total number of MP_CAPABLE SYN/ACKs sent.

<b>MP_CAPABLE Final ACKs (FinalACK)</b>
Total number of MP_CAPABLE Final ACKs received.

<b>MP_JOIN SYN received (JoinSYN)</b>
MPTCP total MP_JOIN syn received

<b>MP_JOIN subflows steered (SFsteer)</b>
Total MP_JOIN subflows steered

<b>MP_JOIN SYN/ACKs sent (SFsynack)</b>
Total MP_JOIN SYN/ACKs sent.

<b>MP_JOIN Final ACKs (SFFACK)</b>
Total number of MP_JOIN Final ACKs

<b>MP_JOIN Final ACK validated (FACKVald)</b>
Total number of Subflow final ACK from peer in 3 way handshake validated with 4th ACK.

<b>Established subflows replaced (TotSFRep)</b>
MPTCP Total established subflows replaced due to new MP_JOIN.

<b>Pending subflows replaced (PendRep)</b>
MPTCP Total pending subflows replaced due to new MP_JOIN.

<b>Fresh ACK on subflow (SFfrhACK)</b>
Fresh ACK recieved on a subflow

<b>Fallback to TCP on plain ACK (TotFB)</b>
MPTCP Fallback to regular tcp on receiving plain ACK for DSS.

<b>Infinite map set (InfSet)</b>
MPTCP Received and set infinite map and fallen back to regular TCP.

<b>Addresses removed with REMOVE_ADDR (REMAddr)</b>
Total number of addresses removed from MPTCP connection with REMOVE_ADDR option

<b>DSS(Data Sequence Signal) packets (TotDSS)</b>
Total number of Data Sequence Signal packets.

<b>DSS received (DSSrcv)</b>
MPTCP Total Data Sequence Signal packets received.

<b>DSS sent (DSSsnd)</b>
MMPTCP Total Data Sequence Signal packets sent

<b>DSS with DATA_ACK (DSSA)</b>
Total Data Sequence Signal packets during data transfer with DATA_ACK

<b>DSS with 8 octet DATA_ACK (DSSa)</b>
Total Data Sequence Signal packets during data transfer with 8 octet DATA_ACK

<b>DSS with Fresh ACK (FreshAck)</b>
MPTCP total Data Sequence Signal packets during  data transfer with fresh ACK

<b>DSS with Sequence Map (SeqMapM)</b>
MPTCP total data Sequence Signal packets with Data Sequence Mapping and checksum

<b>DSS with 8 octet Sequence Map (SeqMapm)</b>
MPTCP total data Sequence Signal packets with 8 octet Data Sequence Mapping and checksum

<b>DSS with infinite map flag (InfMapFg)</b>
MPTCP received Data Sequence Signal with  infinite map flag (Fallback to regular TCP).

<b>Map amount of data not received (LDataLen)</b>
MPTCP Map amount of data not yet received.

<b>Subflow used as backup path (PrioBkup)</b>
MPTCP Subflow used as backup path.

<b>Clear backup subflow(MP_PRIO) (ClrBkup)</b>
Subflow earlier used only as a backup subflow, changes to regular subflow with MP_PRIO option

<b>MP_CAPABLE DATA_FIN sent (TxFin)</b>
Total MPTCP connection close requests sent

<b>MP_CAPABLE DATA_FIN received (RxFin)</b>
Total MPTCP connection close(DATA_FIN) requests received.

<b>Subflow FIN (SfFin)</b>
MPTCP total subflow close requests.

<b>Invalid cookie in MP_CAPABLE ACK (CookieEr)</b>
MPTCP invalid cookie received on MP_CAPABLE final ACK.

<b>MP_CAPABLE Extension flag set (ExtnFlEr)</b>
Extension flag is set on MP_CAPABLE request.

<b>MP_CAPABLE Reserved flag set (ResFlgEr)</b>
MPTCP One or more reserved bits are set on MP_CAPABLE request.

<b>Invalid token in MP_JOIN Request (TokenEr)</b>
MPTCP invalid token received on MP_JOIN request.

<b>MP_JOIN on existing address id (AddrIdEr)</b>
MPTCP MP_JOIN request on existing address id.

<b>MP_JOIN request with addr id 0 (addridEr)</b>
MPTCP MP_JOIN request on address id 0.

<b>MP_JOIN after Maximum subflows (MaxsfEr)</b>
MPTCP new MP_JOIN request after maximum configured subflows are established.

<b>MP_JOIN Threshold limit reached (JoinThEr)</b>
MPTCP Global pending MP_JOIN threshold limit is reached, new MP_JOIN request will be dropped sending RST

<b>MP_JOIN request after fallback (FBJoinEr)</b>
MPTCP New MP_JOIN request received after fallback to regular tcp.

<b>Invalid MAC in MP_JOIN (InMACEr)</b>
MPTCP invalid MAC on MP_JOIN final ACK.

<b>Invalid MPTCP option received (OPTEr)</b>
MPTCP invalid mptcp option is received and is dropped.

<b>Invalid subtype in option (SubtypEr)</b>
Invalid subtype in MPTCP option field and hence discarded.

<b>Option on nonexistent session (OptSesEr)</b>
MPTCP options sent on non existing connection/subflow PCBs.

<b>Invalid remove address ID (REMEr)</b>
MPTCP remove address request received on invalid/unknown address id.

<b>RST on bad options (OptRstEr)</b>
MPTCP sent RST on receiving improper option field.

<b>Remove self address (RemSlfEr)</b>
MPTCP remove address request for self address.

<b>Add RSS filter failed (RssfEr)</b>
Add RSS filter to steer traffic to right node on established MPTCP session failed.

<b>No Payload length (LenEr)</b>
MPTCP Payload length not specified in packet.

<b>Unsupported MSS negotiated (MSSErr)</b>
MPTCP Unsupported MSS negotiated error.

<b>MPTCP Checksum failure (CksumEr)</b>
MPTCP checksum failed. Connection will fallback to regular tcp.

<b>Client crypto algo not supported (CryptoEr)</b>
MPTCP client crypto algorithm not supported.

<b>Client version not supported (VerEr)</b>
MPTCP MP_CAPABLE request from unsupported mptcp client.

<b>RST subflow on plain ACK (TotPArst)</b>
MPTCP Sent RST on receiving plain ACK for DSS.

<b>DATA_FIN on passive subflow (DFpasveEr)</b>
MPTCP Data FIN received on passive subflow

<b>Total FAST_CLOSE sent (FCSentEr)</b>
MPTCP FAST CLOSE sent.

<b>FAST_CLOSE on passive subflow (FCpasvEr)</b>
MPTCP Fast close received on passive subflow.

<b>FAST_CLOSE received (FCRcvEr)</b>
MPTCP FAST_CLOSE received on a subflow.

<b>FAST_CLOSE with invalid key (FCkeyEr)</b>
MPTCP FAST_CLOSE received with invalid key and the packet is dropped.

<b>MP_FAIL sent (MPFAILst)</b>
MPTCP Total MP_FAIL sent due to checksum failure.

<b>MP_FAIL received (MPFAILrv)</b>
MPTCP Total MP_FAIL received and fallback to regular TCP.

<b>Packet without Sequence mapping (NomapEr)</b>
MPTCP Packet received with no Data Sequence Mapping.

<b>More data than Sequence mapping (MrDataEr)</b>
MPTCP More data received than the available Data Sequence Mapping.

<b>Invalid Sequence Map (InMapEr)</b>
MPTCP Drop the session incase of invalid Data Sequence map.

<b>Duplicate Sequence Map (DupmapEr)</b>
MPTCP Duplicate maps in Data Sequence map table.

<b>Invalid subflow sequence (SfnEr)</b>
MPTCP subflow map doesn't exactly match MPTCP session mapping.

<b>Received bad sequence map (BadMapEr)</b>
MPTCP sequence map already exists.

<b>Retransmitted Data Recevied (RetxEr)</b>
Retransmitted Data Recevied on MPTCP session.

<b>Subflow MEM ALLOC Fail (SfMemEr)</b>
Attaching the subflow to MPTCP session failed due to failure in allocating memory to subflow map table.

<b>Session MEM ALLOC Fail (SesMemEr)</b>
Creating a MPTCP connection failed due to failure in allocating memory to MPTCP connection management structure.

<b>Subflow connection ALLOC Fail (SfPcbEr)</b>
Allocating memory to TCP protocol control block(PCB) for subflow failed.

<b>Session connection ALLOC Fail (MpcbEr)</b>
Allocating memory to MPTCP protocol control block failed.

<b>Output packet MEM ALLOC Fail (PktMemEr)</b>
Failed to allocate memory to output MPTCP packet.

<b>Output packet without subflow (PktSfEr)</b>
MPTCP output a packet without any subflow PCB.



##Related Commands

<ul><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol tcp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol http</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol ipv6</a></li><li><a href="../../../.html#stat-protocol-i/.html#stat-protocol-i">stat protocol icmpv6</a></li><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol udp</a></li></ul>



