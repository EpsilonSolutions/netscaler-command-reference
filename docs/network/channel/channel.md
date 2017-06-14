#channel

The following operations can be performed on "channel":


[add](#add-channel) | [rm](#rm-channel) | [set](#set-channel) | [unset](#unset-channel) | [bind](#bind-channel) | [unbind](#unbind-channel) | [show](#show-channel)

##add channel

Creates a link aggregate channel on the NetScaler appliance or on a cluster configuration. Link aggregation combines data coming from multiple ports into a single high-speed link. Configuring link aggregation increases the capacity and availability of the communication channel between the NetScaler appliance and other connected devices.When a network interface is bound to a channel, the channel parameters have precedence over the network interface parameters. That is, the network interface parameters are ignored. A network interface can be bound only to one channel.


##Synopsys

add channel &lt;id> [-ifnum &lt;interface_name> ...] [-state ( ENABLED | DISABLED )] [-lamac &lt;mac_addr>] [-speed &lt;speed>] [-flowControl &lt;flowControl>] [-haMonitor ( ON | OFF )] [-tagall ( ON | OFF )] [-ifAlias &lt;string>] [-throughput &lt;positive_integer>] [-bandwidthHigh &lt;positive_integer>  [-bandwidthNormal &lt;positive_integer>]]


##Arguments

<b>id</b>
ID for the LA channel or cluster LA channel to be created. Specify an LA channel in LA/x notation or cluster LA channel in CLA/x notation, where x can range from 1 to 4. Cannot be changed after the LA channel is created.

<b>ifnum</b>
Interfaces to be bound to the LA channel of a NetScaler appliance or to the LA channel of a cluster configuration.
For an LA channel of a NetScaler appliance, specify an interface in C/U notation (for example, 1/3). 
For an LA channel of a cluster configuration, specify an interface in N/C/U notation (for example, 2/1/3).
where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
U is a unique integer for representing an interface in a particular port group.
N is the ID of the node to which an interface belongs in a cluster configuration.
Use spaces to separate multiple entries.

<b>state</b>
Enable or disable the LA channel.
Possible values: ENABLED, DISABLED
Default value: NSA_DVC_ENABLE

<b>Mode</b>
The initital mode for the LA channel.
Possible values: MANUAL, AUTO

<b>connDistr</b>
The 'connection' distribution mode for the LA channel.
Possible values: DISABLED, ENABLED

<b>macdistr</b>
The  'MAC' distribution mode for the LA channel.
Possible values: SOURCE, DESTINATION, BOTH

<b>lamac</b>
Specifies a MAC address for the LA channels configured in NetScaler virtual appliances (VPX). This MAC address is persistent after each reboot. If you don't specify this parameter, a MAC address is generated randomly for each LA channel. These MAC addresses changes after each reboot.

<b>speed</b>
Ethernet speed of the channel, in Mbps. If the speed of any bound interface is greater than or equal to the value set for this parameter, the state of the interface is UP. Otherwise, the state is INACTIVE. Bound Interfaces whose state is INACTIVE do not process any traffic.
Possible values: AUTO, 10, 100, 1000, 10000
Default value: NSA_DVC_SPEED_AUTO

<b>flowControl</b>
Specifies the flow control type for this LA channel to manage the flow of frames. Flow control is a function as mentioned in clause 31 of the IEEE 802.3 standard. Flow control allows congested ports to pause traffic from the peer device. Flow control is achieved by sending PAUSE frames.
Possible values: OFF, RX, TX, RXTX
Default value: NSA_DVC_FC_OFF

<b>haMonitor</b>
In a High Availability (HA) configuration, monitor the LA channel for failure events. Failure of any LA channel that has HA MON enabled triggers HA failover.
Possible values: ON, OFF
Default value: NSA_DVC_MONITOR_ON

<b>tagall</b>
Adds a four-byte 802.1q tag to every packet sent on this channel.  The ON setting applies tags for all VLANs that are bound to this channel. OFF applies the tag for all VLANs other than the native VLAN.
Possible values: ON, OFF
Default value: NSA_DVC_VTRUNK_OFF

<b>trunk</b>
This is deprecated by tagall
Possible values: ON, OFF
Default value: OFF

<b>ifAlias</b>
Alias name for the LA channel. Used only to enhance readability. To perform any operations, you have to specify the LA channel ID.
Default value: " "

<b>throughput</b>
Low threshold value for the throughput of the LA channel, in Mbps. In an high availability (HA) configuration, failover is triggered when the LA channel has HA MON enabled and the throughput is below the specified threshold.
Maximum value: 160000

<b>bandwidthHigh</b>
High threshold value for the bandwidth usage of the LA channel, in Mbps. The NetScaler appliance generates an SNMP trap message when the bandwidth usage of the LA channel is greater than or equal to the specified high threshold value.
Maximum value: 160000



##rm channel

Removes an LA channel from the NetScaler appliance or a cluster LA channel from a cluster configuration.Important: When a LA channel is removed, the network interfaces bound to it induce network loops that decrease network performance. You must disable the network interfaces before you remove the channel.


##Synopsys

rm channel &lt;id>


##Arguments

<b>id</b>
ID of the LA channel or cluster LA channel that you want to remove. Specify an LA channel in LA/x notation or a cluster LA channel in CLA/x notation, where x can range from 1 to 4.



##set channel

Modifies the specified parameters of an LA channel.


##Synopsys

set channel &lt;id> [-state ( ENABLED | DISABLED )] [-lamac &lt;mac_addr>] [-speed &lt;speed>] [-mtu &lt;positive_integer>] [-flowControl &lt;flowControl>] [-haMonitor ( ON | OFF )] [-tagall ( ON | OFF )] [-ifAlias &lt;string>] [-throughput &lt;positive_integer>] [-lrMinThroughput &lt;positive_integer>] [-linkRedundancy ( ON | OFF )] [-bandwidthHigh &lt;positive_integer>  [-bandwidthNormal &lt;positive_integer>]]


##Arguments

<b>id</b>
ID of the LA channel or the cluster LA channel whose parameters you want to modify. Specify an LA channel in LA/x notation or a cluster LA channel in CLA/x notation, where x can range from 1 to 4. Required for identifying the LA channel and cannot be modified.

<b>state</b>
Enable or disable the LA channel.
Possible values: ENABLED, DISABLED
Default value: NSA_DVC_ENABLE

<b>Mode</b>
The mode for the LA channel.
Possible values: MANUAL, AUTO

<b>connDistr</b>
The  'connection' distribution mode for the LA channel.
Possible values: DISABLED, ENABLED

<b>macdistr</b>
The 'MAC' distribution mode for the LA channel.
Possible values: SOURCE, DESTINATION, BOTH

<b>lamac</b>
Allows User to set MAC address for LA channels on Hypervised platforms.

<b>speed</b>
The  speed for the LA channel.
Possible values: AUTO, 10, 100, 1000, 10000
Default value: NSA_DVC_SPEED_AUTO

<b>mtu</b>
The maximum transmission unit (MTU) is the largest packet size, measured in bytes excluding 14 bytes ethernet header and 4 bytes crc, that can be transmitted and received by this interface. Default value of MTU is 1500 on all the interface of Netscaler appliance any value configured more than 1500 on the interface will make the interface as jumbo enabled. In case of cluster backplane interface MTU value will be changed to 1514 by default, user has to change the backplane interface value to maximum mtu configured on any of the interface in cluster system plus 14 bytes more for backplane interface if Jumbo is enabled on any of the interface in a cluster system. Changing the backplane will bring back the MTU of backplane interface to default value of 1500. If a channel is configured as backplane then the same holds true for channel as well as member interfaces. In case of channel if member interfaces is configured as different mtu then the highest MTU configured MTU is treated as the LA MTU if MTU is not specified on LA explicitly. Low MTU interfaces in channel will be taken out of LA distribution list.
Default value: 1500
Minimum value: 1500
Maximum value: 9216

<b>flowControl</b>
Required flow control for the LA channel.
Possible values: OFF, RX, TX, RXTX
Default value: NSA_DVC_FC_OFF

<b>haMonitor</b>
The state of HA monitoring for the LA channel.
Possible values: ON, OFF
Default value: NSA_DVC_MONITOR_ON

<b>tagall</b>
The appliance adds  a four-byte 802.1q tag to every packet sent on this channel.  ON applies tags for all the VLANs that are bound to this channel. OFF, applies the tag for all VLANs other than the native VLAN.
Possible values: ON, OFF
Default value: NSA_DVC_VTRUNK_OFF

<b>trunk</b>
This is deprecated by tagall.
Possible values: ON, OFF
Default value: OFF

<b>ifAlias</b>
The alias name for the interface.
Default value: " "

<b>throughput</b>
Low threshold value for the throughput of the LA channel, in Mbps. In an high availability (HA) configuration, failover is triggered when the LA channel has HA MON enabled and the throughput is below the specified threshold.
Maximum value: 160000

<b>lrMinThroughput</b>
Specifies the minimum throughput threshold (in Mbps) to be met by the active subchannel. Setting this parameter automatically divides an LACP channel into logical subchannels, with one subchannel active and the others in standby mode.  When the maximum supported throughput of the active channel falls below the lrMinThroughput value, link failover occurs and a standby subchannel becomes active.
Maximum value: 80000

<b>linkRedundancy</b>
Link Redundancy for Cluster LAG.
Possible values: ON, OFF
Default value: OFF

<b>bandwidthHigh</b>
High threshold value for the bandwidth usage of the LA channel, in Mbps. The NetScaler appliance generates an SNMP trap message when the bandwidth usage of the LA channel is greater than or equal to the specified high threshold value.
Maximum value: 160000



##unset channel

Use this command to remove  channel settings.Refer to the set  channel command for meanings of the arguments.


##Synopsys

unset channel &lt;id> [-state] [-speed] [-mtu] [-flowControl] [-haMonitor] [-tagall] [-ifAlias] [-throughput] [-lrMinThroughput] [-linkRedundancy] [-bandwidthHigh] [-bandwidthNormal]


##bind channel

Binds the specified interfaces to a channel.


##Synopsys

bind channel &lt;id> &lt;ifnum> ...


##Arguments

<b>id</b>
ID of the LA channel or the cluster LA channel to which you want to bind interfaces. Specify an LA channel in LA/x notation or a cluster LA channel in CLA/x notation, where x can range from 1 to 4.

<b>ifnum</b>
Interfaces to be bound to the LA channel of a NetScaler appliance or to the LA channel of a cluster configuration.
For an LA channel of a NetScaler appliance, specify an interface in C/U notation (for example, 1/3). 
For an LA channel of a cluster configuration, specify an interface in N/C/U notation (for example, 2/1/3).
where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
U is a unique integer for representing an interface in a particular port group.
N is the ID of the node to which an interface belongs in a cluster configuration.
Use spaces to separate multiple entries.



##unbind channel

Unbinds the specified interfaces from an LA channel.


##Synopsys

unbind channel &lt;id> &lt;ifnum> ...


##Arguments

<b>id</b>
ID of the LA channel or cluster LA channel from which you want to unbind interfaces. Specify an LA channel in LA/x notation or a cluster LA channel in CLA/x notation, where x can range from 1 to 4.

<b>ifnum</b>
Interfaces to be unbound from the LA channel of a NetScaler appliance or from the LA channel of a cluster configuration.
For an LA channel of a NetScaler appliance, specify an interface in C/U notation (for example, 1/3). 
For an LA channel of a cluster configuration, specify an interface in N/C/U notation (for example, 2/1/3).
where C can take one of the following values:
* 0 - Indicates a management interface.
* 1 - Indicates a 1 Gbps port.
* 10 - Indicates a 10 Gbps port.
U is a unique integer for representing an interface in a particular port group.
N is the ID of the node to which an interface belongs in a cluster configuration.
Use spaces to separate multiple entries.



##show channel

Displays the settings of all LA channels or of the specified channel. To display the settings of all channels, run the command without any parameters. To display the settings of a particular channel, specify the ID of the channel.


##Synopsys

show channel [&lt;id>]


##Arguments

<b>id</b>
ID of an LA channel or LA channel in cluster configuration whose details you want the NetScaler appliance to display.
Specify an LA channel in LA/x notation or a cluster LA channel in CLA/x notation, where x can range from 1 to 4.
Minimum value: 1

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>deviceName</b>
LA channel name in form LA/x, where x is channel ID, which ranges from 1 to 4.

<b>unit</b>
Unit number of the channel. This is an internal reference number that the NetScaler uses to identify the channel.

<b>description</b>
The IEEE standard that the channel is based on.

<b>flags</b>
Flags of this channel.

<b>mtu</b>
The maximum transmission unit (MTU) is the largest packet size, measured in bytes excluding 14 bytes ethernet header and 4 bytes crc, that can be transmitted and received by this interface. Default value of MTU is 1500 on all the interface of Netscaler appliance any value configured more than 1500 on the interface will make the interface as jumbo enabled. In case of cluster backplane interface MTU value will be changed to 1514 by default, user has to change the backplane interface value to maximum mtu configured on any of the interface in cluster system plus 14 bytes more for backplane interface if Jumbo is enabled on any of the interface in a cluster system. Changing the backplane will bring back the MTU of backplane interface to default value of 1500. If a channel is configured as backplane then the same holds true for channel as well as member interfaces. In case of channel if member interfaces is configured as different mtu then the highest MTU configured MTU is treated as the LA MTU if MTU is not specified on LA explicitly. Low MTU interfaces in channel will be taken out of LA distribution list.

<b>actualMtu</b>
MTU of the channel. This is the maximum frame size that the channel can process.

<b>vlan</b>
Native VLAN of the channel.

<b>mac</b>
MAC address of the channel.

<b>lamac</b>
Specifies a MAC address for the LA channels configured in NetScaler virtual appliances (VPX). This MAC address is persistent after each reboot. If you don't specify this parameter, a MAC address is generated randomly for each LA channel. These MAC addresses changes after each reboot.

<b>uptime</b>
Duration for which the channel is UP. (Example: 3 hours 1 minute 1 second). This value is reset when the channel state changes to DOWN.

<b>downTime</b>
Duration for which the channel is DOWN. (Example: 3 hours 1 minute 1 second). This value is reset when the channel state changes to UP.

<b>reqMedia</b>
Requested media setting for this channel. Since there is no media associated with LA, the displayed values carry no significance.

<b>reqSpeed</b>
Requested speed setting for this channel. Since no media are associated with LA, this speed is used to determine the threshold for the slave interfaces. If the speed of the member interface is less than the requested speed, that interface is considered inactive.

<b>reqDuplex</b>
Requested duplex setting for this channel. Since no media are associated with LA, the displayed values carry no significance.

<b>reqFlowcontrol</b>
Requested flow control setting for this channel. Since no media are associated with LA, the displayed values carry no significance.

<b>media</b>
Requested media setting for this interface.

<b>speed</b>
Actual speed setting for this channel.

<b>duplex</b>
Actualduplex setting for this interface.

<b>flowControl</b>
Actual flow control setting for this channel.

<b>connDistr</b>
Connection distribution setting on this Channel.

<b>macdistr</b>
MAC distribution setting on this Channel.

<b>Mode</b>
The  mode(AUTO/MANNUAL) for the LA channel.

<b>haMonitor</b>
HA monitoring enabled or disabled for this channel.

<b>state</b>
Enable or disable the LA channel.

<b>autoneg</b>
Requested auto negotiation setting for this channel. Since no media are associated with LA, this setting has no effect.

<b>autonegResult</b>
Actual  auto negotiation setting for this channel.

<b>tagged</b>
VLAN tags setting on this channel.

<b>tagall</b>
The appliance adds a four-byte 802.1q tag to every packet sent on this channel.  ON applies tags for all the VLANs that are bound to this channel. OFF, applies the tag for all VLANs other than the native VLAN.

<b>trunk</b>
This is deprecated by tagallNOTE: This attribute is deprecated.The "trunk" argument is confused with LA-trunk, renaming this to "tagall" instead.

<b>taggedAny</b>
Channel setting to accept/drop all tagged packets.

<b>taggedAutolearn</b>
Dynaminc vlan membership on this channel.

<b>hangDetect</b>
Hang detect for this channel.

<b>hangReset</b>
Hang reset for this channel.

<b>linkState</b>
The current state of the link associated with the interface. For logical interfaces (LA), the state of the link is dependent on the state of the slave interfaces. For the link to be UP at least one of the slave interfaces needs to be UP.

<b>intfState</b>
Current state of the specified interface.  The interface state set to UP only if the link state is UP and administrative state is ENABLED.

<b>rxpackets</b>
Number of bytes received by all the slave interfaces of the channel since the NetScaler appliance was started or the interface statistics were cleared.

<b>rxbytes</b>
Number of packets received by all member interfaces since the NetScaler appliance was started or the interface statistics were cleared.

<b>rxerrors</b>
Number of inbound packets dropped by the hardware of the slave interfaces since the NetScaler appliance was started or the interface statistics were cleared. Possible causes of dropped packets are CRC, length (undersize or oversize), and alignment errors.

<b>rxdrops</b>
Number of inbound packets dropped by the channel's slave interfaces. Commonly dropped packets are multicast frames, spanning tree BPDUs, packets destined to a MAC not owned by the NetScaler when L2 mode is disabled, or packets tagged for a VLAN that is not bound to the interface.  In most healthy networks, this statistic increments at a steady rate regardless of traffic load.  A sharp spike in dropped packets generally indicates an issue with connected L2 switches, such as a forwarding database overflow resulting in packets being broadcast on all ports.

<b>txpackets</b>
Number of packets transmitted by slave interfaces of a channel since the NetScaler appliance was started or the interface statistics were cleared.

<b>txbytes</b>
Number of bytes transmitted by slave interfaces of a channel since the NetScaler appliance was started or the interface statistics were cleared.

<b>txerrors</b>
Number of outbound packets dropped by the hardware of a channel's slave interfaces since the NetScaler appliance was started or the interface statistics were cleared. Possible causes of dropped packets are length (undersize or oversize) errors and lack of resources.

<b>txdrops</b>
Number of packets dropped in transmission by a channel's slave interfaces for one of the following reasons:
						(1) VLAN mismatch.
						(2) Oversized packets.
						(3) Interface congestion.
						(4) Loopback packets sent on non-loopback interface.

<b>inDisc</b>
Number of error-free inbound packets discarded by a channel's slave interfaces because of a lack of resources (for example, insufficient receive buffers).

<b>outDisc</b>
Number of error-free outbound packets discarded by a channel's slave interfaces because of a lack of resources. This statistic is not available on:
						(1) 10G ports of NetScaler MPX 12500/12500/15500-10G  platforms.
						(2) 10G data ports on NetScaler MPX 17500/19500/21500 platforms.

<b>fctls</b>
Number of times flow control is performed on a channel's slave interfaces because of pause frames.

<b>hangs</b>
Number of hangs that occurred on the channel's slave interfaces.

<b>stsStalls</b>
Number of status stalls that occurred on the channel's slave interfaces.

<b>txStalls</b>
Number of Tx stalls happened that occurred on the channel's slave interfaces.

<b>rxStalls</b>
Number of Rx stalls that occurred on the channel's slave interfaces.

<b>bdgMuted</b>
Number of times a channel's slave interfaces stopped transmitting and receiving packets because of MAC moves between ports.

<b>vmac</b>
Virtual MAC of this channel.

<b>vmac6</b>
Virtual MAC for IPv6 on this interface.

<b>ifAlias</b>
The alias name for the interface.

<b>reqThroughput</b>
Minimum required throughput for an interface. Failover is triggered if the operating throughput of a Link Aggregation (LA) channel for which HAMON is ON falls below this value.

<b>lrMinThroughput</b>
Specifies the minimum throughput threshold (in Mbps) to be met by the active subchannel. Setting this parameter automatically divides an LACP channel into logical subchannels, with one subchannel active and the others in standby mode.  When the maximum supported throughput of the active channel falls below the lrMinThroughput value, link failover occurs and a standby subchannel becomes active.

<b>linkRedundancy</b>
Link Redundancy for Cluster LAG.

<b>throughput</b>
Actual throughput for the interface.

<b>bandwidthHigh</b>
High threshold value for the bandwidth usage of the LA channel, in Mbps. The NetScaler appliance generates an SNMP trap message when the bandwidth usage of the LA channel is greater than or equal to the specified high threshold value.

<b>bandwidthNormal</b>
Normal threshold value for the bandwidth usage of the LA channel, in Mbps. When the bandwidth usage of the LA channel returns to less than or equal to the specified normal threshold after exceeding the high threshold, the NetScaler appliance generates an SNMP trap message to indicate that the bandwidth usage has returned to normal.

<b>ifnum</b>
The interfaces bound to link aggregate channel.

<b>backplane</b>
The cluster backplane status of the LA. If the status is enabled, the LA is part of the cluster backplane. By default, the backplane status is disabled.

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

<b>lacpMode</b>
The LACP mode of the specified interface. The possible values are:
						 1. Active: A port in active mode generates LACP protocol messages on a regular basis, regardless of any need expressed by its partner to receive them.
						 2. Passive: A port in passive mode generally does not transmit LACP messages unless its partner is in the active mode; that is, it does not speak unless spoken to.
						 3. Disabled: Removes the interface from the LA channel. If this is only interface in the LA channel, the LA channel is also deleted.

<b>lacpTimeout</b>
Time to wait for the LACPDU.  If a LACPDU is not received within this interval, the NetScaler markes the link partner port as DOWN. Possible values: Long and Short. Long lacptimeout is 90 sec and Short LACP timeout is 3 sec.

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

<b>devno</b>

<b>count</b>



