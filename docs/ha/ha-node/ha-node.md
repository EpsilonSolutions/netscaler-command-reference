#HA node

The following operations can be performed on "HA node":


[add](#add-ha-node) | [rm](#rm-ha-node) | [set](#set-ha-node) | [unset](#unset-ha-node) | [bind](#bind-ha-node) | [unbind](#unbind-ha-node) | [show](#show-ha-node) | [stat](#stat-ha-node)

##add HA node

Adds a peer node to an HA configuration. Each node must add the other as a peer. An algorithm determines which node becomes primary and which becomes secondary.


##Synopsys

add HA node &lt;id> &lt;IPAddress> [-inc ( ENABLED | DISABLED )]


##Arguments

<b>id</b>
Number that uniquely identifies the node. For self node, it will always be 0. Peer node values can range from 1-64.
Minimum value: 1
Maximum value: 64

<b>IPAddress</b>
The NSIP or NSIP6 address of the node to be added for an HA configuration. This setting is neither propagated nor synchronized.

<b>inc</b>
This option is required if the HA nodes reside on different networks. When this mode is enabled, the following independent network entities and configurations are neither propagated nor synced to the other node: MIPs, SNIPs, VLANs, routes (except LLB routes), route monitors, RNAT rules (except any RNAT rule with a VIP as the NAT IP), and dynamic routing configurations. They are maintained independently on each node.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##rm HA node

Removes the peer node from the HA configuration. To completely remove both the nodes from the HA configuration, you have to log on to each node and remove its peer node.


##Synopsys

rm HA node &lt;id>


##Arguments

<b>id</b>
Number that uniquely identifies the peer node.
CLI users: To learn the ID of the peer node, run the show HA node command on the local node.
Minimum value: 0
Maximum value: 64



##set HA node

Sets the specified HA related parameters for the node. The settings are neither propagated nor synchronized to the peer node.


##Synopsys

set HA node [-haStatus &lt;haStatus>] [-haSync ( ENABLED | DISABLED )] [-haProp ( ENABLED | DISABLED )] [-helloInterval &lt;msecs>] [-deadInterval &lt;secs>] [-failSafe ( ON | OFF )] [-maxFlips &lt;positive_integer>] [-maxFlipTime &lt;positive_integer>] [-syncvlan &lt;positive_integer>]


##Arguments

<b>id</b>
Number that uniquely identifies the node. For self node, it will always be 0. Peer node values can range from 1-64.
Minimum value: 0
Maximum value: 64

<b>haStatus</b>
The HA status of the node. The HA status STAYSECONDARY is used to force the secondary device stay as secondary independent of the state of the Primary device. For example, in an existing HA setup, the Primary node has to be upgraded and this process would take few seconds. During the upgradation, it is possible that the Primary node may suffer from a downtime for a few seconds. However, the Secondary should not take over as the Primary node. Thus, the Secondary node should remain as Secondary even if there is a failure in the Primary node.
	 STAYPRIMARY configuration keeps the node in primary state in case if it is healthy, even if the peer node was the primary node initially. If the node with STAYPRIMARY setting (and no peer node) is added to a primary node (which has this node as the peer) then this node takes over as the new primary and the older node becomes secondary. ENABLED state means normal HA operation without any constraints/preferences. DISABLED state disables the normal HA operation of the node.
Possible values: ENABLED, STAYSECONDARY, DISABLED, STAYPRIMARY

<b>haSync</b>
Automatically maintain synchronization by duplicating the configuration of the primary node on the secondary node. This setting is not propagated. Automatic synchronization requires that this setting be enabled (the default) on the current secondary node. Synchronization uses TCP port 3010.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>haProp</b>
Automatically propagate all commands from the primary to the secondary node, except the following:
* All HA configuration related commands. For example, add ha node, set ha node, and bind ha node. 
* All Interface related commands. For example, set interface and unset interface.
* All channels related commands. For example, add channel, set channel, and bind channel.
The propagated command is executed on the secondary node before it is executed on the primary. If command propagation fails, or if command execution fails on the secondary, the primary node executes the command and logs an error.  Command propagation uses port 3010.
Note: After enabling propagation, run force synchronization on either node.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>helloInterval</b>
Interval, in milliseconds, between heartbeat messages sent to the peer node. The heartbeat messages are UDP packets sent to port 3003 of the peer node.
Default value: 200
Minimum value: 200
Maximum value: 1000

<b>deadInterval</b>
Number of seconds after which a peer node is marked DOWN if heartbeat messages are not received from the peer node.
Default value: 3
Minimum value: 3
Maximum value: 60

<b>failSafe</b>
Keep one node primary if both nodes fail the health check, so that a partially available node can back up data and handle traffic. This mode is set independently on each node.
Possible values: ON, OFF
Default value: OFF

<b>maxFlips</b>
Max number of flips allowed before becoming sticky primary
Default value: 0

<b>maxFlipTime</b>
Interval after which flipping of node states can again start
Default value: 0

<b>syncvlan</b>
Vlan on which HA related communication is sent. This include sync, propagation , connection mirroring , LB persistency config sync, persistent session sync and session state sync. However HA heartbeats can go all interfaces.
Minimum value: 1
Maximum value: 4094



##unset HA node

Use this command to remove HA node settings.Refer to the set HA node command for meanings of the arguments.


##Synopsys

unset HA node [-haStatus] [-haSync] [-haProp] [-helloInterval] [-deadInterval] [-failSafe] [-maxFlips] [-maxFlipTime] [-syncvlan]


##bind HA node

Adds a route monitor to the local node. When a NetScaler appliance has only static routes for reaching a network, and you want to create a route monitor for the network, you must enable monitored static routes (MSR) for the static routes.Route Monitors are supported both in non-INC and INC modes.


##Synopsys

bind HA node [&lt;id>] (-routeMonitor &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>])


##Arguments

<b>id</b>
Number that uniquely identifies the local node. The ID of the local node is always 0.
Minimum value: 0
Maximum value: 64

<b>routeMonitor</b>
A route that you want the NetScaler appliance to monitor in its internal routing table. You can specify an IPv4 address or network, or an IPv6 address or network prefix. If you specify an IPv4 network address or IPv6 network prefix, the appliance monitors any route that matches the network or prefix.



##unbind HA node

Removes a route monitor entry from the local node. The NetScaler appliance stops monitoring the route in its internal routing table.


##Synopsys

unbind HA node [&lt;id>] (-routeMonitor &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>])


##Arguments

<b>id</b>
Number that uniquely identifies the local node. The ID of the local node is always 0.
Minimum value: 0
Maximum value: 64

<b>routeMonitor</b>
The route specified in the route monitor entry that you want to remove from the NetScaler appliance. Can be an IPv4 address or network, or an IPv6 address or network prefix.



##show HA node

Displays the HA settings of both nodes or, if you specify a node, just the specified node.You can use this command to display the master state (primary or secondary) of the nodes in a HA configuration.


##Synopsys

show HA node [&lt;id>]


##Arguments

<b>id</b>
ID of the node whose HA settings you want to display. (The ID of the local node is always 0.)
Minimum value: 0
Maximum value: 64

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>name</b>
Node Name.

<b>IPAddress</b>
IP Address of the node.

<b>flags</b>
The flags for this entry.

<b>stateflag</b>

<b>haStatus</b>
HA status.

<b>state</b>
HA Master State.

<b>haSync</b>
HA Sync State.

<b>haProp</b>
HA Propagation Status.

<b>enaifaces</b>
Enabled interfaces.

<b>disifaces</b>
Disabled interfaces.

<b>hamonifaces</b>
HAMON ON interfaces.

<b>pfifaces</b>
Interfaces causing Partial Failure.

<b>ifaces</b>
Interfaces on which non-multicast is not seen.

<b>network</b>
The network.

<b>netmask</b>
The netmask.

<b>inc</b>
INC state.

<b>ssl2</b>
SSL card status.

<b>helloInterval</b>
Hello Interval.

<b>deadInterval</b>
Dead Interval.

<b>masterStateTime</b>
Time elapsed in current master state

<b>failSafe</b>
Keep one node primary if both nodes fail the health check, so that a partially available node can back up data and handle traffic. This mode is set independently on each node.

<b>routeMonitor</b>
The IP address (IPv4 or IPv6).

<b>maxFlips</b>
Max number of flips allowed before becoming sticky primary

<b>maxFlipTime</b>
Interval after which flipping of node states can again start

<b>curFlips</b>
Keeps track of number of flips that have happened till now in current interval

<b>completedFlipTime</b>
To inform user whether flip time is elapsed or not

<b>syncvlan</b>
Vlan on which HA related communication is sent. This include sync, propagation , connection mirroring , LB persistency config sync, persistent session sync and session state sync. However HA heartbeats can go all interfaces.

<b>routeMonitorState</b>
State for route monitor

<b>devno</b>

<b>count</b>



##Example

An example of the command's output is as follows:2 configured nodes:1) Node ID: 0 IP: 192.168.100.5 Primary node2) Node ID: 2 IP: 192.168.100.112 Secondary node

##stat HA node

Display the statistics related to HA configuration.


##Synopsys

stat HA node [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>High Availability (HA)</b>
Whether a NetScaler appliance is configured for high availability. Possible values are YES and NO. If the value is NO, the high availability statistics below are invalid.

<b>System state (HAState)</b>
State of the HA node, based on its health, in a high availability setup. Possible values are: 
UP ? Indicates that the node is accessible and can function as either a primary or secondary node.
DISABLED ? Indicates that the high availability status of the node has been manually disabled. Synchronization and propagation cannot take place between the peer nodes.
INIT ? Indicates that the node is in the process of becoming part of the high availability configuration. 
PARTIALFAIL ? Indicates that one of the high availability monitored interfaces has failed because of a card or link failure. This state triggers a failover.
COMPLETEFAIL ? Indicates that all the interfaces of the node are unusable, because the interfaces on which high availability monitoring is enabled are not connected or are manually disabled. This state triggers a failover.
DUMB ? Indicates that the node is in listening mode. It does not participate in high availability transitions or transfer configuration from the peer node. This is a configured value, not a statistic.
PARTIALFAILSSL ? Indicates that the SSL card has failed. This state triggers a failover.
ROUTEMONITORFAIL ? Indicates that the route monitor has failed. This state triggers a failover.

<b>Master state (mastate)</b>
Indicates the high availability state of the node. Possible values are: 
STAYSECONDARY ? Indicates that the selected node remains the secondary node in a high availability setup. In this case a forced failover does not change the state but, instead, returns an appropriate error message. This is a configured value and not a statistic.
PRIMARY ? Indicates that the selected node is the primary node in a high availability setup. 
SECONDARY ? Indicates that the selected node is the secondary node in a high availability setup. 
CLAIMING ? Indicates that the secondary node is in the process of taking over as the primary node. This is the intermediate state in the transition of the secondary node to primary status. 
FORCE CHANGE - Indicates that the secondary node is forcibly changing its status to primary due to a forced failover issued on the secondary node.

<b>Last Transition time (TransTime)</b>
Time when the last master state transition occurred. You can use this statistic for debugging.

<b>Heartbeats received (HApktrx)</b>
Number of heartbeat packets received from the peer node. Heartbeats are sent at regular intervals (default is 200 milliseconds) to determine the state of the peer node.

<b>Heartbeats sent (HApkttx)</b>
Number of heartbeat packets sent to the peer node. Heartbeats are sent at regular intervals (default is 200 milliseconds) to determine the state of the peer node.

<b>Propagation timeouts (ptimeout)</b>
Number of times propagation timed out.

<b>Sync failure (syncfail)</b>
Number of times the configuration of the primary and secondary nodes failed to synchronize since that last transition. A synchronization failure results in mismatched configuration. It can be caused by a mismatch in the Remote Procedural Call (RPC) password on the two nodes forming the high availability pair.



