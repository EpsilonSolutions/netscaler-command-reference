#nstrace

The following operations can be performed on "nstrace":


##nstrace

Invokes the nstrace program to log traffic flowing through the NetScaler appliance.


##Synopsys

nstrace [-nf &lt;positive_integer>] [-time &lt;secs>] [-size &lt;positive_integer>] [-mode &lt;mode> ...] [-tcpdump ( ENABLED | DISABLED )  [-perNIC ( ENABLED | DISABLED )]] [-name &lt;string>  [-id &lt;string>]] [-filter &lt;expression>  [-link ( ENABLED | DISABLED )]]


##Arguments

<b>h</b>
prints this message - exclusive option

<b>nf</b>
Number of files to be generated in a single run of the command.
Default value: 24

<b>time</b>
Number of seconds for which to log to trace file. Can be a mathematical expression. For example, to log to trace files for 2 hours, you can specify 2*60*60.
Default value: 3600

<b>size</b>
Size of the packet to be logged (should be in the range of 60 to 1514 bytes). Set to 0 for full packet trace.
Default value: 164
Maximum value: 1514

<b>m</b>
Capturing mode: sum of the values:
						1 - Transmitted packets (TX)
						2 - Packets buffered for transmission (TXB)
						4 - Received packets (RX)
Default value: 6

<b>tcpDump</b>
Log files in TCP dump format (instead of nstrace format).
Possible values: NSTRACE, TCPDUMP

<b>mode</b>
Capturing mode for trace. Can be any of the following values, or a combination of  these values:
* RX - Received packets before NIC pipelining
* NEW_RX - Received packets after NIC pipelining (packets that are not dropped)
* TX - Transmitted packets
* TXB - Packets buffered for transmission
* IPV6 - Translated IPv6 packets
* C2C - Capture core-to-core messages
* NS_FR_TX - Flow receiver does not capture the TX/TXB packets. Applicable only for a cluster setup.
You can also provide a combination of modes. For example:
* -mode NEW_RX TXB: Capture RX packets after NIC handling and packets that are buffered for actual transmission.
* -mode RX TX: Capture packet during NIC pipeline (filter expressions will not work for RX mode).
* -mode NEW_RX TXB NS_FR_TX: Default mode except that TX/TXB packets on the flow receiver are not captured.
Default value: DEFAULT_MODE

<b>tcpdump</b>
Log files format supported:nstrace-format, tcpdump-format. default:nstrace-format
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>name</b>
Custom file name for nstrace files.

<b>filter</b>
Filter expression for nstrace. Maximum length of filter is 255 and it can be of the following format:
"&lt;expression&gt; [&lt;relop&gt; &lt;expression&gt;"]
where,
&lt;relop&gt; can be the && or the || relational operators.
&lt;expression&gt; is a string in the following format: &lt;qualifier&gt; &lt;operator&gt; &lt;qualifier-value&gt;
where, 
&lt;operator&gt; can be any one of the following (except the commas): ==, eq, !=, neq, &gt;, gt, &lt;, lt, &gt;=, ge, &lt;=, le, BETWEEN
Following are the valid qualifiers for the command: SOURCEIP, SOURCEPORT, DESTIP, DESTPORT, IP, PORT, SVCNAME, VSVRNAME, CONNID, VLAN, INTF.
Example: 
nstrace -filter "SOURCEIP==10.102.34.201 || SVCNAME !=s1 && SOURCEPORT &gt;80"



##Example

nstrace -nf 10 -time 100 -mode RX IPV6 TXB -name abc -tcpdump ENABLED -perNIC ENABLED

