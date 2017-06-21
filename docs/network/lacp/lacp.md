#lacp

The following operations can be performed on "lacp":


[set](#set-lacp) | [show](#show-lacp)

##set lacp

Sets the Link Aggregation Control Protocol (LACP) system priority. Note: The NetScaler appliance automatically adds a parameter called mac in the configuration file (ns.conf) for this command entry. This parameter is set to the MAC address of one of the NetScaler appliance's interfaces and is used along with the system priority to form the system ID for the LACP channel.


##Synopsys

set lacp -sysPriority &lt;positive_integer> [-ownerNode &lt;positive_integer>]


##Arguments

<b>sysPriority</b>
Priority number that determines which peer device of an LACP LA channel can have control over the LA channel. This parameter is globally applied to all LACP channels on the NetScaler appliance. The lower the number, the higher the priority.
Default value: 32768
Minimum value: 1
Maximum value: 65535

<b>ownerNode</b>
The owner node in a cluster for which we want to set the lacp priority. Owner node can vary from 0 to 31. Ownernode value of 254 is used for Cluster.
Default value: 255
Minimum value: 0



##show lacp

Displays the settings of all channels created by the link aggregation control protocol (LACP) on the NetScaler appliance.


##Synopsys

show lacp [-ownerNode &lt;positive_integer>]


##Arguments

<b>ownerNode</b>
The owner node in a cluster for which we want to set the lacp priority. Owner node can vary from 0 to 31. Ownernode value of 254 is used for Cluster.
Default value: 255
Minimum value: 0



##Outputs

<b>deviceName</b>
Name of the channel.

<b>sysPriority</b>
Priority number that determines which peer device of an LACP LA channel can have control over the LA channel. This parameter is globally applied to all LACP channels on the NetScaler appliance. The lower the number, the higher the priority.

<b>mac</b>
LACP system MAC.

<b>flags</b>
Flags of this channel.

<b>lacpKey</b>
LACP key of this channel.

<b>clustersysPriority</b>
LACP system (Cluster) priority

<b>clusterMac</b>
LACP system (Cluster) mac.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



