#ns ip6

The following operations can be performed on "ns ip6":


[add](#add-ns-ip6) | [rm](#rm-ns-ip6) | [set](#set-ns-ip6) | [unset](#unset-ns-ip6) | [show](#show-ns-ip6)

##add ns ip6

Creates an IPv6 address on the NetScaler appliance.


##Synopsys

add ns ip6 &lt;IPv6Address>@ [-scope ( global | link-local )] [-type &lt;type>  [-hostRoute ( ENABLED | DISABLED )  [-ip6hostRtGw &lt;ipv6_addr|*>]  [-metric &lt;integer>]  [-vserverRHILevel &lt;vserverRHILevel>]  [-ospf6LSAType ( INTRA_AREA | EXTERNAL )  [-ospfArea &lt;positive_integer>]]] ] [-vlan &lt;positive_integer>] [-nd ( ENABLED | DISABLED )] [-icmp ( ENABLED | DISABLED )] [-vServer ( ENABLED | DISABLED )] [-telnet ( ENABLED | DISABLED )] [-ftp ( ENABLED | DISABLED )] [-gui &lt;gui>] [-ssh ( ENABLED | DISABLED )] [-snmp ( ENABLED | DISABLED )] [-mgmtAccess ( ENABLED | DISABLED )] [-restrictAccess ( ENABLED | DISABLED )] [-dynamicRouting ( ENABLED | DISABLED )] [-state ( DISABLED | ENABLED )] [-map &lt;ip_addr>] [-ownerNode &lt;positive_integer>] [-td &lt;positive_integer>]


##Arguments

<b>IPv6Address</b>
IPv6 address to create on the NetScaler appliance.

<b>scope</b>
Scope of the IPv6 address to be created. Cannot be changed after the IP address is created.
Possible values: global, link-local
Default value: NS_GLOBAL

<b>type</b>
Type of IP address to be created on the NetScaler appliance. Cannot be changed after the IP address is created.
Possible values: NSIP, VIP, SNIP, GSLBsiteIP, ADNSsvcIP, CLIP
Default value: NS_IPV6_SNIP

<b>vlan</b>
The VLAN number.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>nd</b>
Respond to Neighbor Discovery (ND) requests for this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>icmp</b>
Respond to ICMP requests for this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>vServer</b>
Enable or disable the state of all the virtual servers associated with this VIP6 address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>telnet</b>
Allow Telnet access to this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>ftp</b>
Allow File Transfer Protocol (FTP) access to this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>gui</b>
Allow graphical user interface (GUI) access to this IP address.
Possible values: ENABLED, SECUREONLY, DISABLED
Default value: ENABLED

<b>ssh</b>
Allow secure Shell (SSH) access to this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>snmp</b>
Allow Simple Network Management Protocol (SNMP) access to this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>mgmtAccess</b>
Allow access to management applications on this IP address.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>restrictAccess</b>
Block access to nonmanagement applications on this IP address. This option is applicable forMIP6s, SNIP6s, and NSIP6s, and is disabled by default. Nonmanagement applications can run on the underlying NetScaler Free BSD operating system.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dynamicRouting</b>
Allow dynamic routing on this IP address. Specific to Subnet IPv6 (SNIP6) address.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>hostRoute</b>
Advertise a route for the VIP6 address by using the dynamic routing protocols running on the NetScaler appliance.
Possible values: ENABLED, DISABLED

<b>ip6hostRtGw</b>
IPv6 address of the gateway for the route. If Gateway is not set, VIP uses :: as the gateway.
Default value: 0

<b>metric</b>
Integer value to add to or subtract from the cost of the route advertised for the VIP6 address.
Minimum value: -16777215

<b>vserverRHILevel</b>
Advertise or do not advertise the route for the Virtual IP (VIP6) address on the basis of the state of the virtual servers associated with that VIP6.
* NONE - Advertise the route for the VIP6 address, irrespective of the state of the virtual servers associated with the address.
* ONE VSERVER - Advertise the route for the VIP6 address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - Advertise the route for the VIP6 address if all of the associated virtual servers are in UP state.
* VSVR_CNTRLD.   Advertise the route for the VIP address according to the  RHIstate (RHI STATE) parameter setting on all the associated virtual servers of the VIP address along with their states.
When Vserver RHI Level (RHI) parameter is set to VSVR_CNTRLD, the following are different RHI behaviors for the VIP address on the basis of RHIstate (RHI STATE) settings on the virtual servers associated with the VIP address:
* If you set RHI STATE to PASSIVE on all virtual servers, the NetScaler ADC always advertises the route for the VIP address.
* If you set RHI STATE to ACTIVE on all virtual servers, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers is in UP state.
*If you set RHI STATE to ACTIVE on some and PASSIVE on others, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers, whose RHI STATE set to ACTIVE, is in UP state.
Possible values: ONE_VSERVER, ALL_VSERVERS, NONE, VSVR_CNTRLD
Default value: RHI_STATE_ONE

<b>ospf6LSAType</b>
Type of LSAs to be used by the IPv6 OSPF protocol, running on the NetScaler appliance, for advertising the route for the VIP6 address.
Possible values: INTRA_AREA, EXTERNAL
Default value: DISABLED

<b>ospfArea</b>
ID of the area in which the Intra-Area-Prefix LSAs are to be advertised for the VIP6 address by the IPv6 OSPF protocol running on the NetScaler appliance. When ospfArea is not set, VIP6 is advertised on all areas.
Default value: -1
Maximum value: 4294967294LU

<b>state</b>
Enable or disable the IP address.
Possible values: DISABLED, ENABLED
Default value: ENABLED

<b>map</b>
Mapped IPV4 address for the IPV6 address.

<b>ownerNode</b>
ID of the cluster node for which you are adding the IP address. Must be used if you want the IP address to be active only on the specific node. Can be configured only through the cluster IP address. Cannot be changed after the IP address is created.
Default value: 255
Minimum value: 0

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

add ns ip6 2001::a/96 -scope GLOBAL

##rm ns ip6

Removes an IPv6 address configured on the NetScaler appliance.


##Synopsys

rm ns ip6 &lt;IPv6Address>@ [-td &lt;positive_integer>]


##Arguments

<b>IPv6Address</b>
IPv6 address that you want to remove.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

rm ns ip6 2002::5

##set ns ip6

Modifies the specified parameters of an IPv6 address configured on the NetScaler appliance.


##Synopsys

set ns ip6 (&lt;IPv6Address>@  [-td &lt;positive_integer>]) [-nd ( ENABLED | DISABLED )] [-icmp ( ENABLED | DISABLED )] [-vServer ( ENABLED | DISABLED )] [-telnet ( ENABLED | DISABLED )] [-ftp ( ENABLED | DISABLED )] [-gui &lt;gui>] [-ssh ( ENABLED | DISABLED )] [-snmp ( ENABLED | DISABLED )] [-mgmtAccess ( ENABLED | DISABLED )] [-restrictAccess ( ENABLED | DISABLED )] [-state ( DISABLED | ENABLED )] [-map &lt;ip_addr>] [-dynamicRouting ( ENABLED | DISABLED )] [-hostRoute ( ENABLED | DISABLED )  [-ip6hostRtGw &lt;ipv6_addr|*>]  [-metric &lt;integer>]  [-vserverRHILevel &lt;vserverRHILevel>]  [-ospf6LSAType ( INTRA_AREA | EXTERNAL )  [-ospfArea &lt;positive_integer>]]]


##Arguments

<b>IPv6Address</b>
IPv6 address whose parameters you want to modify.

<b>nd</b>
The state of ND responses for the entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>icmp</b>
The state of ICMP responses for the entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>vServer</b>
The state of vserver attribute for this IP entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>telnet</b>
The state of telnet access to this IP entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>ftp</b>
The state of ftp access to this IP entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>gui</b>
The state of GUI access to this IP entity.
Possible values: ENABLED, SECUREONLY, DISABLED
Default value: ENABLED

<b>ssh</b>
The state of SSH access to this IP entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>snmp</b>
The state of SNMP access to this IP entity.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>mgmtAccess</b>
The state of management access to this IP entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>restrictAccess</b>
Status of ports not used for management access (blocked/open) for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>state</b>
Enable or disable the IP address.
Possible values: DISABLED, ENABLED
Default value: ENABLED

<b>map</b>
Mapped IPV4 address for the IPV6 address.

<b>dynamicRouting</b>
Allow dynamic routing on this IP address. Specific to Subnet IPv6 (SNIP6) address.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>hostRoute</b>
Advertise a route for the VIP6 address by using the dynamic routing protocols running on the NetScaler appliance.
Possible values: ENABLED, DISABLED



##Example

set ns ip6 2001::a -map 10.102.33.27

##unset ns ip6

Modifies the parameters of an IPv6 address configured on the NetScaler appliance..Refer to the set ns ip6 command for meanings of the arguments.


##Synopsys

unset ns ip6 &lt;IPv6Address>@ [-td &lt;positive_integer>] [-ospfArea] [-nd] [-icmp] [-vServer] [-telnet] [-ftp] [-gui] [-ssh] [-snmp] [-mgmtAccess] [-restrictAccess] [-state] [-map] [-dynamicRouting] [-hostRoute] [-ip6hostRtGw] [-metric] [-vserverRHILevel] [-ospf6LSAType]


##Example

unset ns ip6 2001::a -ospfArea

##show ns ip6

Displays settings of all the IPv6 addresses or of the specified IPv6 address configured on the NetScaler appliance. To display settings of all the IPv6 addresses, run the command without any parameters. To display settings of a particular IPv6 address, specify the IPv6 address.


##Synopsys

show ns ip6 [&lt;IPv6Address>  [-td &lt;positive_integer>]]


##Arguments

<b>IPv6Address</b>
IPv6 address whose settings you want the NetScaler appliance to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>scope</b>
Scope of the IPv6 address to be created. Cannot be changed after the IP address is created.

<b>type</b>
The type of the IPV6 addressNOTE: This attribute is deprecated.This option is deprecated in favour of ip6_type

<b>ipType</b>
The type of the IPv6 address

<b>vlan</b>
The VLAN number.

<b>nd</b>
Whether ND is enabled or disabled.

<b>icmp</b>
Whether icmp is enabled or disabled.

<b>vServer</b>
Whether vserver is enabled or disabled.

<b>telnet</b>
Whether telnet is enabled or disabled.

<b>ssh</b>
Whether ssh is enabled or disabled.

<b>gui</b>
Whether gui is (enabled|SecureOnly|disabled).

<b>snmp</b>
Whether snmp is enabled or disabled.

<b>ftp</b>
Whether ftp is enabled or disabled.

<b>mgmtAccess</b>
Whether management access is enabled or disabled.

<b>restrictAccess</b>
Blocking of all ports not used for management access enabled or disabled

<b>state</b>
Current state of this IP.

<b>map</b>
Mapped IPV4 address for the IPV6 address.

<b>dynamicRouting</b>
Allow dynamic routing on this IP address. Specific to Subnet IPv6 (SNIP6) address.

<b>hostRoute</b>
Advertise a route for the VIP6 address by using the dynamic routing protocols running on the NetScaler appliance.

<b>ip6hostRtGw</b>
IPv6 address of the gateway for the route. If Gateway is not set, VIP uses :: as the gateway.

<b>metric</b>
The metric value to be added or subtracted from the cost of the hostroute advertised for this IPv6 entity.

<b>vserverRHILevel</b>
Advertise or do not advertise the route for the Virtual IP (VIP6) address on the basis of the state of the virtual servers associated with that VIP6.
* NONE - Advertise the route for the VIP6 address, irrespective of the state of the virtual servers associated with the address.
* ONE VSERVER - Advertise the route for the VIP6 address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - Advertise the route for the VIP6 address if all of the associated virtual servers are in UP state.
* VSVR_CNTRLD.   Advertise the route for the VIP address according to the  RHIstate (RHI STATE) parameter setting on all the associated virtual servers of the VIP address along with their states.
When Vserver RHI Level (RHI) parameter is set to VSVR_CNTRLD, the following are different RHI behaviors for the VIP address on the basis of RHIstate (RHI STATE) settings on the virtual servers associated with the VIP address:
* If you set RHI STATE to PASSIVE on all virtual servers, the NetScaler ADC always advertises the route for the VIP address.
* If you set RHI STATE to ACTIVE on all virtual servers, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers is in UP state.
*If you set RHI STATE to ACTIVE on some and PASSIVE on others, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers, whose RHI STATE set to ACTIVE, is in UP state.

<b>VIPrtadv2BSD</b>
Whether this route is advertised to FreeBSD

<b>VIPvserCount</b>
Number	of vservers	bound to this VIP

<b>VIPvserDownCount</b>
Number	of vservers	bound to this VIP, which are down

<b>ospf6LSAType</b>
The OSPF's route advertisement type.

<b>ospfArea</b>
The area ID of the area in which OSPF INTRA AREA PREFIX LSAs should be advertised. When ospfArea is not set, LSAs are advertised in all areas.

<b>ownerNode</b>
ID of the cluster node for which you are adding the IP address. Must be used if you want the IP address to be active only on the specific node. Can be configured only through the cluster IP address. Cannot be changed after the IP address is created.

<b>stateflag</b>

<b>cfgflags</b>
This contains the flags for IP in DB

<b>ipRefcount</b>
Used to keep reference count of IPv6

<b>systemType</b>
The type of the System. Possible Values: Standalone, HA, Cluster. Used for display purpose.

<b>devno</b>

<b>count</b>



##Example

show ns ip6

