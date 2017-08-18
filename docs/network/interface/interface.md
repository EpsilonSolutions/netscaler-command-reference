#interface

The following operations can be performed on "interface":


[clear](#clear-interface) | [set](#set-interface) | [unset](#unset-interface) | [enable](#enable-interface) | [disable](#disable-interface) | [reset](#reset-interface) | [show](#show-interface) | [stat](#stat-interface)

##clear interface

Resets the statistical counters of the specified interface.


##Synopsys

clear interface &lt;id>@


##Arguments

<b>id</b>
Interface number, in C/U format, where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
* LA - Indicates a link aggregation port.
* LO - Indicates a loop back port.
U is a unique integer for representing an interface in a particular port group.



##set interface

Modifies the parameters of an interface.


##Synopsys

set interface &lt;id>@ [-speed &lt;speed>] [-duplex &lt;duplex>] [-flowControl &lt;flowControl>] [-autoneg ( DISABLED | ENABLED )] [-haMonitor ( ON | OFF )] [-haHeartbeat ( OFF | ON )] [-mtu &lt;positive_integer>] [-tagall ( ON | OFF )] [-trunkmode ( ON | OFF )] [-trunkAllowedVlan &lt;int[-int]> ...] [-lacpMode &lt;lacpMode>] [-lacpKey &lt;positive_integer>] [-lagtype ( NODE | CLUSTER )] [-lacpPriority &lt;positive_integer>] [-lacpTimeout ( LONG | SHORT )] [-ifAlias &lt;string>] [-throughput &lt;positive_integer>] [-linkRedundancy ( ON | OFF )] [-bandwidthHigh &lt;positive_integer>  [-bandwidthNormal &lt;positive_integer>]] [-lldpmode &lt;lldpmode>] [-lrsetPriority &lt;positive_integer>]


##Arguments

<b>id</b>
ID of the Interface whose parameters you want to modify.
For a NetScaler appliance, specify the interface in C/U notation (for example, 1/3). 
For a cluster configuration, specify the interface in N/C/U notation (for example, 2/1/3).
where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
U is a unique integer for representing an interface in a particular port group.
N is the ID of the node to which an interface belongs in a cluster configuration.
Use spaces to separate multiple entries.

<b>speed</b>
Ethernet speed of the interface, in Mbps. 
Notes:
* If you set the speed as AUTO, the NetScaler appliance attempts to auto-negotiate or auto-sense the link speed of the interface when it is UP. You must enable auto negotiation on the interface.
* If you set a speed other than AUTO, you must specify the same speed for the peer network device. Mismatched speed and duplex settings between the peer devices of a link lead to link errors, packet loss, and other errors. 
Some interfaces do not support certain speeds. If you specify an unsupported speed, an error message appears.
Possible values: AUTO, 10, 100, 1000, 10000, 40000
Default value: AUTO

<b>duplex</b>
The duplex mode for the interface. Notes:* If you set the duplex mode to AUTO, the NetScaler appliance attempts to auto-negotiate the duplex mode of the interface when it is UP. You must enable auto negotiation on the interface. If you set a duplex mode other than AUTO, you must specify the same duplex mode for the peer network device. Mismatched speed and duplex settings between the peer devices of a link lead to link errors, packet loss, and other errors.
Possible values: AUTO, HALF, FULL
Default value: AUTO

<b>flowControl</b>
802.3x flow control setting for the interface.  The 802.3x specification does not define flow control for 10 Mbps and 100 Mbps speeds, but if a Gigabit Ethernet interface operates at those speeds, the flow control settings can be applied. The flow control setting that is finally applied to an interface depends on auto-negotiation. With the ON option, the peer negotiates the flow control, but the appliance then forces two-way flow control for the interface.
Possible values: OFF, RX, TX, RXTX, ON
Default value: OFF

<b>autoneg</b>
Auto-negotiation state of the interface. With the ENABLED setting, the NetScaler appliance auto-negotiates the speed and duplex settings with the peer network device on the link. The NetScaler appliance auto-negotiates the settings of only those parameters (speed or duplex mode) for which the value is set as AUTO.
Possible values: DISABLED, ENABLED
Default value: NSA_DVC_AUTONEG_ON

<b>haMonitor</b>
In a High Availability (HA) configuration, monitor the interface for failure events. In an HA configuration, an interface that has HA MON enabled and is not bound to any Failover Interface Set (FIS), is a critical interface. Failure or disabling of any critical interface triggers HA failover.
Possible values: ON, OFF
Default value: ON

<b>haHeartbeat</b>
In a High Availability (HA) or Cluster configuration, configure the interface for sending heartbeats. In an HA or Cluster configuration, an interface that has HA Heartbeat disabled should not send the heartbeats.
Possible values: OFF, ON
Default value: ON

<b>mtu</b>
The maximum transmission unit (MTU) is the largest packet size, measured in bytes excluding 14 bytes ethernet header and 4 bytes crc, that can be transmitted and received by this interface. Default value of MTU is 1500 on all the interface of Netscaler appliance any value configured more than 1500 on the interface will make the interface as jumbo enabled. In case of cluster backplane interface MTU value will be changed to 1514 by default, user has to change the backplane interface value to maximum mtu configured on any of the interface in cluster system plus 14 bytes more for backplane interface if Jumbo is enabled on any of the interface in a cluster system. Changing the backplane will bring back the MTU of backplane interface to default value of 1500. If a channel is configured as backplane then the same holds true for channel as well as member interfaces.
Default value: 1500
Minimum value: 1500
Maximum value: 9216

<b>tagall</b>
Add a four-byte 802.1q tag to every packet sent on this interface.  The ON setting applies the tag for this interface's native VLAN. OFF applies the tag for all VLANs other than the native VLAN.
Possible values: ON, OFF
Default value: OFF

<b>trunkmode</b>
Accept and send 802.1q VLAN tagged packets, based on Allowed Vlan List of this interface.
Possible values: ON, OFF
Default value: OFF

<b>trunkAllowedVlan</b>
VLAN ID or range of VLAN IDs will be allowed on this trunk interface. In the command line interface, separate the range with a hyphen. For example: 40-90.
Minimum value: 1
Maximum value: 4094

<b>lacpMode</b>
Bind the interface to a LA channel created by the Link Aggregation control protocol (LACP).  
Available settings function as follows:
* Active - The LA channel port of the NetScaler appliance generates LACPDU messages on a regular basis, regardless of any need expressed by its peer device to receive them.
* Passive - The LA channel port of the NetScaler appliance does not transmit LACPDU messages unless the peer device port is in the active mode. That is, the port does not speak unless spoken to.
* Disabled - Unbinds the interface from the LA channel. If this is the only interface in the LA channel, the LA channel is removed.
Possible values: DISABLED, ACTIVE, PASSIVE
Default value: DISABLED

<b>lacpKey</b>
Integer identifying the LACP LA channel to which the interface is to be bound. 
For an LA channel of the NetScaler appliance, this digit specifies the variable x of an LA channel in LA/x notation, where x can range from 1 to 8. For example, if you specify 3 as the LACP key for an LA channel, the interface is bound to the LA channel LA/3.
For an LA channel of a cluster configuration, this digit specifies the variable y of a cluster LA channel in CLA/(y-4) notation, where y can range from 5 to 8. For example, if you specify 6 as the LACP key for a cluster LA channel, the interface is bound to the cluster LA channel CLA/2.
Minimum value: 1
Maximum value: 8

<b>lagtype</b>
Type of entity (NetScaler appliance or cluster configuration) for which to create the channel.
Possible values: NODE, CLUSTER
Default value: NODE

<b>lacpPriority</b>
LACP port priority, expressed as an integer. The lower the number, the higher the priority. The NetScaler appliance limits the number of interfaces in an LA channel to sixteen.
Default value: 32768
Minimum value: 1
Maximum value: 65535

<b>lacpTimeout</b>
Interval at which the NetScaler appliance sends LACPDU messages to the peer device on the LA channel.
Available settings function as follows:
LONG - 30 seconds.
SHORT - 1 second.
Possible values: LONG, SHORT
Default value: NSA_LACP_TIMEOUT_LONG

<b>ifAlias</b>
Alias name for the interface. Used only to enhance readability. To perform any operations, you have to specify the interface ID.
Default value: " "

<b>throughput</b>
Low threshold value for the throughput of the interface, in Mbps. In an HA configuration, failover is triggered if the interface has HA MON enabled and the throughput is below the specified the threshold.
Minimum value: 0
Maximum value: 160000

<b>linkRedundancy</b>
Link Redundancy for Cluster LAG.
Possible values: ON, OFF
Default value: OFF

<b>bandwidthHigh</b>
High threshold value for the bandwidth usage of the interface, in Mbps. The NetScaler appliance generates an SNMP trap message when the bandwidth usage of the interface is greater than or equal to the specified high threshold value.
Minimum value: 0
Maximum value: 160000

<b>bandwidthNormal</b>
Normal threshold value for the bandwidth usage of the interface, in Mbps. When the bandwidth usage of the interface becomes less than or equal to the specified normal threshold after exceeding the high threshold, the NetScaler appliance generates an SNMP trap message to indicate that the bandwidth usage has returned to normal.
Minimum value: 0
Maximum value: 160000

<b>lldpmode</b>
Link Layer Discovery Protocol (LLDP) mode for an interface. The resultant LLDP mode of an interface depends on the LLDP mode configured at the global and the interface levels.
Possible values: NONE, TRANSMITTER, RECEIVER, TRANSCEIVER

<b>lrsetPriority</b>
LRSET port priority, expressed as an integer ranging from 1 to 1024. The highest priority is 1. The NetScaler limits the number of interfaces in an LRSET to 8. Within a LRSET the highest LR Priority Interface is considered as the first candidate for the Active interface, if the interface is UP.
Default value: 1024
Minimum value: 1
Maximum value: 1024



##unset interface

Use this command to remove  interface settings.Refer to the set  interface command for meanings of the arguments.


##Synopsys

unset interface &lt;id>@ [-speed] [-duplex] [-flowControl] [-autoneg] [-haMonitor] [-haHeartbeat] [-mtu] [-tagall] [-trunkmode] [-trunkAllowedVlan] [-lacpMode] [-lacpKey] [-lacpPriority] [-lacpTimeout] [-ifAlias] [-throughput] [-linkRedundancy] [-bandwidthHigh] [-bandwidthNormal] [-lldpmode] [-lrsetPriority]


##enable interface

Enables the interface. If the link is active, it can transmit and receive packets.Note: To view the status of an interface, use the show interface command.


##Synopsys

enable interface &lt;id>@


##Arguments

<b>id</b>
Interface number, in C/U format, where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
* LA - Indicates a link aggregation port.
* LO - Indicates a loop back port.
U is a unique integer for representing an interface in a particular port group.



##disable interface

Disables the interface from transmitting and receiving packets. The link remains active and the peer network device is unaware that the interface has been disabled. In a High Availability configuration, an interface that has HA MON enabled and is not bound to any Failover Interface Set (FIS), is a critical interface. Disabling or failure of any critical interface triggers HA failover.Note: To view the status of an interface, use the show interface command.


##Synopsys

disable interface &lt;id>@


##Arguments

<b>id</b>
Interface number, in C/U format, where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
* LA - Indicates a link aggregation port.
* LO - Indicates a loop back port.
U is a unique integer for representing an interface in a particular port group.



##reset interface

Restarts the interface but leaves the administrative state ENABLED or DISABLED and configuration unchanged. The link pertaining to the interface is reestablished with the existing settings.


##Synopsys

reset interface &lt;id>@


##Arguments

<b>id</b>
Interface number, in C/U format, where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
* LA - Indicates a link aggregation port.
* LO - Indicates a loop back port.
U is a unique integer for representing an interface in a particular port group.



##show interface

Displays the settings of all interfaces or of the specified interface on the NetScaler appliance. To display the settings of all interfaces, run the command without any parameters. To display the settings of a particular interface, specify the ID of the interface.


##Synopsys

show interface [&lt;id>@]show interface stats - alias for 'stat interface'


##Arguments

<b>id</b>
Interface number, in C/U format, where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
* LA - Indicates a link aggregation port.
* LO - Indicates a loop back port.
U is a unique integer for representing an interface in a particular port group.



##Outputs

<b>stateflag</b>

<b>deviceName</b>
Name of the interface.

<b>unit</b>
Unit number for this interface, signifying the sequence number in which this interface is discovered on this Netscaler.

<b>description</b>
Display the type of interface, the speeds at which this interface can operate, and, if applicable, the type of SFP,.

<b>flags</b>
Flags for this interface. Used for communicating the device states.

<b>mtu</b>
The maximum transmission unit (MTU) is the largest packet size, measured in bytes excluding 14 bytes ethernet header and 4 bytes crc, that can be transmitted and received by this interface. Default value of MTU is 1500 on all the interface of Netscaler appliance any value configured more than 1500 on the interface will make the interface as jumbo enabled. In case of cluster backplane interface MTU value will be changed to 1514 by default, user has to change the backplane interface value to maximum mtu configured on any of the interface in cluster system plus 14 bytes more for backplane interface if Jumbo is enabled on any of the interface in a cluster system. Changing the backplane will bring back the MTU of backplane interface to default value of 1500. If a channel is configured as backplane then the same holds true for channel as well as member interfaces.

<b>actualMtu</b>
MTU for this interface (the largest frame that can transit this interface).

<b>vlan</b>
Native VLAN for this interface.

<b>mac</b>
MAC address for this interface.

<b>uptime</b>
Duration for which the interface has been UP (Example: 3 hours 1 minute 1 second). This value is reset when the interface state changes to DOWN..

<b>downTime</b>
Duration for which the interface has been DOWN.  This value is reset when the interface state changes to UP.(Example: 3 hours 1 minute 1 second).

<b>reqMedia</b>
Requested media setting for this interface.

<b>reqSpeed</b>
Requested speed setting for this interface.

<b>reqDuplex</b>
Requested duplex setting for this interface.

<b>reqFlowcontrol</b>
Requested flow control setting for this interface.

<b>media</b>
Actual media setting for this interface.

<b>speed</b>
Actual speed setting for this interface.

<b>duplex</b>
Actual duplex setting for this interface.

<b>flowControl</b>
Actual flow control setting for this interface.

<b>Mode</b>
The  mode(AUTO/MANNUAL) for the LA channel.

<b>haMonitor</b>
HA monitor enabled or disabled for this interface.

<b>haHeartbeat</b>
HA Hearbeat send enabled or disabled for this interface.

<b>state</b>
Link state of the interface (UP/DOWN).

<b>autoneg</b>
Interface autonegotiation enabled or disabled.

<b>autonegResult</b>
Actual auto-negotiation setting for this interface.

<b>tagged</b>
VLAN tags setting on this channel.

<b>tagall</b>
VLAN tagging behavior on this interface. With the ON setting,, packets are tagged with all the VLANs that are bound to this interface. With the OFF setting, packets are tagged with the native VLAN.

<b>trunk</b>
This argument is deprecated by tagall.

<b>trunkmode</b>
Accept and send 802.1q VLAN tagged packets, based on Allowed Vlan List of this interface.

<b>trunkAllowedVlan</b>
VLAN ID or range of VLAN IDs will be allowed on this trunk interface. In the command line interface, separate the range with a hyphen. For example: 40-90.

<b>taggedAny</b>
Interface setting to accept/drop all tagged packets.

<b>taggedAutolearn</b>
Dynamic VLAN membership autolearning enabled or disabled on this interface.

<b>hangDetect</b>
Hang detection enabled or disabled for this interface.

<b>hangReset</b>
Hang reset enabled or disabled for this interface.

<b>linkState</b>
The current state of the link associated with the interface. For logical interfaces (LA), the state of the link is dependent on the state of the slave interfaces. For the link to be UP at least one of the slave interfaces needs to be UP.

<b>intfState</b>
Current state of the specified interface.  The interface state set to UP only if the link state is UP and administrative state is ENABLED.

<b>rxpackets</b>
Number of packets received by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>rxbytes</b>
Number of bytes received by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>rxerrors</b>
Number of inbound packets dropped by the hardware on a specified interface since the NetScaler appliance was started or the interface statistics were cleared. Packets can be dropped because of CRC, length (undersize or oversize), or alignment errors.

<b>rxdrops</b>
Number of inbound packets dropped by the specified interface. Commonly dropped packets are multicast frames, spanning tree BPDUs, packets destined to a MAC not owned by the NetScaler appliance when L2 mode is disabled, or packets tagged for a VLAN that is not bound to the interface.  In most healthy networks, this statistic increments at a steady rate regardless of traffic load.  A sharp spike in dropped packets generally indicates an issue with connected L2 switches, such as a forwarding database overflow resulting in packets being broadcast on all ports.

<b>txpackets</b>
Number of packets transmitted by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>txbytes</b>
Number of bytes transmitted by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>txerrors</b>
Number of outbound packets dropped by the hardware on a specified interface since the NetScaler appliance was started or the interface statistics were cleared. Packets can be dropped because of length (undersize or oversize) errors or a lack of resources. This statistic is available only for:
						(1) Loop back interface (LO) of all platforms.
						(2) All data ports on the NetScaler 12000 platform.
						(3) Management ports on the Netscaler MPX 15000 and 17000 platforms.

<b>txdrops</b>
Number of packets dropped in transmission by the specified interface for one of the following reasons.
						(1) VLAN mismatch.
						(2) Oversized packets.
						(3) Interface congestion.
						(4) Loopback packets sent on non loop back interface.

<b>inDisc</b>
Number of error-free inbound packets discarded by the specified interface because of a lack of resources (for example, insufficient receive buffers).

<b>outDisc</b>
Number of error-free outbound packets discarded by the specified interface because of a lack of resources. This statistic is not available on:
						(1) 10G ports of NetScaler MPX 12500/12500/15500-10G  platforms.
						(2) 10G data ports on NetScaler MPX 17500/19500/21500 platforms.

<b>fctls</b>
Number of times flow control is performed on the specified interface because of received pause frames.

<b>hangs</b>
Number of times the specified interface detected hangs in the transmit and receive paths since the NetScaler appliance was started or the interface statistics were cleared.

<b>stsStalls</b>
Number of times the status updates for a specified interface were stalled since the NetScaler appliance was started or the interface statistics were cleared. A status stall is detected when the status of the interface is not updated by the NIC hardware within 0.8 seconds of the last update.

<b>txStalls</b>
Number of times the interface stalled, when transmitting packets, since the NetScaler appliance was started or the interface statistics were cleared. Transmit (Tx) stalls are detected when a packet posted for transmission is not transmitted in 4 seconds.

<b>rxStalls</b>
Number of times the interface stalled, when receiving packets, since the NetScaler appliance was started or the interface statistics were cleared. Receive (Rx) stalls are detected when the following conditions are met:
						(1)The link is up for more than 10 minutes.
						(2)Packets are transmitted, but no packets are received for 16 seconds.

<b>bdgMacMoved</b>
Number of MAC moves between ports. A high rate of MAC moves typically indicates a bridge loop between two interfaces.

<b>bdgMuted</b>
Number of times the specified interface stopped transmitting and receiving packets because of MAC moves between ports.

<b>vmac</b>
Virtual MAC of this interface.

<b>vmac6</b>
Virtual MAC for IPv6 of this interface.

<b>lacpMode</b>
The LACP mode of the specified interface. The possible values are:
						 1. Active: A port in active mode generates LACP protocol messages on a regular basis, regardless of any need expressed by its partner to receive them.
						 2. Passive: A port in passive mode is generally not transmit LACP messages unless its partner is in the active mode; that is, it does not communicate to the other appliance unless other appliance communicates with this appliance.

<b>lacpKey</b>
Identifies the channel to which the interface is bound. The possible values are 1, 2, 3, and 4.

<b>lacpPriority</b>
LACP port priority, expressed as an integer. The lower the number, the higher the priority. The NetScaler appliance limits the number of interfaces in an LA channel to sixteen.

<b>lacpTimeout</b>
Time to wait for the LACPDU. If an LACPDU is not received within this interval, the NetScaler markes the link partner port as DOWN. Possible values; Long, Short. Long lacptimeout is 90 sec and Short LACP timeout is 3 sec.

<b>lagtype</b>
Type of entity (NetScaler appliance or cluster configuration) for which to create the channel.

<b>ifAlias</b>
Alias name for the interface. Used only to enhance readability. To perform any operations, you have to specify the interface ID.

<b>reqThroughput</b>
Minimum required throughput for an interface. Failover is triggered if the operating throughput of a Link Aggregation (LA) channel for which HAMON is ON falls below this value. The possible values are:
1. 1000Mbps for 1G interfaces.
2. 10000Mbps for 10G interfaces.
3. 160000Mbps for Link Aggregation channels.

<b>throughput</b>
Actual throughput for the interface.

<b>linkRedundancy</b>
Link Redundancy for Cluster LAG.

<b>bandwidthHigh</b>
High threshold value for the bandwidth usage of the interface, in Mbps. The NetScaler appliance generates an SNMP trap message when the bandwidth usage of the interface is greater than or equal to the specified high threshold value.

<b>bandwidthNormal</b>
Normal threshold value for the bandwidth usage of the interface, in Mbps. When the bandwidth usage of the interface becomes less than or equal to the specified normal threshold after exceeding the high threshold, the NetScaler appliance generates an SNMP trap message to indicate that the bandwidth usage has returned to normal.

<b>backplane</b>
The cluster backplane status of the interface. If the status is enabled, the interface is part of the cluster backplane. By default, the backplane status is disabled.

<b>ifnum</b>
Contains the LA Master, if the interface is part of LA channel.

<b>clearTime</b>
Time since the interface stats are cleared last time.

<b>slavestate</b>
State of the member interfaces.

<b>slavemedia</b>
Media type of the member interfaces.

<b>slavespeed</b>
Speed of the member interfaces.

<b>slaveduplex</b>
Duplex of the member interfaces.

<b>slaveflowctl</b>
Flowcontrol of the member interfaces.

<b>slavetime</b>
UP time of the member interfaces.

<b>intftype</b>
Interface Type, this field will have the interface type either it is virtual, physical or loopback.

<b>lacpActorMode</b>
* Active - The LA channel port of the NetScaler appliance generates LACPDU messages on a regular basis, regardless of any need expressed by its peer device to receive them.
* Passive - The LA channel port of the NetScaler appliance does not transmit LACPDU messages unless the peer device port is in the active mode. That is, the port does not speak unless spoken to.
* Disabled - Unbinds the interface from the LA channel. If this is the only interface in the LA channel, the LA channel is removed.

<b>lacpActorTimeout</b>
Interval at which the NetScaler appliance sends LACPDU messages to the peer device on the LA channel.
Available settings function as follows:
LONG - 30 seconds.
SHORT - 1 second.

<b>lacpActorPriority</b>
LACP Actor Priority. A LACP port priority is configured on each port using LACP. LACP uses the port priority with the port number to form the port identifier. The port priority determines which ports should be put in standby mode when there is a hardware limitation that prevents all compatible ports from aggregating.

<b>lacpActorPortno</b>
LACP Actor port number. LACP uses the port priority with the port number to form the port identifier.

<b>lacpPartnerState</b>
LACP Partner State. Whether the port is in Active or Passive negotiating state.

<b>lacpPartnerTimeout</b>
The timeout value for the information revieved in LACPDUs. It can have values as SHORT or LONG. The SHORT timeout is 3s and the LONG timeout is 90s.

<b>lacpPartnerAggregation</b>
The Aggregation flag indicates that the participant will allow the link to be used as part of an aggregate. Otherwise the link is to be used as an individual link, i.e. not aggregated with any other.

<b>lacpPartnerInsync</b>
The Synchronization flag indicates that the transmitting participant.s mux component is in sync with the system id and key information transmitted.

<b>lacpPartnerCollecting</b>
The Collecting flag indicates that the participant.s collector, i.e. the reception component of the mux, is definitely on. If set the flag communicates collecting.

<b>lacpPartnerDistributing</b>
The Distributing flag indicates that the participant.s distributor is not definitely off. If reset the flag indicates not distributing.

<b>lacpPartnerDefaulted</b>
If the timer expires in the Expired state, the Receive Machine enters the Defaulted state.

<b>lacpPartnerExpired</b>
If the LACPDUs are received for timeout period, the Receive Machine enters the Expired state and the timer is restarted with the timeout value of SHORT timeout

<b>lacpPartnerPriority</b>
LACP Partner Priority. A LACP port priority is configured on each port using LACP. LACP uses the port priority with the port number to form the port identifier. 
					The port priority determines which ports should be put in standby mode when there is a hardware limitation that prevents all compatible ports from aggregating.

<b>lacpPartnerSystemMac</b>
LACP Partner System MAC.

<b>lacpPartnerSystemPriority</b>
LACP Partner System Priority. The LACP partner's system priority. The values for the priority range from 0 to 65535. The lower the value, the higher the system priority. The switch with the lower system priority value determines which links between LACP partner are active and which are in the standby for each LACP Channel.

<b>lacpPartnerPortno</b>
LACP Partner Port number. LACP uses the port priority with the port number to form the port identifier.

<b>lacpPartnerKey</b>
LACP Partner Key. The LACP key used by the partner port.

<b>lacpActorAggregation</b>
The Aggregation flag indicates that the participant will allow the link to be used as part of an aggregate. Otherwise the link is to be used as an individual link, i.e. not aggregated with any other.

<b>lacpActorInsync</b>
The Synchronization flag indicates that the transmitting participant.s mux component is in sync with the system id and key information transmitted.

<b>lacpActorCollecting</b>
The Collecting flag indicates that the participant.s collector, i.e. the reception component of the mux, is definitely on. If set the flag communicates collecting.

<b>lacpActorDistributing</b>
The Distributing flag indicates that the participant.s distributor is not definitely off. If reset the flag indicates not distributing.

<b>lacpPortMuxState</b>
LACP Port MUX state. The state of the MUX control machine. The  Mux Control Machine attaches the physical port to an aggregate port, using the Selection Logic to choose an appropriate port, and turns the distributor and collector for the physical port on or off as required by protocol	information.

<b>lacpPortRxStat</b>
LACP Port RX state. The state of the Receive machine. The Receive Machine maintains partner information, recording protocol information from LACPDUs sent by remote partner(s). Received information is subject to a timeout, and if sufficient time elapses the receive machine will revert to using default partner information.

<b>lacpPortSelectState</b>
LACP Port SELECT state. The state of the SELECT state machine, It could be SELECTED or UNSELECTED.

<b>lldpmode</b>
Link Layer Discovery Protocol (LLDP) mode for an interface. The resultant LLDP mode of an interface depends on the LLDP mode configured at the global and the interface levels.

<b>lrsetPriority</b>
LRSET port priority, expressed as an integer ranging from 1 to 1024. The highest priority is 1. The NetScaler limits the number of interfaces in an LRSET to 8. Within a LRSET the highest LR Priority Interface is considered as the first candidate for the Active interface, if the interface is UP.

<b>lrActiveIntf</b>
LR set member interface state(active/inactive).

<b>devno</b>

<b>count</b>



##Example

The output for the show interface command is as follows:1)      Interface 0/1 (Gig Ethernet 10/100/1000 MBits) #4        flags=0x4021 &lt;ENABLED, UP, UP, autoneg, HAMON, 802.1q&gt;        MTU=1500, native vlan=1, MAC=00:30:48:67:9a:9a, uptime 1039h54m28s        Requested: media AUTO, speed AUTO, duplex AUTO, fctl OFF,                 throughput 02)      Interface 1/1 (Gig Ethernet, copper SFP) #3        flags=0x4021 &lt;ENABLED, UP, UP, autoneg, HAMON, BACKPLANE, 802.1q&gt;        MTU=1500, native vlan=1, MAC=00:e0:ed:12:e8:b7, uptime 1039h54m28s        Requested: media AUTO, speed AUTO, duplex AUTO, fctl OFF,                 throughput 03)      Interface 1/2 (Gig Ethernet, copper SFP) #2        flags=0x4001 &lt;ENABLED, DOWN, down, autoneg, HAMON, 802.1q&gt;        MTU=1500, native vlan=1, MAC=00:e0:ed:12:e8:b6, downtime 1039h54m28s        Requested: media AUTO, speed AUTO, duplex AUTO, fctl OFF,                 throughput 04)      Interface 1/3 (Gig Ethernet, copper SFP) #1        flags=0x4001 &lt;disabled, DOWN, down, autoneg, HAMON, 802.1q&gt;        MTU=1500, native vlan=1, MAC=00:e0:ed:12:e8:b5, downtime 1039h54m33s        Requested: media AUTO, speed AUTO, duplex AUTO, fctl OFF,                 throughput 05)      Interface 1/4 (Gig Ethernet, copper SFP) #0        flags=0x4001 &lt;disabled, UP, down, autoneg, HAMON, 802.1q&gt;        MTU=1500, native vlan=1, MAC=00:e0:ed:12:e8:b4, downtime 1039h54m28s        Requested: media AUTO, speed AUTO, duplex AUTO, fctl OFF,                 throughput 0 Done&gt;The output for the show interface 0/1 command is as follows:        Interface 0/1 (Gig Ethernet 10/100/1000 MBits) #4        flags=0xc020 &lt;ENABLED, UP, UP, autoneg, HAMON, 802.1q&gt;        MTU=1500, native vlan=1, MAC=00:30:48:67:9a:9a, uptime 0h00m40s        Requested: media AUTO, speed AUTO, duplex AUTO, fctl RXTX,                 throughput 0        Actual: media UTP, speed 1000, duplex FULL, fctl RXTX, throughput 1000        RX: Pkts(27) Bytes(2034) Errs(0) Drops(27) Stalls(0)        TX: Pkts(3) Bytes(170) Errs(0) Drops(22) Stalls(0)        NIC: InDisc(0) OutDisc(0) Fctls(0) Stalls(0) Hangs(0) Muted(0)        Bandwidth thresholds are not set. Done&gt;

##stat interface

Displays the statistics of all interfaces or of the specified interface on the NetScaler appliance. To display the statistics of all interfaces, run the command without any parameters. To display the statistics of a particular interface, specify the ID of the interface.


##Synopsys

stat interface [&lt;id>@] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>id</b>
Interface number, in C/U format, where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
* LA - Indicates a link aggregation port.
* LO - Indicates a loop back port.
U is a unique integer for representing an interface in a particular port group.

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

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Interface State (IntfState)</b>
Current state of the specified interface.  The interface state set to UP only if the link state is UP and administrative state is ENABLED .

<b>Link uptime (UpTime)</b>
Duration for which the link is UP. This statistic is reset when the state changes to DOWN.

<b>Link downtime (DnTime)</b>
Duration for which the link is DOWN. This statistic is reset when the state changes to UP.

<b>Bytes received (Rx Bytes)</b>
Number of bytes received by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>Bytes transmitted (Tx Bytes)</b>
Number of bytes transmitted by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>Packets received (Rx Pkts)</b>
Number of packets received by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>Packets transmitted (Tx Pkts)</b>
Number of packets transmitted by an interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>Jumbo Packets Received (JumboRcv)</b>
Number of Jumbo Packets received on this interface.

<b>Jumbo Packets Transmitted (JumboXmit)</b>
Number of Jumbo packets transmitted on this interface by upper layer, with TSO enabled actual trasmission size could be non Jumbo.

<b>Tagged Packets Received on Trunk interface through allowed vlan list (TrunkRcv)</b>
Number of Tagged Packets received on this Trunk interface through Allowed VLan List.

<b>Tagged Packets transmitted on Trunk interface through allowed vlan list (TrunkXmit)</b>
Number of Tagged Packets transmitted on this Trunk interface through Allowed VLan List.

<b>Multicast packets (McastPkt)</b>
Number of multicast packets received by the specified interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>NetScaler packets (NSPkt)</b>
Number of packets, destined to the NetScaler, received by an interface since the NetScaler appliance was started or the interface statistics were cleared. The packets destined to NetScaler are those that have the same MAC address as that of an interface or a VMAC address owned by the NetScaler.

<b>LACPDUs received (RxLacpdu)</b>
Number of Link Aggregation Control Protocol Data Units(LACPDUs) received by the specified interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>LACPDUs transmitted (TxLacpdu)</b>
Number of Link Aggregation Control Protocol Data Units(LACPDUs) transmitted by the specified interface since the NetScaler appliance was started or the interface statistics were cleared.

<b>Error packets received (hw) (ErrRx)</b>
Number of inbound packets dropped by the hardware on a specified interface once the NetScaler appliance starts or the interface statistics are cleared. This happens due to following reasons:
			1)	The hardware receives packets at a rate higher rate than that at which the software is processing packets. In this case, the hardware FIFO overruns and starts dropping the packets .
			2)	The specified interface fails to receive inbound packets from the appliance because of insufficient memory.
			3)	The specified interface receives packets with CRC errors (Alignment or Frame Check Sequence).
			4)	The specified interface receives overly long packets.
			5)	The specified interface receives packets with alignment errors.
			6)	The software does less buffering because it is running out of available memory. When hardware detects that there is no space into which to push newly arrived packets, it starts dropping them.
			7)	The specified interface receives packets with Frame Check Sequence (FCS) errors.
			8)	The specified interface receives packets smaller than 64 bytes.
			9)	The specified interface discards error-free inbound packets because of insufficient resources. For example: NIC buffers.
			10)	Packets are missed because of collision detection, link lost, physical decoding error, or MAC abort.

<b>Error packets transmitted (hw) (ErrTx)</b>
Number of outbound packets dropped by the hardware on a specified interface since the NetScaler appliance was started or the interface statistics were cleared. This could happen due to length (undersize or oversize) errors and lack of resources. This statistic is available only for: 
			(1) Loop back interface (LO) of all platforms.
			(2) All data ports on the NetScaler 12000 platform.
			(3) Management ports on the MPX 15000 and 17000 platforms.

<b>Inbound packets discarded(hw) (InDisc)</b>
Number of error-free inbound packets discarded by the specified interface due to a lack of resources, for example, insufficient receive buffers.

<b>Outbound packets discarded(hw) (OutDisc)</b>
Number of error-free outbound packets discarded by the specified interface due to a lack of resources. This statistic is not available on:
			(1) 10G ports of NetScaler MPX 12500/12500/15500-10G  platforms. 
			(2) 10G data ports on NetScaler MPX 17500/19500/21500 platforms.

<b>Packets dropped in Rx (sw) (DrpRxPkt)</b>
Number of inbound packets dropped by the specified interface. Commonly dropped packets are multicast frames, spanning tree BPDUs, packets destined to a MAC not owned by the NetScaler when L2 mode is disabled, or packets tagged for a VLAN that is not bound to the interface.  This statistic will increment in most healthy networks at a steady rate regardless of traffic load.  If a sharp spike in dropped packets occurs, it generally indicates an issue with connected L2 switches, such as a forwarding database overflow resulting in packets being broadcast on all ports.

<b>Packets dropped in Tx (sw) (DrpTxPkt)</b>
Number of packets dropped in transmission by the specified interface due to one of the following reasons.
			(1) VLAN mismatch.
			(2) Oversized packets.
			(3) Interface congestion.  
			(4) Loopback packets sent on non loop back interface.

<b>NIC hangs (Hangs)</b>
Number of times the specified interface detected hangs in the transmit and receive paths since the NetScaler appliance was started or the interface statistics were cleared.

<b>Status stalls (StsStall)</b>
Number of times the status updates for a specified interface were stalled since the NetScaler appliance was started or the interface statistics were cleared. A status stall is detected when the status of the interface is not updated by the NIC hardware within 0.8 seconds of the last update.

<b>Transmit stalls (TxStall)</b>
Number of times the interface stalled, when transmitting packets, since the NetScaler appliance was started or the interface statistics were cleared. Transmit (Tx) stalls are detected when a packet posted for transmission is not transmitted in 4 seconds.

<b>Receive stalls (RxStall)</b>
Number of times the interface stalled, when receiving packets, since the NetScaler appliance was started or the interface statistics were cleared. Receive (Rx) stalls are detected when the following conditions are met:
			(1)The link is up for more than 10 minutes. 
			(2)Packets are transmitted, but no packets is received for 16 seconds.

<b>Error-disables (ErrDis)</b>
Number of times the specified interface is disabled by the NetScaler, due to continuous Receive (Rx) or Transmit (Tx) stalls, since the NetScaler appliance was started or the interface statistics were cleared. The NetScaler disables an interface when one of the following conditions is met:
			(1) Three consecutive transmit stalls occurs with at most gap of 10 seconds between any two stalls.
			(2) Three consecutive receive stalls occurs with at most gap of 120 seconds between any two stalls.

<b>Duplex mismatches (DupMism)</b>
Number of times duplex mismatches were detected on the specified interface since the NetScaler appliance was started or the interface statistics were cleared. A mismatch will occur if the duplex mode is not identically set on both ends of the link. This statistic is only available on the NetScaler Classic edition.

<b>Link re-initializations (LnkReint)</b>
Number of times the link has been re-initialized. A re-initialization occurs due to link state change, configuration parameter change, or administrative reset operation.

<b>MAC moves registered (MacMvd)</b>
Number of MAC moves between ports. If a high rate of MAC moves is observed, it is likely that there is a bridge loop between two interfaces.

<b>Times NIC became muted (ErrMtd)</b>
Number of times the specified interface stopped transmitting and receiving packets due to MAC moves between ports.

<b>Receive CRC errors (ErrRxCRC)</b>
Number of packets received with the wrong checksum by the specified interface since the NetScaler appliance was started or the interface statistics were cleared. This indicates the number of Jabber frames received instead of CRC errors on the 10G data ports of NetScaler 12000-10G platform and the data ports of NetScaler MPX 15000 and 17000 platforms.

<b>Interface Alias (IntfAlias)</b>
Alias Name for the Interface

<b>Link State (State)</b>
The current state of the link associated with the interface. For logical interfaces (LA), the state of the link is dependent on the state of the slave interfaces. For the link to be UP at least one of the slave interfaces needs to be UP.



