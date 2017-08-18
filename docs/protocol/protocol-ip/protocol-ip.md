#protocol ip

The following operations can be performed on "protocol ip":


##stat protocol ip

Displays statistics of the IP protocol.


##Synopsys

stat protocol ip [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>IP packets received (IPPktRx)</b>
IP packets received.

<b>IP bytes received (IPbRx)</b>
Bytes of IP data received.

<b>IP packets transmitted (IPPktTx)</b>
IP packets transmitted.

<b>IP bytes transmitted (IPbTx)</b>
Bytes of IP data transmitted.

<b>Megabits received (IPMbRx)</b>
Megabits of IP data received.

<b>Megabits transmitted (IPMbTx)</b>
Megabits of IP data transmitted.

<b>Total routed IP packets (IPRoutedPkts)</b>
Total routed packets.

<b>Total routed IP Mbits (IPRoutedMbits)</b>
Total routed Mbits

<b>IP fragments received (IPFragRx)</b>
IP fragments received.

<b>Successful reassembly (reasSucc)</b>
Fragmented IP packets successfully reassembled on the NetScaler.

<b>Reassembly attempted (reasAtmp)</b>
IP packets that the NetScaler attempts to reassemble. If one of the fragments is missing, the whole packet is dropped.

<b>IP address lookups (IpLkUp)</b>
IP address lookups performed by the NetScaler. When a packet is received on a non-established session, the NetScaler checks if the destination IP address is one of the NetScaler owned IP addresses.

<b>IP address lookup failure (IpLkFail)</b>
IP address lookups performed by the NetScaler that have failed because the destination IP address of the packet does not match any of the NetScaler owned IP addresses.

<b>UDP fragments forwarded (udpFgFwd)</b>
UDP fragments forwarded to the client or the server.

<b>TCP fragments forwarded (tcpFgFwd)</b>
TCP fragments forwarded to the client or the server.

<b>Fragmentation packets created (frgPktCr)</b>
Fragmented packets created by the NetScaler.

<b>Bad IP checksums (badCksum)</b>
Packets received with an IP checksum error.

<b>Unsuccessful reassembly (reasFail)</b>
Packets received that could not be reassembled. This can occur when there is a checksum failure, an identification field mismatch, or when one of the fragments is missing.

<b>Reassembled data too big (reasBig)</b>
Packets received for which the reassembled data exceeds the Ethernet packet data length of 1500 bytes.

<b>Zero fragment length received (zeroLen)</b>
Packets received with a fragment length of 0 bytes.

<b>Duplicate fragments received (dupFrag)</b>
Duplicate IP fragments received. This can occur when the acknowledgement was not received within the expected time.

<b>Out of order fragment received (oooFrag)</b>
Fragments received that are out of order.

<b>Unknown destination received (UnkDst)</b>
Packets received in which the destination IP address was not reachable or not owned by the NetScaler.

<b>Bad Transport (badTran)</b>
Packets received in which the protocol specified in the IP header is unknown to the NetScaler.

<b>VIP down (vipDown)</b>
Packets received for which the VIP is down. This can occur when all the services bound to the VIP are down or the VIP is manually disabled.

<b>Fix header failure (hdrFail)</b>
Packets received that contain an error in one or more components of the IP header.

<b>TTL expired during transit (ttlExp)</b>
Packets for which the time-to-live (TTL) expired during transit. These packets are dropped.

<b>max non-TCP clients (maxClt)</b>
Attempts to open a new connection to a service for which the maximum limit has been exceeded. Default value, 0, applies no limit.

<b>Unknown services (UnkSvc)</b>
Packets received on a port or service that is not configured.

<b>land-attacks (LndAtk)</b>
Land-attack packets received. The source and destination addresses are the same.

<b>Invalid IP header size (errHdrSz)</b>
Packets received in which an invalid data length is specified, or the value in the length field and the actual data length do not match. The range for the Ethernet packet data length is 0-1500 bytes.

<b>Invalid IP packet size (errPktLen)</b>
Total number of packets received by NetScaler with invalid IP packet size.

<b>Truncated IP packet (trIP)</b>
Truncated IP packets received. An overflow in the routers along the path can truncate IP packets.

<b>Truncated non-IP packet (trNonIp)</b>
Truncated non-IP packets received.

<b>ZERO next hop (zrNxtHop)</b>
Packets received that contain a 0 value in the next hop field. These packets are dropped.

<b>Packets with len > 1514 rcvd (BadLenTx)</b>
Packets received with a length greater than the normal maximum transmission unit of 1514 bytes.

<b>Packets with bad MAC sent (BadMacTx)</b>
IP packets transmitted with a bad MAC address.



##Related Commands

<ul><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol tcp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol http</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol ipv6</a></li><li><a href="../../../.html#stat-protocol-i/.html#stat-protocol-i">stat protocol icmpv6</a></li><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol udp</a></li><li><a href="../../../html#stat-protocol-/html#stat-protocol-">stat protocol mptcp</a></li></ul>



