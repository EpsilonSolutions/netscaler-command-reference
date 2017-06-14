#L4Param

The following operations can be performed on "L4Param":


[set](#set-l4param) | [unset](#unset-l4param) | [show](#show-l4param)

##set L4Param

Set Layer 4 related global settings on the NetScaler


##Synopsys

set L4Param [-l2ConnMethod &lt;l2ConnMethod>] [-l4switch ( ENABLED | DISABLED )]


##Arguments

<b>l2ConnMethod</b>
Layer 2 connection method based on the combination of  channel number, MAC address and VLAN. It is tuned with l2conn param of lb vserver. If l2conn of lb vserver is ON then method specified here will be used to identify a connection in addition to the 4-tuple (&lt;source IP&gt;:&lt;source port&gt;::&lt;destination IP&gt;:&lt;destination port&gt;).
Possible values: Channel, Vlan, VlanChannel, Mac, MacChannel, MacVlan, MacVlanChannel
Default value: NS_L2CONN_MAC_VLAN_CHAN

<b>l4switch</b>
In L4 switch topology, always clients and servers are on the same side. Enable l4switch to allow such connections.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set l4param

##unset L4Param

Use this command to remove  L4Param settings.Refer to the set  L4Param command for meanings of the arguments.


##Synopsys

unset L4Param [-l2ConnMethod] [-l4switch]


##show L4Param

Displays the settings of global Layer 4 parameters.


##Synopsys

show L4Param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>l2ConnMethod</b>
Layer 2 connection method based on the combination of  channel number, MAC address and VLAN. It is tuned with l2conn param of lb vserver. If l2conn of lb vserver is ON then method specified here will be used to identify a connection in addition to the 4-tuple (&lt;source IP>:&lt;source port>::&lt;destination IP>:&lt;destination port>).

<b>l4switch</b>
In L4 switch topology, always clients and servers are on the same side. Enable l4switch to allow such connections.



