#L2Param

The following operations can be performed on "L2Param":


[set](#set-l2param) | [unset](#unset-l2param) | [show](#show-l2param)

##set L2Param

Set Layer 2 related global settings on the NetScaler


##Synopsys

set L2Param [-mbfPeermacUpdate &lt;positive_integer>] [-maxBridgeCollision &lt;positive_integer>] [-bdggrpProxyArp ( ENABLED | DISABLED )] [-bdgSetting ( ENABLED | DISABLED )] [-garpOnVridIntf ( ENABLED | DISABLED )] [-macModeFwdMyPkt ( ENABLED | DISABLED )] [-useMyMAC ( ENABLED | DISABLED )] [-proxyArp ( ENABLED | DISABLED )] [-garpReply ( ENABLED | DISABLED )] [-mbfInstLearning ( ENABLED | DISABLED )] [-rstIntfOnHaFo ( ENABLED | DISABLED )] [-skipProxyingBsdTraffic ( ENABLED | DISABLED )] [-returnToEthernetSender ( ENABLED | DISABLED )]


##Arguments

<b>mbfPeermacUpdate</b>
When mbf_instant_learning is enabled, learn any changes in peer's MAC after this time interval, which is in 10ms ticks.
Default value: 10

<b>maxBridgeCollision</b>
Maximum bridge collision for loop detection 
Default value: 20

<b>bdggrpProxyArp</b>
Set/reset proxy ARP in bridge group deployment
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>bdgSetting</b>
Bridging settings for C2C behavior
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>garpOnVridIntf</b>
Send GARP messagess on VRID-configured interfaces upon failover 
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>macModeFwdMyPkt</b>
MAC mode vserver forward packets destined to VIPs.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>useMyMAC</b>
Set/reset cfg_use_my_mac 
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>proxyArp</b>
Set/reset cfg_proxy_arp_dr 
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>garpReply</b>
Set/reset REPLY form of GARP 
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mbfInstLearning</b>
Enable instant learning of MAC changes in MBF mode.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rstIntfOnHaFo</b>
Enable the reset interface upon HA failover.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>skipProxyingBsdTraffic</b>
Enable the proxying of FreeBSD traffic.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>returnToEthernetSender</b>
Return to ethernet sender.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset L2Param

Use this command to remove  L2Param settings.Refer to the set  L2Param command for meanings of the arguments.


##Synopsys

unset L2Param [-mbfPeermacUpdate] [-maxBridgeCollision] [-bdggrpProxyArp] [-bdgSetting] [-garpOnVridIntf] [-macModeFwdMyPkt] [-useMyMAC] [-proxyArp] [-garpReply] [-mbfInstLearning] [-rstIntfOnHaFo] [-skipProxyingBsdTraffic] [-returnToEthernetSender]


##show L2Param

Displays the settings of global Layer 2 parameters on the NetScaler appliance.


##Synopsys

show L2Param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>maxBridgeCollision</b>
Maximum bridge collision for loop detection

<b>linkMTU</b>
this MTU is used for Ready logo purpose, changing the Interface MTU at soft layer level.

<b>mbfPeermacUpdate</b>
When mbf_instant_learning is enabled, learn any changes in peer's MAC after this time interval, which is in 10ms ticks.

<b>bdggrpProxyArp</b>
Set/reset proxy ARP in bridge group deployment

<b>bdgSetting</b>
Bridging settings for C2C behavior

<b>garpOnVridIntf</b>
Send GARP messagess on VRID-configured interfaces upon failover

<b>macModeFwdMyPkt</b>
MAC mode vserver forward packets destined to VIPs.

<b>useMyMAC</b>
Set/reset cfg_use_my_mac

<b>proxyArp</b>
Set/reset cfg_proxy_arp_dr

<b>garpReply</b>
Set/reset REPLY form of GARP

<b>mbfInstLearning</b>
Enable instant learning of MAC changes in MBF mode.

<b>rstIntfOnHaFo</b>
Enable the reset interface upon HA failover.

<b>skipProxyingBsdTraffic</b>
Enable the proxying of FreeBSD traffic.

<b>returnToEthernetSender</b>
Return to ethernet sender.



