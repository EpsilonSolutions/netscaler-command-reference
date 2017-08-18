#L2Param

The following operations can be performed on "L2Param":


[set](#set-l2param) | [unset](#unset-l2param) | [show](#show-l2param)

##set L2Param

Set Layer 2 related global settings on the NetScaler


##Synopsys

set L2Param [-mbfPeermacUpdate &lt;positive_integer>] [-maxBridgeCollision &lt;positive_integer>] [-bdggrpProxyArp ( ENABLED | DISABLED )] [-bdgSetting ( ENABLED | DISABLED )] [-garpOnVridIntf ( ENABLED | DISABLED )] [-macModeFwdMyPkt ( ENABLED | DISABLED )] [-useMyMAC ( ENABLED | DISABLED )] [-proxyArp ( ENABLED | DISABLED )] [-garpReply ( ENABLED | DISABLED )] [-mbfInstLearning ( ENABLED | DISABLED )] [-rstIntfOnHaFo ( ENABLED | DISABLED )] [-skipProxyingBsdTraffic ( ENABLED | DISABLED )] [-returnToEthernetSender ( ENABLED | DISABLED )] [-stopMacMoveUpdate ( ENABLED | DISABLED )] [-bridgeAgeTimeout &lt;positive_integer>]


##Arguments

<b>mbfPeermacUpdate</b>
When mbf_instant_learning is enabled, learn any changes in peer's MAC after this time interval, which is in 10ms ticks.
Default value: 10
Minimum value: 0

<b>maxBridgeCollision</b>
Maximum bridge collision for loop detection 
Default value: 20
Minimum value: 0

<b>bdggrpProxyArp</b>
Set/reset proxy ARP in bridge group deployment
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>bdgSetting</b>
Bridging settings for C2C behavior. If enabled, each PE will learn MAC entries independently. Otherwise, when L2 mode is ON, learned MAC entries on a PE will be broadcasted to all other PEs.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>garpOnVridIntf</b>
Send GARP messagess on VRID-configured interfaces upon failover 
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>macModeFwdMyPkt</b>
Allows MAC mode vserver to pick and forward the packets even if it is destined to NetScaler owned VIP.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>useMyMAC</b>
Use Netscaler MAC for all outgoing packets.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>proxyArp</b>
Proxies the ARP as Netscaler MAC for FreeBSD.
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
Control source parameters (IP and Port) for FreeBSD initiated traffic. If Enabled, source parameters are retained. Else proxy the source parameters based on next hop.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>returnToEthernetSender</b>
Return to ethernet sender.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>stopMacMoveUpdate</b>
Stop Update of server mac change to NAT sessions.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>bridgeAgeTimeout</b>
Time-out value for the bridge table entries, in seconds. The new value applies only to the entries that are dynamically learned after the new value is set. Previously existing bridge table entries expire after the previously configured time-out value.
Default value: 300
Minimum value: 60
Maximum value: 300



##unset L2Param

Use this command to remove  L2Param settings.Refer to the set  L2Param command for meanings of the arguments.


##Synopsys

unset L2Param [-mbfPeermacUpdate] [-maxBridgeCollision] [-bdggrpProxyArp] [-bdgSetting] [-garpOnVridIntf] [-macModeFwdMyPkt] [-useMyMAC] [-proxyArp] [-garpReply] [-mbfInstLearning] [-rstIntfOnHaFo] [-skipProxyingBsdTraffic] [-returnToEthernetSender] [-stopMacMoveUpdate] [-bridgeAgeTimeout]


##show L2Param

Displays the settings of global Layer 2 parameters on the NetScaler appliance.


##Synopsys

show L2Param


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
Bridging settings for C2C behavior. If enabled, each PE will learn MAC entries independently. Otherwise, when L2 mode is ON, learned MAC entries on a PE will be broadcasted to all other PEs.

<b>garpOnVridIntf</b>
Send GARP messagess on VRID-configured interfaces upon failover

<b>macModeFwdMyPkt</b>
Allows MAC mode vserver to pick and forward the packets even if it is destined to NetScaler owned VIP.

<b>useMyMAC</b>
Use Netscaler MAC for all outgoing packets.

<b>proxyArp</b>
Proxies the ARP as Netscaler MAC for FreeBSD.

<b>garpReply</b>
Set/reset REPLY form of GARP

<b>mbfInstLearning</b>
Enable instant learning of MAC changes in MBF mode.

<b>rstIntfOnHaFo</b>
Enable the reset interface upon HA failover.

<b>skipProxyingBsdTraffic</b>
Control source parameters (IP and Port) for FreeBSD initiated traffic. If Enabled, source parameters are retained. Else proxy the source parameters based on next hop.

<b>returnToEthernetSender</b>
Return to ethernet sender.

<b>stopMacMoveUpdate</b>
Stop Update of server mac change to NAT sessions.

<b>bridgeAgeTimeout</b>
Time-out value for the bridge table entries, in seconds. The new value applies only to the entries that are dynamically learned after the new value is set. Previously existing bridge table entries expire after the previously configured time-out value.



