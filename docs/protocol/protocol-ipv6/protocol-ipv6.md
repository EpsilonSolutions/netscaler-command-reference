#protocol ipv6

The following operations can be performed on "protocol ipv6":


##stat protocol ipv6

Displays statistics of the IPv6 protocol.


##Synopsys

stat protocol ipv6 [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>IPv6 packets received (ipv6RxPkts)</b>
IPv6 packets received.

<b>IPv6 bytes received (ipv6RxBytes)</b>
Bytes of IPv6 data received.

<b>IPv6 packets transmitted (ipv6TxPkts)</b>
IPv6 packets transmitted

<b>IPv6 bytes transmitted (ipv6TxBytes)</b>
Bytes of IPv6 data transmitted.

<b>Total Routed IPv6 packets (ipv6RoutePkts)</b>
IPv6 packets routed.

<b>Total Routed IPv6 Mbits (ipv6RouteMbits)</b>
IPv6 total Mbits.

<b>IPv6 Fragments received. (ipv6FragRxPkts)</b>
IPv6 fragments received.

<b>TCP Fragments reassembled. (ipv6FragTcpReass)</b>
TCP fragments processed after reassembly.

<b>UDP Fragments reassembled. (ipv6FragUdpReass)</b>
UDP fragments processed after reassembly.

<b>IPv6 Fragments processed without reassembly. (ipv6FragPktsProcessNoReass)</b>
IPv6 fragments processed without reassembly.

<b>IPv6 Fragments bridged. (ipv6FragPktsForward)</b>
IPv6 fragments forwarded to the client or server without reassembly.

<b>IPv6 error hdr packets  (RxErrHdr)</b>
Packets received that contain an error in one or more components of the IPv6 header.

<b>IPv6 unsupported next header (Errnxthdr)</b>
Packets received that contain an unsupported next header. The supported next headers are TCP, ICMP, UDP, OSPF, and FRAGMENT.

<b>IPv6 Land-attacks (land attack)</b>
Land-attack packets received. The source and destination addresses are the same. If not dropped, these packets can lock up the appliance.

<b>Reassembled data too big (AssembledPktTooBig)</b>
Packets received for which the reassembled data exceeds the Ethernet packet data length of 1500 bytes.

<b>Zero fragment length received (ZeroLenFramentedPkt)</b>
Packets received with a fragment length of 0 bytes.

<b>ICMPv6 NA packets received</b>
Number of ICMPv6 NA packets received by NetScaler (OBSOLETE).

<b>ICMPv6 NS packets received</b>
Number of ICMPv6 NS packets received by NetScaler (OBSOLETE).

<b>ICMPv6 NA packets transmitted</b>
Number of ICMPv6 NA packets transmitted by NetScaler (OBSOLETE).

<b>ICMPv6 NS packets transmitted</b>
Number of ICMPv6 NS packets transmitted by NetScaler (OBSOLETE).

<b>ICMPv6 RA packets received</b>
Number of ICMPv6 RA packets received by NetScaler (OBSOLETE).

<b>ICMPv6 RS packets transmitted</b>
Number of ICMPv6 RS packets transmitted by NetScaler (OBSOLETE).

<b>ICMPv6 packets received</b>
Number of ICMPv6 packets received by NetScaler (OBSOLETE).

<b>ICMPv6 packets transmitted</b>
Number of ICMPv6 packets transmitted by NetScaler (OBSOLETE).

<b>IPv6 error hdr packets</b>
Number of erroneous header packets received (OBSOLETE).

<b>IPv6 error packets</b>
Number of erroneous packets received (OBSOLETE).

<b>IPv6 bad checksum</b>
Number of bad checksum packets received (OBSOLETE).

<b>ICMPv6 error packets</b>
Number of erroneous ICMPv6 packets received (OBSOLETE).

<b>unsupported ICMPv6 packets</b>
Number of ICMPv6 unsupported packets received (OBSOLETE).

<b>Rate threshold exceeded packets</b>
Number of ICMPv6 packets dropped for rate threshold exceeded (OBSOLETE).



##Related Commands

<ul><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol tcp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol http</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../.html#stat-protocol-i/.html#stat-protocol-i">stat protocol icmpv6</a></li><li><a href="../../../l#stat-protoc/l#stat-protoc">stat protocol ip</a></li><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol udp</a></li></ul>



