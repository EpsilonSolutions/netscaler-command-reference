#cluster node

The following operations can be performed on "cluster node":


[add](#add-cluster-node) | [set](#set-cluster-node) | [unset](#unset-cluster-node) | [rm](#rm-cluster-node) | [show](#show-cluster-node) | [stat](#stat-cluster-node) | [bind](#bind-cluster-node) | [unbind](#unbind-cluster-node)

##add cluster node

Adds a NetScaler appliance to a cluster.


##Synopsys

add cluster node &lt;nodeId>@ &lt;IPAddress>@ [-state &lt;state>] [-backplane &lt;interface_name>@] [-priority &lt;positive_integer>] [-nodegroup &lt;string>] [-delay &lt;mins>]


##Arguments

<b>nodeId</b>
Unique number that identifies the cluster node.
Minimum value: 0
Maximum value: 31

<b>IPAddress</b>
NetScaler IP (NSIP) address of the appliance to add to the cluster. Must be an IPv4 address.

<b>state</b>
Admin state of the cluster node. The available settings function as follows:
ACTIVE - The node serves traffic.
SPARE - The node does not serve traffic unless an ACTIVE node goes down.
PASSIVE - The node does not serve traffic, unless you change its state. PASSIVE state is useful during temporary maintenance activities in which you want the node to take part in the consensus protocol but not to serve traffic.
Possible values: ACTIVE, SPARE, PASSIVE
Default value: PASSIVE

<b>backplane</b>
Interface through which the node communicates with the other nodes in the cluster. Must be specified in the three-tuple form n/c/u, where n represents the node ID and c/u refers to the interface on the appliance.
Minimum value: 1

<b>priority</b>
Preference for selecting a node as the configuration coordinator. The node with the lowest priority value is selected as the configuration coordinator.
When the current configuration coordinator goes down, the node with the next lowest priority is made the new configuration coordinator. When the original node comes back up, it will preempt the new configuration coordinator and take over as the configuration coordinator.
Note: When priority is not configured for any of the nodes or if multiple nodes have the same priority, the cluster elects one of the nodes as the configuration coordinator.
Default value: 31
Minimum value: 0
Maximum value: 31

<b>nodegroup</b>
The default node group in a Cluster system.
Default value: DEFAULT_NG

<b>delay</b>
Applicable for Passive node and node becomes passive after this timeout
Default value: 0
Maximum value: 1440



##Example

add cluster node 1 1.1.1.1 -backplane 1/1/1 -state ACTIVE

##set cluster node

Modifies the attributes of a cluster node.


##Synopsys

set cluster node &lt;nodeId>@ [-state &lt;state>] [-backplane &lt;interface_name>@] [-priority &lt;positive_integer>] [-delay &lt;mins>]


##Arguments

<b>nodeId</b>
ID of the cluster node to be modified.
Minimum value: 0
Maximum value: 31

<b>state</b>
Admin state of the cluster node. The available settings function as follows:
ACTIVE - The node serves traffic.
SPARE - The node does not serve traffic unless an ACTIVE node goes down.
PASSIVE - The node does not serve traffic, unless you change its state. PASSIVE state is useful during temporary maintenance activities in which you want the node to take part in the consensus protocol but not to serve traffic.
Possible values: ACTIVE, SPARE, PASSIVE
Default value: PASSIVE

<b>backplane</b>
Interface through which the node communicates with the other nodes in the cluster. Must be specified in the three-tuple form n/c/u, where n represents the node ID and c/u refers to the interface on the appliance.
Minimum value: 1

<b>priority</b>
Preference for selecting a node as the configuration coordinator. The node with the lowest priority value is selected as the configuration coordinator.
When the current configuration coordinator goes down, the node with the next lowest priority is made the new configuration coordinator. When the original node comes back up, it will preempt the new configuration coordinator and take over as the configuration coordinator.
Note: When priority is not configured for any of the nodes or if multiple nodes have the same priority, the cluster elects one of the nodes as the configuration coordinator.
Default value: 31
Minimum value: 0
Maximum value: 31

<b>delay</b>
Applicable for Passive node and node becomes passive after this timeout
Default value: 0
Maximum value: 1440



##Example

set cluster node 1 -state PASSIVE

##unset cluster node

Use this command to remove cluster node settings.Refer to the set cluster node command for meanings of the arguments.


##Synopsys

unset cluster node &lt;nodeId>@ [-state] [-backplane] [-priority] [-delay]


##rm cluster node

Removes a node from the cluster and removes the cluster instance from the node. You must execute this command on the cluster IP address.


##Synopsys

rm cluster node &lt;nodeId> [-clearNodegroupConfig ( YES | NO )]


##Arguments

<b>nodeId</b>
ID of the cluster node to be removed from the cluster.
Minimum value: 0
Maximum value: 31

<b>clearNodegroupConfig</b>
Option to remove nodegroup config
Possible values: YES, NO
Default value: YES



##Example

rm cluster node 1

##show cluster node

Displays information about the cluster node. 


##Synopsys

show cluster node [&lt;nodeId>@]


##Arguments

<b>nodeId</b>
ID of the cluster node for which to display information. If an ID is not provided, information about all nodes is shown.
Default value: 255
Minimum value: 0
Maximum value: 31



##Outputs

<b>IPAddress</b>
The IP Address of the node.

<b>flags</b>
The flags for this entry.

<b>clusterHealth</b>
Node clusterd state.

<b>effectiveState</b>
Node effective health state.

<b>operationalSyncState</b>
Node Operational Reconciliation state.

<b>masterState</b>
Node Master state.

<b>health</b>
Node Health state.

<b>state</b>
Active, Spare or Passive.

<b>backplane</b>
Interface through which the node communicates with the other nodes in the cluster. Must be specified in the three-tuple form n/c/u, where n represents the node ID and c/u refers to the interface on the appliance.

<b>syncState</b>
Enable/Disable the synchronization of cluster configurations on the node.

<b>priority</b>
Preference for selecting a node as the configuration coordinator. The node with the lowest priority value is selected as the configuration coordinator.
When the current configuration coordinator goes down, the node with the next lowest priority is made the new configuration coordinator. When the original node comes back up, it will preempt the new configuration coordinator and take over as the configuration coordinator.
Note: When priority is not configured for any of the nodes or if multiple nodes have the same priority, the cluster elects one of the nodes as the configuration coordinator.

<b>isConfigurationCoordinator</b>
This argument is used to determine whether the node is configuration coordinator (CCO).

<b>isLocalnode</b>
This argument is used to determine whether it is local node.

<b>NodeRSSKeyMismatch</b>
This argument is used to determine if there is a RSS key mismatch at cluster node level.

<b>NodeLicenseMismatch</b>
This argument is used to determine if there is a License mismatch at cluster node level.

<b>NodeJumboNotSupported</b>
This argument is used to determine if Jumbo framework not supported at cluster node level.

<b>stateflag</b>

<b>nodeList</b>
Nodelist for displaying Heartbeat not seen interfaces on a cluster node

<b>ifacesList</b>
Interface list corresponding to nodelist for Heartbeat not seen interfaces on a cluster node

<b>enabledIfaces</b>
Enabled Interfaces on a cluster node.

<b>disabledIfaces</b>
Disabled Interfaces on a cluster node.

<b>partialFailIfaces</b>
Partial Failure Interfaces on a cluster node.

<b>hamonIfaces</b>
Hamon Interfaces on a cluster node.

<b>ifaces</b>
Interfaces status on cluster node.

<b>nodegroup</b>
The default node group in a Cluster system.

<b>name</b>
Name of the state specific nodegroup.

<b>cfgflags</b>
Flag indicates whether the node is bound to cluster nodegroup

<b>routeMonitor</b>
The IP address (IPv4 or IPv6).

<b>routeMonState</b>
Current routemonstate

<b>netmask</b>
The netmask.

<b>delay</b>
Applicable for Passive node and node becomes passive after this timeout

<b>curPassiveTimeout</b>
Applicable for Passive node and node becomes passive after this timeout

<b>isLearnedAsPassive</b>
Applicable for Active nodes, it will be set to TRUE if the node is active but learned as Passive

<b>devno</b>

<b>count</b>



##Example

An example of the command's output is as follows:       1 cluster node:1)Node ID: 1        IP:                  1.1.1.1*        Backplane:           1/1/1        Health:              UP        Admin State:         ACTIVE        Operational State:   ACTIVE(Configuration Coordinator)        Sync State:          DISABLED  Done  *: Local node                 

##stat cluster node

Displays statistics for a cluster node.


##Synopsys

stat cluster node [&lt;nodeId>@] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>nodeId</b>
ID of the cluster node for which to display statistics. If an ID is not provided, statistics are shown for all nodes.
Minimum value: 0
Maximum value: 31

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

<b>Sync state (Sync State)</b>
Sync state of the cluster node.

<b>Health</b>
Health of the cluster node.

<b>Node IP (NodeIP)</b>
NSIP address of the cluster node.

<b>Operational state (OpState)</b>
Operational state of the cluster node.

<b>Heartbeats transmitted (HB Sent)</b>
Number of heartbeats sent. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>Heartbeats received (HB Rcvd)</b>
Number of heartbeats received. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>Current node-node connections (NNMCurConn)</b>
Number of connections open for node-to-node communication.

<b>Node-node messages transmitted (NNMTotConnTx)</b>
Number of node-to-node messages sent. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>Node-node messages received (NNMTotConnRx)</b>
Number of node-to-node messages received. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>PTP operational state (PTP State)</b>
PTP state of the node. This state is Master for one node and Slave for the rest. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows UNKNOWN. When executed from the cluster IP address, shows all the statistics.

<b>PTP packets transmitted (PTP Tx)</b>
Number of PTP packets transmitted by the node. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>PTP packets received (PTP Rx)</b>
Number of PTP packets received on the node. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>Multicast/Broadcast send errors (NNMErrMsend)</b>
Number of errors in sending node-to-node multicast/broadcast messages. When executed from the NSIP address, shows the statistics for local node only. For remote node it shows a value of 0. When executed from the cluster IP address, shows all the statistics.

<b>(Health)</b>
Health of the node in the cluster.

<b>CH State</b>
Health State of the node with respect to sync in the cluster.



##Related Commands

<ul><li><a href="../../../.html#stat-cluster-ins/.html#stat-cluster-ins">stat cluster instance</a></li></ul>



##bind cluster node

Adds a route monitor to the specified cluster node.


##Synopsys

bind cluster node &lt;nodeId> (-routeMonitor &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>])


##Arguments

<b>nodeId</b>
A number that uniquely identifies the cluster node. 
Minimum value: 0
Maximum value: 31

<b>routeMonitor</b>
Route Monitor

<b>netmask</b>
The subnet mask associated with the IPv4 route specified by the routeMonitor parameter.



##Example

bind cluster node 1 -routeMonitor 5.5.5.0 255.255.255.0

##unbind cluster node

Removes a route monitor entry from the local node


##Synopsys

unbind cluster node &lt;nodeId> (-routeMonitor &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>])


##Arguments

<b>nodeId</b>
A number that uniquely identifies the cluster node.
Minimum value: 0
Maximum value: 31

<b>routeMonitor</b>
Route Monitor

<b>netmask</b>
The subnet mask associated with the IPv4 route specified by the routeMonitor parameter.



##Example

unbind cluster node 1 -routeMonitor 5.5.5.0 255.255.255.0

