#cluster instance

The following operations can be performed on "cluster instance":


[add](#add-cluster-instance) | [rm](#rm-cluster-instance) | [set](#set-cluster-instance) | [unset](#unset-cluster-instance) | [enable](#enable-cluster-instance) | [disable](#disable-cluster-instance) | [show](#show-cluster-instance) | [stat](#stat-cluster-instance)

##add cluster instance

Adds a cluster instance to the appliance. Execute this command on only the first node that you add to the cluster.


##Synopsys

add cluster instance &lt;clId> [-deadInterval &lt;secs>] [-helloInterval &lt;msecs>] [-preemption ( ENABLED | DISABLED )] [-quorumType ( MAJORITY | NONE )] [-inc ( ENABLED | DISABLED )] [-processLocal ( ENABLED | DISABLED )]


##Arguments

<b>clId</b>
Unique number that identifies the cluster.
Minimum value: 1
Maximum value: 16

<b>deadInterval</b>
Amount of time, in seconds, after which nodes that do not respond to the heartbeats are assumed to be down.
Default value: 3
Minimum value: 3
Maximum value: 60

<b>helloInterval</b>
Interval, in milliseconds, at which heartbeats are sent to each cluster node to check the health status.
Default value: 200
Minimum value: 200
Maximum value: 1000

<b>preemption</b>
Preempt a cluster node that is configured as a SPARE if an ACTIVE node becomes available.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>quorumType</b>
Quorum Configuration Choices  - "Majority" (recommended) requires majority of nodes to be online for the cluster to be UP. "None" relaxes this requirement.
Possible values: MAJORITY, NONE
Default value: MAJORITY

<b>inc</b>
This option is required if the cluster nodes reside on different networks.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>processLocal</b>
By turning on this option packets destined to a service in a cluster will not under go any steering.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add cluster instance 1

##rm cluster instance

Removes the cluster instance from the node. You must execute this command on the NetScaler IP (NSIP) address of the node.


##Synopsys

rm cluster instance &lt;clId>


##Arguments

<b>clId</b>
Unique number that identifies the cluster.
Minimum value: 1
Maximum value: 16



##Example

rm cluster instance 1

##set cluster instance

Modifies the specified attributes of a cluster instance.


##Synopsys

set cluster instance &lt;clId> [-deadInterval &lt;secs>] [-helloInterval &lt;msecs>] [-preemption ( ENABLED | DISABLED )] [-quorumType ( MAJORITY | NONE )] [-inc ( ENABLED | DISABLED )] [-processLocal ( ENABLED | DISABLED )] [-nodegroup &lt;string>]


##Arguments

<b>clId</b>
ID of the cluster instance to be modified.
Minimum value: 1
Maximum value: 16

<b>deadInterval</b>
Amount of time, in seconds, after which nodes that do not respond to the heartbeats are assumed to be down.
Default value: 3
Minimum value: 3
Maximum value: 60

<b>helloInterval</b>
Interval, in milliseconds, at which heartbeats are sent to each cluster node to check the health status.
Default value: 200
Minimum value: 200
Maximum value: 1000

<b>preemption</b>
Preempt a cluster node that is configured as a SPARE if an ACTIVE node becomes available.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>quorumType</b>
Quorum Configuration Choices  - "Majority" (recommended) requires majority of nodes to be online for the cluster to be UP. "None" relaxes this requirement.
Possible values: MAJORITY, NONE
Default value: MAJORITY

<b>inc</b>
This option is required if the cluster nodes reside on different networks.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>processLocal</b>
By turning on this option packets destined to a service in a cluster will not under go any steering.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nodegroup</b>
The node group in a Cluster system used for transition from L2 to L3.



##Example

set cluster instance 1 -preemption ENABLED

##unset cluster instance

Use this command to remove cluster instance settings.Refer to the set cluster instance command for meanings of the arguments.


##Synopsys

unset cluster instance &lt;clId> [-deadInterval] [-helloInterval] [-preemption] [-quorumType] [-inc] [-processLocal] [-nodegroup]


##enable cluster instance

Enables a cluster instance.


##Synopsys

enable cluster instance &lt;clId>


##Arguments

<b>clId</b>
ID of the cluster instance that you want to enable.
Minimum value: 1
Maximum value: 16



##Example

enable cluster instance 1

##disable cluster instance

Disables a cluster instance.


##Synopsys

disable cluster instance &lt;clId>


##Arguments

<b>clId</b>
ID of the cluster instance that you want to disable.
Minimum value: 1
Maximum value: 16



##Example

disable cluster instance 1

##show cluster instance

Displays information about the cluster instance and its nodes.


##Synopsys

show cluster instance [&lt;clId>]


##Arguments

<b>clId</b>
Unique number that identifies the cluster.
Minimum value: 1
Maximum value: 16



##Outputs

<b>deadInterval</b>
Amount of time, in seconds, after which nodes that do not respond to the heartbeats are assumed to be down.

<b>helloInterval</b>
Interval, in milliseconds, at which heartbeats are sent to each cluster node to check the health status.

<b>preemption</b>
Preempt a cluster node that is configured as a SPARE if an ACTIVE node becomes available.

<b>adminstate</b>
Cluster Admin State.

<b>quorumType</b>
Quorum Configuration Choices  - "Majority" (recommended) requires majority of nodes to be online for the cluster to be UP. "None" relaxes this requirement.

<b>propState</b>
Enable/Disable the execution of commands on the cluster. This will not impact the execution of commands on individual cluster nodes by using the NSIP.

<b>inc</b>
This option is required if the cluster nodes reside on different networks.

<b>nodegroup</b>
The node group in a Cluster system used for transition from L2 to L3.

<b>processLocal</b>
By turning on this option packets destined to a service in a cluster will not under go any steering.

<b>nodeId</b>
The unique number that identiies a cluster.

<b>IPAddress</b>
The IP Address of the node.

<b>flags</b>
The flags for this entry.

<b>masterState</b>
Master state.

<b>health</b>
Node Health state.

<b>clusterHealth</b>
Node clusterd state.

<b>effectiveState</b>
Node effective health state.

<b>state</b>
Active, Spare or Passive. An active node serves traffic. A spare node serves as a backup for active nodes. A passive node does not serve traffic. This may be useful during temporary maintenance activity where it is desirable that the node takes part in the consensus protocol, but not serve traffic.

<b>flag</b>
Cluster Flag.

<b>operationalstate</b>
Cluster Operational State.

<b>status</b>
Cluster Operational State.

<b>isConfigurationCoordinator</b>
This argument is used to determine whether the node is configuration coordinator (CCO).

<b>isLocalnode</b>
This argument is used to determine whether it is local node.

<b>RSSKeyMismatch</b>
This argument is used to determine if there is a RSS key mismatch at cluster instance level.

<b>NodegroupStateWarning</b>
This argumnt is used to determind whether all the cluster nodes are bound to nodegroup with state set.

<b>LicenseMismatch</b>
This argument is used to determine if there is a License mismatch at cluster instance level.

<b>JumboNotSupported</b>
This argument is used to determine if Jumbo framework is not supported at cluster instance level.

<b>ClusterNoHeartbeatOnNode</b>
HB is not seen on the backplane interface of member node

<b>ClusterNoLinksetMBF</b>
MBF is enabled but linkset is not configured

<b>ClusterNoSpottedIp</b>
There is no spotted SNIP or MIP

<b>NodeRSSKeyMismatch</b>
This argument is used to determine if there is a RSS key mismatch at cluster node level.

<b>NodeLicenseMismatch</b>
This argument is used to determine if there is a License mismatch at cluster node level.

<b>NodeJumboNotSupported</b>
This argument is used to determine if Jumbo framework not supported at cluster node level.

<b>stateflag</b>
State Flag.

<b>operationalPropState</b>
Cluster Operational Propagation State.

<b>devno</b>

<b>count</b>



##Example

An example of the command's output is as follows:1)Cluster ID: 1        Dead Interval: 3 secs        Hello Interval: 200 msecs        Preemption: DISABLED        Propagation: ENABLED        Cluster Status: ENABLED(admin), ENABLED(operational), UP        Member Nodes:        Node ID         Node IP              Health     Admin State       Operational State        -------         -------              ------     -----------       -----------------1)      1               1.1.1.1*             UP         ACTIVE            ACTIVE(Configuration Coordinator)2)      2               1.1.1.2              UP         ACTIVE            ACTIVE Done *: Local node                

##stat cluster instance

Displays statistics for a cluster instance.


##Synopsys

stat cluster instance [&lt;clId>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clId</b>
ID of the cluster instance for which to display statistics.
Minimum value: 1
Maximum value: 16

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

<b>Cluster size (CLNumNodes)</b>
Number of nodes in the cluster.

<b>Cluster status (CLCurEnable)</b>
State of the cluster.

<b>Configuration coordinator (CLViewLeader)</b>
NSIP address of the Configuration Coordinator of the cluster.

<b>Total steered packets (TotSteeredPkts)</b>
Total number of packets steered on the cluster backplane.

<b>Traffic received (Bkplane Rx)</b>
Traffic received on backplane (in mbits)

<b>Traffic transmitted (Bkplane Tx)</b>
Traffic transmitted from backplane (in mbits)

<b>Dropped steered packets (DFDdropPkts)</b>
Number of steered packets that are dropped.

<b>Propagation timeout (propTimeout)</b>
Number of times the update to the client timed-out.



##Related Commands

<ul><li><a href="../../../l#stat-cluster/l#stat-cluster">stat cluster node</a></li></ul>



