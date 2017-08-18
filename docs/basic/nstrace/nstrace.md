#nstrace

The following operations can be performed on "nstrace":


[start](#start-nstrace) | [stop](#stop-nstrace) | [dump](#dump-nstrace) | [show](#show-nstrace)

##start nstrace

Start NetScaler packet capture tool. There should be at least 2 GB of free disk space for trace to start


##Synopsys

start nstrace [-nf &lt;positive_integer>] [-time &lt;positive_integer>] [-size &lt;positive_integer>] [-mode &lt;mode> ...] [-perNIC ( ENABLED | DISABLED )] [-fileName &lt;string>] [-fileId &lt;string>] [-filter &lt;expression>] [-link ( ENABLED | DISABLED )] [-nodes &lt;positive_integer> ...] [-filesize &lt;positive_integer>] [-traceformat ( NSCAP | PCAP )] [-merge &lt;merge>] [-doruntimecleanup ( ENABLED | DISABLED )] [-traceBuffers &lt;positive_integer>] [-skipRPC ( ENABLED | DISABLED )] [-skipLocalSSH ( ENABLED | DISABLED )] [-capsslkeys ( ENABLED | DISABLED )] [-capdroppkt ( ENABLED | DISABLED )] [-inMemoryTrace ( ENABLED | DISABLED )]


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
Minimum value: 0
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
      MPTCP       MPTCP master flow
      Default mode: NEW_RX TXB 
Default value: DEFAULT_MODE

<b>perNIC</b>
Use separate trace files for each interface. Works only with cap format.
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
        SVC_MYSQL | SVC_MSSQL | FIX | SSL_FIX | SERVICE_UNKNOWN )
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
Minimum value: 0
Maximum value: 32

<b>filesize</b>
File size, in MB, treshold for rollover. If free disk space is less than 2GB at the time of rollover, trace will stop
Default value: 1024
Minimum value: 0
Maximum value: 10240

<b>traceformat</b>
Format in which trace will be generated
Possible values: NSCAP, PCAP
Default value: 0

<b>merge</b>
Specify how traces across PE's are merged
Possible values: ONSTOP, ONTHEFLY, NOMERGE
Default value: 0

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

<b>skipLocalSSH</b>
skip local SSH packets
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>capsslkeys</b>
Capture SSL Master keys. Master keys will not be captured on FIPS machine.
                Warning: The captured keys can be used to decrypt information that may be confidential. The captured key files have to be stored in a secure environment
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>capdroppkt</b>
Captures Dropped Packets if set to ENABLED.
Possible values: ENABLED, DISABLED
Default value: ENABLED

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
      MPTCP       MPTCP master flow
      Default mode: NEW_RX TXB

<b>traceformat</b>
Format in which trace will be generated

<b>perNIC</b>
Use separate trace files for each interface. Works only with cap format.

<b>fileName</b>
Name of the trace file.

<b>fileId</b>
ID for the trace file name for uniqueness. Should be used only with -name option.

<b>filter</b>
Filter expression for nstrace. Maximum length of filter is 255 and it can be of following format:
     &lt;expression> [&lt;relop> &lt;expression>]
     &lt;relop> = ( && | || )
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
        SVC_MYSQL | SVC_MSSQL | FIX | SSL_FIX | SERVICE_UNKNOWN )
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

<b>merge</b>
Specify how traces across PE's are merged

<b>doruntimecleanup</b>
Enable or disable runtime temp file cleanup

<b>traceBuffers</b>
Number of 16KB trace buffers

<b>skipRPC</b>
skip RPC packets

<b>skipLocalSSH</b>
skip local SSH packets

<b>capsslkeys</b>
Capture SSL Master keys. Master keys will not be captured on FIPS machine.
                Warning: The captured keys can be used to decrypt information that may be confidential. The captured key files have to be stored in a secure environment

<b>capdroppkt</b>
Captures Dropped Packets if set to ENABLED.

<b>inMemoryTrace</b>
Logs packets in appliance's memory and dumps the trace file on stopping the nstrace operation



##Example

show nstrace

