#ns partition

The following operations can be performed on "ns partition":


[add](#add-ns-partition) | [rm](#rm-ns-partition) | [set](#set-ns-partition) | [unset](#unset-ns-partition) | [switch](#switch-ns-partition) | [bind](#bind-ns-partition) | [unbind](#unbind-ns-partition) | [show](#show-ns-partition) | [stat](#stat-ns-partition)

##add ns partition

creates a new admin partition


##Synopsys

add ns partition &lt;partitionName> [-maxBandwidth &lt;positive_integer>] [-minBandwidth &lt;positive_integer>] [-maxConn &lt;positive_integer>] [-maxMemLimit &lt;MBytes>] [-partitionMAC &lt;mac_addr>]


##Arguments

<b>partitionName</b>
Name of the Partition. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, that the partition can consume. A zero value indicates the bandwidth is unrestricted on the partition and it can consume up to the system limits.
Default value: 10240
Minimum value: 0

<b>minBandwidth</b>
Minimum bandwidth, in Kbps, that the partition can consume. A zero value indicates the bandwidth is unrestricted on the partition and it can consume up to the system limits
Default value: 10240
Minimum value: 0

<b>maxConn</b>
Maximum number of concurrent connections that can be open in the partition. A zero value indicates no limit on number of open connections.
Default value: 1024
Minimum value: 0

<b>maxMemLimit</b>
Maximum memory, in megabytes, allocated to the partition.  A zero value indicates the memory is unlimited on the partition and it can consume up to the system limits.
Default value: 10
Minimum value: 0

<b>partitionMAC</b>
Special MAC address for the partition which is used for communication over shared vlans in this partition. If not specified, the MAC address is auto-generated.



##Example

add partition &lt;pname&gt;

##rm ns partition

deletes a admin partition


##Synopsys

rm ns partition &lt;partitionName>


##Arguments

<b>partitionName</b>
Name of the Partition. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

rm partition &lt;pname&gt;

##set ns partition

set the properties of partition


##Synopsys

set ns partition &lt;partitionName> [-maxBandwidth &lt;positive_integer>] [-minBandwidth &lt;positive_integer>] [-maxConn &lt;positive_integer>] [-maxMemLimit &lt;MBytes>] [-partitionMAC &lt;mac_addr>]


##Arguments

<b>partitionName</b>
Name of the Partition. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, that the partition can consume. A zero value indicates the bandwidth is unrestricted on the partition and it can consume up to the system limits.
Default value: 10240
Minimum value: 0

<b>minBandwidth</b>
Minimum bandwidth, in Kbps, that the partition can consume. A zero value indicates the bandwidth is unrestricted on the partition and it can consume up to the system limits
Default value: 10240
Minimum value: 0

<b>maxConn</b>
Maximum number of concurrent connections that can be open in the partition. A zero value indicates no limit on number of open connections.
Default value: 1024
Minimum value: 0

<b>maxMemLimit</b>
Maximum memory, in megabytes, allocated to the partition.  A zero value indicates the memory is unlimited on the partition and it can consume up to the system limits.
Default value: 10
Minimum value: 0

<b>partitionMAC</b>
Special MAC address for the partition which is used for communication over shared vlans in this partition. If not specified, the MAC address is auto-generated.



##Example

set partition &lt;pname&gt;

##unset ns partition

Use this command to remove ns partition settings.Refer to the set ns partition command for meanings of the arguments.


##Synopsys

unset ns partition &lt;partitionName> [-maxBandwidth] [-minBandwidth] [-maxConn] [-maxMemLimit] [-partitionMAC]


##switch ns partition

switches to a new admin partition


##Synopsys

switch ns partition &lt;partitionName>


##Arguments

<b>partitionName</b>
Name of the Partition. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

switch partition &lt;pname&gt;

##bind ns partition

bind resources to a partition.


##Synopsys

bind ns partition &lt;partitionName> (-vlan &lt;positive_integer> | -vxlan &lt;positive_integer> | -bridgegroup &lt;positive_integer>)


##Arguments

<b>partitionName</b>
Name of the Partition. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>vlan</b>
Vlan Identifier.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
VXLAN Identifier.
Minimum value: 1
Maximum value: 16777215

<b>bridgegroup</b>
Bridge group Identifier.
Minimum value: 1
Maximum value: 1000



##Example

bind partition &lt;name&gt; -vlan 2

##unbind ns partition

Unbind resources to a partition.


##Synopsys

unbind ns partition &lt;partitionName> (-vlan &lt;positive_integer> | -vxlan &lt;positive_integer> | -bridgegroup &lt;positive_integer>)


##Arguments

<b>partitionName</b>
Name of the Partition. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>vlan</b>
Vlan Identifier.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
VXLAN Identifier.
Minimum value: 1
Maximum value: 16777215

<b>bridgegroup</b>
Bridge group Identifier.
Minimum value: 1
Maximum value: 1000



##Example

unbind partition &lt;name&gt; -vlan 2

##show ns partition

Display all the partitions configured


##Synopsys

show ns partition [&lt;partitionName>]


##Arguments

<b>partitionName</b>
Name of partition for which to display parameters.



##Outputs

<b>partitionid</b>
Partition Id

<b>partitionType</b>
Type of the Partition

<b>maxBandwidth</b>
Maximum bandwidth, in Kbps, that the partition can consume. A zero value indicates the bandwidth is unrestricted on the partition and it can consume up to the system limits.

<b>minBandwidth</b>
Minimum bandwidth, in Kbps, that the partition can consume. A zero value indicates the bandwidth is unrestricted on the partition and it can consume up to the system limits

<b>maxConn</b>
Maximum number of concurrent connections that can be open in the partition. A zero value indicates no limit on number of open connections.

<b>maxMemLimit</b>
Maximum memory, in megabytes, allocated to the partition.  A zero value indicates the memory is unlimited on the partition and it can consume up to the system limits.

<b>stateflag</b>
Used internally for display.

<b>vlan</b>
Identifier of the vlan that is assigned to this partition.

<b>vxlan</b>
Identifier of the vxlan that is assigned to this partition.

<b>bridgegroup</b>
Identifier of the bridge group that is assigned to this partition.

<b>partitionMAC</b>
Special MAC address for the partition which is used for communication over shared vlans in this partition. If not specified, the MAC address is auto-generated.

<b>pmacInternal</b>
Partition MAC is generated internally.

<b>devno</b>

<b>count</b>



##Example

show partition

##stat ns partition

Displays statistics that have been collected for the specific partition.


##Synopsys

stat ns partition [&lt;partitionName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>partitionName</b>
Name of the partition.

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

<b>Minimum Bandwidth (MinBW)</b>
Minimum Bandwidth required by the partition.

<b>Maximum Bandwidth (MaxBW)</b>
Maximum Banwidth allowed for the partition.

<b>Maximum Connection (MaxConn)</b>
Maximum Connection allowed for the partition.

<b>Maximum Memory (MaxMem)</b>
Maximum memory limit for the partition.

<b>Current Bandwith (CurBW)</b>
Current Bandwidth usage for the partition.

<b>Current Connections (CurConn)</b>
Current Connections on this partition.

<b>Memory Usage(%) (MemUsgPcnt)</b>
Memory usage(%) on this partition.

<b>Total Packet Drops (TotDrops)</b>
Total packet drops for the partition.

<b>Total Drops(KB) (TotTokenDrops)</b>
Total drops(KB) for the partition.

<b>Total Connection Drops (TotConnDrops)</b>
Total connection drops for the partition.



##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



