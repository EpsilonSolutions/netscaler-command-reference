#arp

The following operations can be performed on "arp":


[add](#add-arp) | [rm](#rm-arp) | [send](#send-arp) | [show](#show-arp)

##add arp

Adds a static ARP entry to the ARP table of the NetScaler appliance.


##Synopsys

add arp -IPAddress &lt;ip_addr> [-td &lt;positive_integer>] -mac &lt;mac_addr> (-ifnum &lt;interface_name> | -vxlan &lt;positive_integer>) [-vtep &lt;ip_addr>] [-vlan &lt;positive_integer>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>IPAddress</b>
IP address of the network device that you want to add to the ARP table.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>mac</b>
MAC address of the network device.

<b>ifnum</b>
Interface through which the network device is accessible. Specify the interface in (slot/port) notation. For example, 1/3.

<b>vxlan</b>
ID of the VXLAN on which the IP address of this ARP entry is reachable.
Minimum value: 1
Maximum value: 16777215

<b>vtep</b>
IP address of the VXLAN tunnel endpoint (VTEP) through which the IP address of this ARP entry is reachable.

<b>vlan</b>
The VLAN ID through which packets are to be sent after matching the ARP entry. This is a numeric value.
Minimum value: 0

<b>ownerNode</b>
The owner node for the Arp entry.
Default value: -1 
Minimum value: 0
Maximum value: 31



##Example

add arp -ip 10.100.0.48 -mac 00:a0:cc:5f:76:3a -ifnum 1/1

##rm arp

Removes a specified static ARP entry or all static ARP entries from the NetScaler appliance's ARP table.


##Synopsys

rm arp (&lt;IPAddress> | -all) [-td &lt;positive_integer>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>IPAddress</b>
IP address of the network device in the ARP entry that you want to remove from the ARP table.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>all</b>
Remove all ARP entries from the ARP table of the NetScaler appliance.

<b>ownerNode</b>
The owner node for the Arp entry.
Default value: -1 
Minimum value: 0
Maximum value: 31



##send arp

Sends Gratuitous Address Resolution Protocol (GARP) messages for the specified NetScaler owned IP addresses.


##Synopsys

send arp ((-IPAddress &lt;ip_addr>  [-td &lt;positive_integer>]) | -all)


##Arguments

<b>IPAddress</b>
NetScaler owned IP address for which the NetScaler appliance sends Gratuitous Address Resolution Protocol (GARP) messages.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>all</b>
Send GARP messages for all NetScaler owned IP addresses on which the ARP option is enabled. In a secondary node of an high availability configuration, this option sends GARP messages for the node's NSIP address only.



##Example

send arp 10.10.10.10

##show arp

Display all the entries in the system's ARP table.


##Synopsys

show arp [&lt;IPAddress>  [-td &lt;positive_integer>]  [-ownerNode &lt;positive_integer>]]


##Arguments

<b>IPAddress</b>
The IP address corresponding to an ARP entry.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>ownerNode</b>
The cluster node which owns the ARP entry.
Default value: -1 
Minimum value: 0
Maximum value: 31



##Outputs

<b>mac</b>
The MAC address corresponding to an ARP entry.

<b>ifnum</b>
The interface on which this MAC address resides.

<b>timeout</b>
The time, in seconds, after which the entry times out.

<b>state</b>
The state of the ARP entry.

<b>flags</b>
The flags for the entry.

<b>type</b>
Indicates whether this ARP entry was added manually or dynamically. When you manually add an ARP entry, the value for this parameter is STATIC. Otherwise, it is DYNAMIC. For the NSIP and loopback IP addresses, the value is PERMANENT.

<b>vlan</b>
The VLAN ID through which packets are to be sent after matching the ARP entry. This is a numeric value.

<b>vxlan</b>
ID of the VXLAN on which the IP address of this ARP entry is reachable.

<b>vtep</b>
IP address of the VXLAN tunnel endpoint (VTEP) through which the IP address of this ARP entry is reachable.

<b>channel</b>
The tunnel, channel, or physical interface through which the ARP entry is identified.

<b>flag</b>
Flags for the entry.

<b>controlPlane</b>
This arp entry is populated by a control plane protocol

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

The output of the sh arp command is as follows:	5 configured arps:	IP                MAC               Inface   VLAN     Origin  TTL  Traffic Domain	-------          -------            -------  ------   ------- ---  -------------- 1) 10.250.11.1      00:04:76:dc:f1:b9   1/2      2       dynamic   700  02) 10.11.0.254      00:30:19:c1:7e:f4  1/1       1       dynamic   500  03) 10.11.0.41       00:d0:a8:00:7c:e4  0/1       1       dynamic   500  04) 10.11.222.2      00:ee:ff:22:00:01  0/1       1       dynamic   500  05) 10.11.201.12     00:30:48:31:23:49  0/1       1       dynamic   500  0

