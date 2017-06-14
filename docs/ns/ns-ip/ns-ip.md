#ns ip

The following operations can be performed on "ns ip":


[add](#add-ns-ip) | [rm](#rm-ns-ip) | [set](#set-ns-ip) | [unset](#unset-ns-ip) | [enable](#enable-ns-ip) | [disable](#disable-ns-ip) | [show](#show-ns-ip)

##add ns ip

Creates an IPv4 address on the NetScaler appliance.


##Synopsys

add ns ip &lt;IPAddress>@ &lt;netmask> [-type &lt;type>  [-hostRoute ( ENABLED | DISABLED )  [-hostRtGw &lt;ip_addr>]  [-metric &lt;integer>]  [-vserverRHILevel &lt;vserverRHILevel>]  [-vserverRHIMode ( DYNAMIC_ROUTING | RISE )]  [-ospfLSAType ( TYPE1 | TYPE5 )  [-ospfArea &lt;positive_integer>]]] ] [-arp ( ENABLED | DISABLED )] [-icmp ( ENABLED | DISABLED )] [-vServer ( ENABLED | DISABLED )] [-telnet ( ENABLED | DISABLED )] [-ftp ( ENABLED | DISABLED )] [-gui &lt;gui>] [-ssh ( ENABLED | DISABLED )] [-snmp ( ENABLED | DISABLED )] [-mgmtAccess ( ENABLED | DISABLED )] [-restrictAccess ( ENABLED | DISABLED )] [-dynamicRouting ( ENABLED | DISABLED )] [-state ( ENABLED | DISABLED )] [-vrID &lt;positive_integer>] [-icmpResponse &lt;icmpResponse>] [-ownerNode &lt;positive_integer>] [-arpResponse &lt;arpResponse>] [-td &lt;positive_integer>]


##Arguments

<b>IPAddress</b>
IPv4 address to create on the NetScaler appliance. Cannot be changed after the IP address is created.

<b>netmask</b>
Subnet mask associated with the IP address.

<b>type</b>
Type of the IP address to create on the NetScaler appliance. Cannot be changed after the IP address is created. The following are the different types of NetScaler owned IP addresses:
* A Subnet IP (SNIP) address is used by the NetScaler ADC to communicate with the servers. The NetScaler also uses the subnet IP address when generating its own packets, such as packets related to dynamic routing protocols, or to send monitor probes to check the health of the servers.
* A Virtual IP (VIP) address is the IP address associated with a virtual server. It is the IP address to which clients connect. An appliance managing a wide range of traffic may have many VIPs configured. Some of the attributes of the VIP address are customized to meet the requirements of the virtual server.
* A GSLB site IP (GSLBIP) address is associated with a GSLB site. It is not mandatory to specify a GSLBIP address when you initially configure the NetScaler appliance. A GSLBIP address is used only when you create a GSLB site.
* A Cluster IP (CLIP) address is the management address of the cluster. All cluster configurations must be performed by accessing the cluster through this IP address.
Possible values: SNIP, VIP, NSIP, GSLBsiteIP, CLIP
Default value: NSADDR_SNIP

<b>arp</b>
Respond to ARP requests for this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>icmp</b>
Respond to ICMP requests for this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>vServer</b>
Use this option to set (enable or disable) the virtual server attribute for this IP address.
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
Allow secure shell (SSH) access to this IP address.
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
Block access to nonmanagement applications on this IP. This option is applicable for MIPs, SNIPs, and NSIP, and is disabled by default. Nonmanagement applications can run on the underlying NetScaler Free BSD operating system.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dynamicRouting</b>
Allow dynamic routing on this IP address. Specific to Subnet IP (SNIP) address.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ospf</b>
Use this option to enable or disable OSPF on this IP address for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>bgp</b>
Use this option to enable or disable BGP on this IP address for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rip</b>
Use this option to enable or disable RIP on this IP address for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>hostRoute</b>
Advertise a route for the VIP address using the dynamic routing protocols running on the NetScaler appliance.
Possible values: ENABLED, DISABLED

<b>hostRtGw</b>
IP address of the gateway of the route for this VIP address.
Default value: -1

<b>metric</b>
Integer value to add to or subtract from the cost of the route advertised for the VIP address.
Minimum value: -16777215

<b>vserverRHILevel</b>
Advertise the route for the Virtual IP (VIP) address on the basis of the state of the virtual servers associated with that VIP.
* NONE - Advertise the route for the VIP address, regardless of the state of the virtual servers associated with the address.
* ONE VSERVER - Advertise the route for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - Advertise the route for the VIP address if all of the associated virtual servers are in UP state.
* VSVR_CNTRLD - Advertise the route for the VIP address according to the  RHIstate (RHI STATE) parameter setting on all the associated virtual servers of the VIP address along with their states.
When Vserver RHI Level (RHI) parameter is set to VSVR_CNTRLD, the following are different RHI behaviors for the VIP address on the basis of RHIstate (RHI STATE) settings on the virtual servers associated with the VIP address:
* If you set RHI STATE to PASSIVE on all virtual servers, the NetScaler ADC always advertises the route for the VIP address.
* If you set RHI STATE to ACTIVE on all virtual servers, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers is in UP state.
*If you set RHI STATE to ACTIVE on some and PASSIVE on others, the NetScaler ADC advertises the route for the VIP address if at least one of the associated virtual servers, whose RHI STATE set to ACTIVE, is in UP state.
Possible values: ONE_VSERVER, ALL_VSERVERS, NONE, VSVR_CNTRLD
Default value: RHI_STATE_ONE

<b>vserverRHIMode</b>
Advertise the route for the Virtual IP (VIP) address using dynamic routing protocols or using RISE
* DYNMAIC_ROUTING - Advertise the route for the VIP address using dynamic routing protocols (default)
* RISE - Advertise the route for the VIP address using RISE.
Possible values: DYNAMIC_ROUTING, RISE
Default value: RHI_MODE_DYNAMIC

<b>ospfLSAType</b>
Type of LSAs to be used by the OSPF protocol, running on the NetScaler appliance, for advertising the route for this VIP address.
Possible values: TYPE1, TYPE5
Default value: DISABLED

<b>ospfArea</b>
ID of the area in which the type1 link-state advertisements (LSAs) are to be advertised for this virtual IP (VIP)  address by the OSPF protocol running on the NetScaler appliance.  When this parameter is not set, the VIP is advertised on all areas.
Default value: -1
Maximum value: 4294967294LU

<b>state</b>
Enable or disable the IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>vrID</b>
A positive integer that uniquely identifies a VMAC address for binding to this VIP address. This binding is used to set up NetScaler appliances in an active-active configuration using VRRP.
Minimum value: 1
Maximum value: 255

<b>icmpResponse</b>
Respond to ICMP requests for a Virtual IP (VIP) address on the basis of the states of the virtual servers associated with that VIP. Available settings function as follows:
* NONE - The NetScaler appliance responds to any ICMP request for the VIP address, irrespective of the states of the virtual servers associated with the address.
* ONE VSERVER - The NetScaler appliance responds to any ICMP request for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - The NetScaler appliance responds to any ICMP request for the VIP address if all of the associated virtual servers are in UP state.
* VSVR_CNTRLD - The behavior depends on the ICMP VSERVER RESPONSE setting on all the associated virtual servers.
The following settings can be made for the ICMP VSERVER RESPONSE parameter on a virtual server:
* If you set ICMP VSERVER RESPONSE to PASSIVE on all virtual servers, NetScaler always responds.
* If you set ICMP VSERVER RESPONSE to ACTIVE on all virtual servers, NetScaler responds if even one virtual server is UP.
* When you set ICMP VSERVER RESPONSE to ACTIVE on some and PASSIVE on others, NetScaler responds if even one virtual server set to ACTIVE is UP.
Possible values: NONE, ONE_VSERVER, ALL_VSERVERS, VSVR_CNTRLD
Default value: NS_IP_NONE

<b>ownerNode</b>
The owner node in a Cluster for this IP address. Owner node can vary from 0 to 31. If ownernode is not specified then the IP is treated as Striped IP.
Default value: 255
Minimum value: 0

<b>arpResponse</b>
Respond to ARP requests for a Virtual IP (VIP) address on the basis of the states of the virtual servers associated with that VIP. Available settings function as follows:
* NONE - The NetScaler appliance responds to any ARP request for the VIP address, irrespective of the states of the virtual servers associated with the address.
* ONE VSERVER - The NetScaler appliance responds to any ARP request for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - The NetScaler appliance responds to any ARP request for the VIP address if all of the associated virtual servers are in UP state.
Possible values: NONE, ONE_VSERVER, ALL_VSERVERS
Default value: NS_IP_NONE

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

add ns ip 10.102.4.123 255.255.255.0

##rm ns ip

Removes an IPv4 address configured on the NetScaler appliance.


##Synopsys

rm ns ip &lt;IPAddress>@ [-td &lt;positive_integer>]


##Arguments

<b>IPAddress</b>
IPv4 address that you want to remove.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

rm ns ip 10.102.4.123

##set ns ip

Modifies the parameters of an IPv4 address configured on the NetScaler appliance.


##Synopsys

set ns ip (&lt;IPAddress>@  [-td &lt;positive_integer>]) [-netmask &lt;netmask>] [-arp ( ENABLED | DISABLED )] [-icmp ( ENABLED | DISABLED )] [-vServer ( ENABLED | DISABLED )] [-telnet ( ENABLED | DISABLED )] [-ftp ( ENABLED | DISABLED )] [-gui &lt;gui>] [-ssh ( ENABLED | DISABLED )] [-snmp ( ENABLED | DISABLED )] [-mgmtAccess ( ENABLED | DISABLED )] [-restrictAccess ( ENABLED | DISABLED )] [-dynamicRouting ( ENABLED | DISABLED )] [-hostRoute ( ENABLED | DISABLED )  [-hostRtGw &lt;ip_addr>]  [-metric &lt;integer>]  [-vserverRHILevel &lt;vserverRHILevel>]  [-vserverRHIMode ( DYNAMIC_ROUTING | RISE )]  [-ospfLSAType ( TYPE1 | TYPE5 )  [-ospfArea &lt;positive_integer>]]] [-vrID &lt;positive_integer>] [-icmpResponse &lt;icmpResponse>] [-arpResponse &lt;arpResponse>]


##Arguments

<b>IPAddress</b>
IPv4 address whose parameters you want to modify.

<b>netmask</b>
Subnet mask associated with the IP address.

<b>arp</b>
Respond to ARP requests for this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>icmp</b>
Respond to ICMP requests for this IP address.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>vServer</b>
Use this option to set (enable or disable) the virtual server attribute for this IP address.
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
Allow secure shell (SSH) access to this IP address.
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
Block access to nonmanagement applications on this IP. This option is applicable for MIPs, SNIPs, and NSIP, and is disabled by default. Nonmanagement applications can run on the underlying NetScaler Free BSD operating system.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dynamicRouting</b>
Allow dynamic routing on this IP address. Specific to Subnet IP (SNIP) address.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ospf</b>
The state of OSPF on this IP address for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>bgp</b>
The state of BGP on this IP address for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rip</b>
The state of RIP on this IP address for the entity.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>hostRoute</b>
Advertise a route for the VIP address using the dynamic routing protocols running on the NetScaler appliance.
Possible values: ENABLED, DISABLED

<b>vrID</b>
A positive integer that uniquely identifies a VMAC address for binding to this VIP address. This binding is used to set up NetScaler appliances in an active-active configuration using VRRP.
Minimum value: 1
Maximum value: 255

<b>icmpResponse</b>
Respond to ICMP requests for a Virtual IP (VIP) address on the basis of the states of the virtual servers associated with that VIP. Available settings function as follows:
* NONE - The NetScaler appliance responds to any ICMP request for the VIP address, irrespective of the states of the virtual servers associated with the address.
* ONE VSERVER - The NetScaler appliance responds to any ICMP request for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - The NetScaler appliance responds to any ICMP request for the VIP address if all of the associated virtual servers are in UP state.
* VSVR_CNTRLD - The behavior depends on the ICMP VSERVER RESPONSE setting on all the associated virtual servers.
The following settings can be made for the ICMP VSERVER RESPONSE parameter on a virtual server:
* If you set ICMP VSERVER RESPONSE to PASSIVE on all virtual servers, NetScaler always responds.
* If you set ICMP VSERVER RESPONSE to ACTIVE on all virtual servers, NetScaler responds if even one virtual server is UP.
* When you set ICMP VSERVER RESPONSE to ACTIVE on some and PASSIVE on others, NetScaler responds if even one virtual server set to ACTIVE is UP.
Possible values: NONE, ONE_VSERVER, ALL_VSERVERS, VSVR_CNTRLD
Default value: NS_IP_NONE

<b>arpResponse</b>
Respond to ARP requests for a Virtual IP (VIP) address on the basis of the states of the virtual servers associated with that VIP. Available settings function as follows:
* NONE - The NetScaler appliance responds to any ARP request for the VIP address, irrespective of the states of the virtual servers associated with the address.
* ONE VSERVER - The NetScaler appliance responds to any ARP request for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - The NetScaler appliance responds to any ARP request for the VIP address if all of the associated virtual servers are in UP state.
Possible values: NONE, ONE_VSERVER, ALL_VSERVERS
Default value: NS_IP_NONE



##Example

set ns ip 10.102.4.123 -arp ENABLED

##unset ns ip

Modifies the parameters of an IPv4 address configured on the NetScaler appliance..Refer to the set ns ip command for meanings of the arguments.


##Synopsys

unset ns ip &lt;IPAddress>@ [-td &lt;positive_integer>] [-ospfArea] [-hostRtGw] [-netmask] [-arp] [-icmp] [-vServer] [-telnet] [-ftp] [-gui] [-ssh] [-snmp] [-mgmtAccess] [-restrictAccess] [-dynamicRouting] [-hostRoute] [-metric] [-vserverRHILevel] [-vserverRHIMode] [-ospfLSAType] [-vrID] [-icmpResponse] [-arpResponse]


##Example

unset ns ip 10.102.4.123 -ospfArea

##enable ns ip

Enables the specified IP address configured on the NetScaler appliance.


##Synopsys

enable ns ip (&lt;IPAddress>@  [-td &lt;positive_integer>])


##Arguments

<b>IPAddress</b>
IP address that you want to enable.



##Example

enable ns ip 10.10.10.10

##disable ns ip

Disables the specified IP address configured on the NetScaler appliance.


##Synopsys

disable ns ip (&lt;IPAddress>@  [-td &lt;positive_integer>])


##Arguments

<b>IPAddress</b>
IP address that you want to disable.



##Example

disable ns ip 10.10.10.10

##show ns ip

Displays settings of all the IPv4 addresses or of the specified IPv4 address configured on the NetScaler appliance. To display settings of all the IPv4 addresses, run the command without any parameters. To display settings of a particular IPv4 address, specify the IPv4 address.


##Synopsys

show ns ip [&lt;IPAddress>  [-td &lt;positive_integer>]] [-type &lt;type>]


##Arguments

<b>IPAddress</b>
IPv4 address whose details you want the NetScaler appliance to display.

<b>type</b>
Display the settings of all IPv4 addresses of a particular type.
Possible values: SNIP, VIP, NSIP, GSLBsiteIP, CLIP
Default value: 0

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>netmask</b>
The netmask of this IP.

<b>flags</b>
The flags for this entry.

<b>ipAttribute</b>

<b>arp</b>
Whether arp is enabled or disabled.

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

<b>dynamicRouting</b>
Whether dynamic routing is enabled or disabled.

<b>bgp</b>
Whether bgp is enabled or disabled.NOTE: This attribute is deprecated.

<b>ospf</b>
Whether ospf is enabled or disabled.NOTE: This attribute is deprecated.

<b>rip</b>
Whether rip is enabled or disabled.NOTE: This attribute is deprecated.

<b>hostRoute</b>
Whether host route is enabled or disabled.

<b>hostRtGw</b>
Gateway used for advertising host route.

<b>hostRtGwAct</b>
Actual Gateway used for advertising host route.

<b>metric</b>
The metric value added or subtracted from the cost of the hostroute.

<b>ospfArea</b>
The area ID of the area in which OSPF Type1 LSAs are advertised. When ospfArea if not set, LSAs are advertised on all areas.NOTE: This attribute is deprecated.Replaced by ospfAreaval

<b>ospfAreaval</b>
The area ID of the area in which OSPF Type1 LSAs are advertised.

<b>vserverRHILevel</b>
The rhi level for this IP.

<b>vserverRHIMode</b>
The rhi advertisement mode for this IP.

<b>VIPrtadv2BSD</b>
Whether this route is advertised to FreeBSD

<b>VIPvserCount</b>
Number of vservers bound to this VIP

<b>VIPvserDownCount</b>
Number of vservers bound to this VIP, which are down

<b>VIPvsrvrRHIActiveCount</b>
Number of vservers that have RHI state ACTIVE

<b>VIPvsrvrRHIActiveUpCount</b>
Number of vservers that have RHI state ACTIVE, which are UP

<b>ospfLSAType</b>
The ospf lsa type to use while advertising this IP.

<b>state</b>
Whether this ip is enabled or disabled.

<b>freePorts</b>
Number of free Ports available on this IP

<b>vrID</b>
A positive integer that uniquely identifies a VMAC address for binding to this VIP address. This binding is used to set up NetScaler appliances in an active-active configuration using VRRP.

<b>riseRhiMsgCode</b>
The code indicating the rise rhi status.

<b>ipType</b>

<b>icmpResponse</b>
Respond to ICMP requests for a Virtual IP (VIP) address on the basis of the states of the virtual servers associated with that VIP. Available settings function as follows:
* NONE - The NetScaler appliance responds to any ICMP request for the VIP address, irrespective of the states of the virtual servers associated with the address.
* ONE VSERVER - The NetScaler appliance responds to any ICMP request for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - The NetScaler appliance responds to any ICMP request for the VIP address if all of the associated virtual servers are in UP state.
* VSVR_CNTRLD - The behavior depends on the ICMP VSERVER RESPONSE setting on all the associated virtual servers.
The following settings can be made for the ICMP VSERVER RESPONSE parameter on a virtual server:
* If you set ICMP VSERVER RESPONSE to PASSIVE on all virtual servers, NetScaler always responds.
* If you set ICMP VSERVER RESPONSE to ACTIVE on all virtual servers, NetScaler responds if even one virtual server is UP.
* When you set ICMP VSERVER RESPONSE to ACTIVE on some and PASSIVE on others, NetScaler responds if even one virtual server set to ACTIVE is UP.

<b>ownerNode</b>
The owner node in a Cluster for this IP address. Owner node can vary from 0 to 31. If ownernode is not specified then the IP is treated as Striped IP.

<b>arpResponse</b>
Respond to ARP requests for a Virtual IP (VIP) address on the basis of the states of the virtual servers associated with that VIP. Available settings function as follows:
* NONE - The NetScaler appliance responds to any ARP request for the VIP address, irrespective of the states of the virtual servers associated with the address.
* ONE VSERVER - The NetScaler appliance responds to any ARP request for the VIP address if at least one of the associated virtual servers is in UP state.
* ALL VSERVER - The NetScaler appliance responds to any ARP request for the VIP address if all of the associated virtual servers are in UP state.

<b>stateflag</b>

<b>cfgflags</b>
This contains the flags for IP in DB

<b>ipRefcount</b>
Used to keep reference count of IP

<b>devno</b>

<b>count</b>



##Example

show ns ipIpaddress	   Type 		Mode	Arp 	Icmp	Vserver State  Owner---------	   ---- 		----	--- 	----	------- -----  -----1)10.102.169.16 Cluster IP   Active	Enabled Enabled NA		Enabled	Configuration Coordinator2)10.102.169.18 NetScaler IP Active Enabled Enabled NA		Enabled 13)10.102.169.19 NetScaler IP Active Enabled Enabled NA      Enabled 24)10.102.169.17 VIP          Active Enabled Enabled Enabled Enabled ALL

