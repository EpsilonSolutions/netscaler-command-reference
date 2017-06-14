#nstrace

The following operations can be performed on "nstrace":


[start](#start-nstrace) | [stop](#stop-nstrace) | [dump](#dump-nstrace) | [show](#show-nstrace)

##start nstrace

Start NetScaler packet capture tool.


##Synopsys

start nstrace [-nf &lt;positive_integer>] [-time &lt;positive_integer>] [-size &lt;positive_integer>] [-mode &lt;mode> ...] [-tcpdump ( ENABLED | DISABLED )] [-perNIC ( ENABLED | DISABLED )] [-fileName &lt;string>] [-fileId &lt;string>] [-filter &lt;expression>] [-link ( ENABLED | DISABLED )] [-nodes &lt;positive_integer> ...] [-doruntimemerge ( ENABLED | DISABLED )] [-doruntimecleanup ( ENABLED | DISABLED )] [-traceBuffers &lt;positive_integer>] [-skipRPC ( ENABLED | DISABLED )] [-inMemoryTrace ( ENABLED | DISABLED )]


##Arguments

<b>nf</b>
Number of files to be generated in cycle.
Default value: 24
Minimum value: 1
Maximum value: 100

<b>time</b>
Time per file (sec).
Default value: 3600
Minimum value: 1

<b>size</b>
Size of the captured data. Set 0 for full packet trace.
Default value: 164
Maximum value: 1514

<b>mode</b>
Capturing mode for trace. Mode can be any of the following values or combination of these values:
      RX          Received packets before NIC pipelining (Filter does not work when RX capturing mode is ON)
      NEW_RX      Received packets after NIC pipelining
      TX          Transmitted packets
      TXB         Packets buffered for transmission
      IPV6        Translated IPv6 packets
      C2C         Capture C2C message
      NS_FR_TX    TX/TXB packets are not captured in flow receiver.
      Default mode: NEW_RX TXB 
Default value: DEFAULT_MODE

<b>tcpdump</b>
Trace is captured in TCPDUMP(.pcap) format. Default capture format is NSTRACE(.cap).
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>perNIC</b>
Use separate trace files for each interface. Works only with tcpdump format.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>fileName</b>
Name of the trace file.

<b>fileId</b>
ID for the trace file name for uniqueness. Should be used only with -name option.

<b>filter</b>
Filter expression for nstrace. Maximum length of filter is 255 and it can be of following format:
     &lt;expression&gt; [&lt;relop&gt; &lt;expression&gt;]
     &lt;relop&gt; = ( && | || )
     nstrace supports two types of filter expressions:
     Classic Expressions:
     &lt;expression&gt; = the expression string in the format:
     &lt;qualifier&gt; &lt;operator&gt; &lt;qualifier-value&gt;
     &lt;qualifier&gt; = SOURCEIP.
     &lt;qualifier-value&gt; = A valid IP address
     &lt;qualifier&gt; = SOURCEPORT.
     &lt;qualifier-value&gt; = A valid port number.
     &lt;qualifier&gt; = DESTIP.
     &lt;qualifier-value&gt; = A valid IP address.
     &lt;qualifier&gt; = DESTPORT.
     &lt;qualifier-value&gt; = A valid port number.
     &lt;qualifier&gt; = IP.
     &lt;qualifier-value&gt; = A valid IP address.
     &lt;qualifier&gt; = PORT.
     &lt;qualifier-value&gt; = A valid port number.
     &lt;qualifier&gt; = SVCNAME.
     &lt;qualifier-value&gt; = The name of a service.
     &lt;qualifier&gt; = VSVRNAME.
     &lt;qualifier-value&gt; = The name of a vserver.
     &lt;qualifier&gt; = CONNID
     &lt;qualifier-value&gt; = A valid PCB dev number.
     &lt;qualifier&gt; = VLAN
     &lt;qualifier-value&gt; = A valid VLAN ID.
     &lt;qualifier&gt; = INTF
     &lt;qualifier-value&gt; = A valid interface id in the form of x/y 
                 (n/x/y in case of cluster interface).
     &lt;operator&gt; = ( == | eq | != | neq | &gt; | gt
     | &lt; | lt | &gt;= | ge | &lt;= | le | BETWEEN )
     eg: start nstrace -filter "SOURCEIP == 10.102.34.201 || (SVCNAME != s1 && SOURCEPORT &gt; 80)"
     The filter expression should be given in double quotes.
     Default Expressions:
     &lt;expression&gt; =:
     CONNECTION.&lt;qualifier&gt;.&lt;qualifier-method&gt;.(&lt;qualifier-value&gt;)
     &lt;qualifier&gt; = SRCIP
     &lt;qualifier-method&gt; = [ EQ | NE ]
     &lt;qualifier-value&gt;  = A valid IPv4 address.
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
     &lt;qualifier&gt; = SVCNAME
     &lt;qualifier-method&gt; = [ EQ | NE | CONTAINS | STARTSWITH 
                         | ENDSWITH ] 
     &lt;qualifier-value&gt;  = A valid text string.
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
     &lt;qualifier-value&gt;  =  A valid interface id in the
                    form of x/y.
     example = CONNECTION.INTF.EQ("x/y")
     &lt;qualifier&gt; = SERVICE_TYPE
     &lt;qualifier-method&gt; = [ EQ | NE ]
     &lt;qualifier-value&gt;  = ( SVC_HTTP | FTP | TCP | UDP | SSL |
        SSL_BRIDGE | SSL_TCP | NNTP | RPCSVR | RPCSVRS |
        RPCCLNT | SVC_DNS | ADNS | SNMP | RTSP | DHCPRA | ANY|
        MONITOR | MONITOR_UDP | MONITOR_PING | SIP_UDP |
        SVC_MYSQL | SVC_MSSQL | SERVICE_UNKNOWN )
     example = CONNECTION.SERVICE_TYPE.EQ(ANY)
     &lt;qualifier&gt; = TRAFFIC_DOMAIN_ID
     &lt;qualifier-method&gt; = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value&gt;  = A valid traffic domain ID.
     example = CONNECTION.TRAFFIC_DOMAIN_ID.EQ(0)
     eg: start nstrace -filter "CONNECTION.SRCIP.EQ(127.0.0.1) || (CONNECTION.SVCNAME.NE("s1") && CONNECTION.SRCPORT.EQ(80))"
     The filter expression should be given in double quotes. 
common use cases:
Trace capturing full sized traffic from/to ip 10.102.44.111, excluding loopback traffic
start nstrace -size 0 -filter "CONNECTION.IP.NE(127.0.0.1) && CONNECTION.IP.EQ(10.102.44.111)"
Trace capturing all traffic to (terminating at) port 80 or 443 
start nstrace -size 0 -filter "CONNECTION.DSTPORT.EQ(443) || CONNECTION.DSTPORT.EQ(80)"
Trace capturing all backend traffic specific to service service1 along with corresponding client side traffic
start nstrace -size 0 -filter "CONNECTION.SVCNAME.EQ("service1")" -link ENABLED
Trace capturing all traffic through NS interface 1/1
start nstrace -filter "CONNECTION.INTF.EQ("1/1")"
Trace capturing all traffic specific through vlan 2
start nstrace -filter "CONNECTION.VLANID.EQ(2)"
Trace capturing all frontend (client side) traffic specific to lb vserver vserver1 along with corresponding server side traffic
start nstrace -size 0 -filter "CONNECTION.LB_VSERVER.NAME.EQ("vserver1")" -link ENABLED

<b>link</b>
Includes filtered connection's peer traffic.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nodes</b>
Nodes on which tracing is started.
Maximum value: 32

<b>doruntimemerge</b>
Enable or disable runtime merge.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>doruntimecleanup</b>
Enable or disable runtime temp file cleanup
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>traceBuffers</b>
Number of 16KB trace buffers
Default value: 5000
Minimum value: 1000

<b>skipRPC</b>
skip RPC packets
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>inMemoryTrace</b>
Logs packets in appliance's memory and dumps the trace file on stopping the nstrace operation
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

start nstrace -time 10

##stop nstrace

Stop running NetScaler packet capture tool.


##Synopsys

stop nstrace


##Example

stop nstrace

##dump nstrace

dump records from trace buffers to file.


##Synopsys

dump nstrace -fileName &lt;string>


##Arguments

<b>fileName</b>
Name of the trace file.



##Example

dump nstrace

##show nstrace

Display nstrace parameters set through 'start nstrace' command.


##Synopsys

show nstrace


##Outputs

<b>state</b>
Current running state of trace.

<b>scope</b>
Scope of started trace, local or cluster level.

<b>traceLocation</b>
Directory where current trace files are saved.

<b>nf</b>
Number of files to be generated in cycle.

<b>time</b>
Time per file (sec).

<b>size</b>
Size of the captured data. Set 0 for full packet trace.

<b>mode</b>
Capturing mode for trace. Mode can be any of the following values or combination of these values:
      RX          Received packets before NIC pipelining (Filter does not work when RX capturing mode is ON)
      NEW_RX      Received packets after NIC pipelining
      TX          Transmitted packets
      TXB         Packets buffered for transmission
      IPV6        Translated IPv6 packets
      C2C         Capture C2C message
      NS_FR_TX    TX/TXB packets are not captured in flow receiver.
      Default mode: NEW_RX TXB

<b>tcpdump</b>
Trace is captured in TCPDUMP(.pcap) format. Default capture format is NSTRACE(.cap).

<b>perNIC</b>
Use separate trace files for each interface. Works only with tcpdump format.

<b>fileName</b>
Name of the trace file.

<b>fileId</b>
ID for the trace file name for uniqueness. Should be used only with -name option.

<b>filter</b>
Filter expression for nstrace. Maximum length of filter is 255 and it can be of following format:
     &lt;expression> [&lt;relop> &lt;expression>]
     &lt;relop> = ( && | || )
     nstrace supports two types of filter expressions:
     Classic Expressions:
     &lt;expression> = the expression string in the format:
     &lt;qualifier> &lt;operator> &lt;qualifier-value>
     &lt;qualifier> = SOURCEIP.
     &lt;qualifier-value> = A valid IP address
     &lt;qualifier> = SOURCEPORT.
     &lt;qualifier-value> = A valid port number.
     &lt;qualifier> = DESTIP.
     &lt;qualifier-value> = A valid IP address.
     &lt;qualifier> = DESTPORT.
     &lt;qualifier-value> = A valid port number.
     &lt;qualifier> = IP.
     &lt;qualifier-value> = A valid IP address.
     &lt;qualifier> = PORT.
     &lt;qualifier-value> = A valid port number.
     &lt;qualifier> = SVCNAME.
     &lt;qualifier-value> = The name of a service.
     &lt;qualifier> = VSVRNAME.
     &lt;qualifier-value> = The name of a vserver.
     &lt;qualifier> = CONNID
     &lt;qualifier-value> = A valid PCB dev number.
     &lt;qualifier> = VLAN
     &lt;qualifier-value> = A valid VLAN ID.
     &lt;qualifier> = INTF
     &lt;qualifier-value> = A valid interface id in the form of x/y 
                 (n/x/y in case of cluster interface).
     &lt;operator> = ( == | eq | != | neq | > | gt
     | &lt; | lt | >= | ge | &lt;= | le | BETWEEN )
     eg: start nstrace -filter "SOURCEIP == 10.102.34.201 || (SVCNAME != s1 && SOURCEPORT > 80)"
     The filter expression should be given in double quotes.
     Default Expressions:
     &lt;expression> =:
     CONNECTION.&lt;qualifier>.&lt;qualifier-method>.(&lt;qualifier-value>)
     &lt;qualifier> = SRCIP
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = A valid IPv4 address.
     example = CONNECTION.SRCIP.EQ(127.0.0.1)
     &lt;qualifier> = DSTIP
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = A valid IPv4 address.
     example = CONNECTION.DSTIP.EQ(127.0.0.1)
     &lt;qualifier> = IP
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = A valid IPv4 address.
     example = CONNECTION.IP.EQ(127.0.0.1)
     &lt;qualifier> = SRCIPv6
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = A valid IPv6 address.
     example = CONNECTION.SRCIPv6.EQ(2001:db8:0:0:1::1)
     &lt;qualifier> = DSTIPv6
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = A valid IPv6 address.
     example = CONNECTION.DSTIPv6.EQ(2001:db8:0:0:1::1)
     &lt;qualifier> = IPv6
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = A valid IPv6 address.
     example = CONNECTION.IPv6.EQ(2001:db8:0:0:1::1)
     &lt;qualifier> = SRCPORT
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid port number.
     example = CONNECTION.SRCPORT.EQ(80)
     &lt;qualifier> = DSTPORT
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid port number.
     example = CONNECTION.DSTPORT.EQ(80)
     &lt;qualifier> = PORT
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid port number.
     example = CONNECTION.PORT.EQ(80)
     &lt;qualifier> = VLANID
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid VLAN ID.
     example = CONNECTION.VLANID.EQ(0)
     &lt;qualifier> = CONNID
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid PCB dev number.
     example = CONNECTION.CONNID.EQ(0)
     &lt;qualifier> = PPEID
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid core ID.
       example = CONNECTION.PPEID.EQ(0)    
     &lt;qualifier> = SVCNAME
     &lt;qualifier-method> = [ EQ | NE | CONTAINS | STARTSWITH 
                         | ENDSWITH ] 
     &lt;qualifier-value>  = A valid text string.
     example = CONNECTION.SVCNAME.EQ("name")
     &lt;qualifier> = LB_VSERVER.NAME
     &lt;qualifier-method> = [ EQ | NE | CONTAINS | STARTSWITH
                        | ENDSWITH ]
     &lt;qualifier-value>  = LB vserver name.
     example = CONNECTION.LB_VSERVER.NAME.EQ("name")
     &lt;qualifier> = CS_VSERVER.NAME
     &lt;qualifier-method> = [ EQ | NE | CONTAINS | STARTSWITH
                        | ENDSWITH ]
     &lt;qualifier-value>  = CS vserver name.
     example = CONNECTION.CS_VSERVER.NAME.EQ("name")
     &lt;qualifier> = INTF
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  =  A valid interface id in the
                    form of x/y.
     example = CONNECTION.INTF.EQ("x/y")
     &lt;qualifier> = SERVICE_TYPE
     &lt;qualifier-method> = [ EQ | NE ]
     &lt;qualifier-value>  = ( SVC_HTTP | FTP | TCP | UDP | SSL |
        SSL_BRIDGE | SSL_TCP | NNTP | RPCSVR | RPCSVRS |
        RPCCLNT | SVC_DNS | ADNS | SNMP | RTSP | DHCPRA | ANY|
        MONITOR | MONITOR_UDP | MONITOR_PING | SIP_UDP |
        SVC_MYSQL | SVC_MSSQL | SERVICE_UNKNOWN )
     example = CONNECTION.SERVICE_TYPE.EQ(ANY)
     &lt;qualifier> = TRAFFIC_DOMAIN_ID
     &lt;qualifier-method> = [ EQ | NE | GT | GE | LT | LE
                         | BETWEEN ]
     &lt;qualifier-value>  = A valid traffic domain ID.
     example = CONNECTION.TRAFFIC_DOMAIN_ID.EQ(0)
     eg: start nstrace -filter "CONNECTION.SRCIP.EQ(127.0.0.1) || (CONNECTION.SVCNAME.NE("s1") && CONNECTION.SRCPORT.EQ(80))"
     The filter expression should be given in double quotes. 
common use cases:
Trace capturing full sized traffic from/to ip 10.102.44.111, excluding loopback traffic
start nstrace -size 0 -filter "CONNECTION.IP.NE(127.0.0.1) && CONNECTION.IP.EQ(10.102.44.111)"
Trace capturing all traffic to (terminating at) port 80 or 443 
start nstrace -size 0 -filter "CONNECTION.DSTPORT.EQ(443) || CONNECTION.DSTPORT.EQ(80)"
Trace capturing all backend traffic specific to service service1 along with corresponding client side traffic
start nstrace -size 0 -filter "CONNECTION.SVCNAME.EQ("service1")" -link ENABLED
Trace capturing all traffic through NS interface 1/1
start nstrace -filter "CONNECTION.INTF.EQ("1/1")"
Trace capturing all traffic specific through vlan 2
start nstrace -filter "CONNECTION.VLANID.EQ(2)"
Trace capturing all frontend (client side) traffic specific to lb vserver vserver1 along with corresponding server side traffic
start nstrace -size 0 -filter "CONNECTION.LB_VSERVER.NAME.EQ("vserver1")" -link ENABLED

<b>link</b>
Includes filtered connection's peer traffic.

<b>nodes</b>
Nodes on which tracing is started.

<b>doruntimemerge</b>
Enable or disable runtime merge.

<b>doruntimecleanup</b>
Enable or disable runtime temp file cleanup

<b>traceBuffers</b>
Number of 16KB trace buffers

<b>skipRPC</b>
skip RPC packets

<b>inMemoryTrace</b>
Logs packets in appliance's memory and dumps the trace file on stopping the nstrace operation



##Example

show nstrace

