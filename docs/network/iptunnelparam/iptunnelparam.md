#ipTunnelParam

The following operations can be performed on "ipTunnelParam":


[set](#set-iptunnelparam) | [unset](#unset-iptunnelparam) | [show](#show-iptunnelparam)

##set ipTunnelParam

Sets global parameters of IPv4 tunnels on the NetScaler appliance.


##Synopsys

set ipTunnelParam [-srcIP &lt;ip_addr>] [-dropFrag ( YES | NO )] [-dropFragCpuThreshold &lt;positive_integer>] [-srcIPRoundRobin ( YES | NO )] [-enableStrictRx ( YES | NO )] [-enableStrictTx ( YES | NO )]


##Arguments

<b>srcIP</b>
Common source-IP address for all tunnels. For a specific tunnel, this global setting is overridden if you have specified another source IP address. Must be a MIP or SNIP address.

<b>dropFrag</b>
Drop any IP packet that requires fragmentation before it is sent through the tunnel.
Possible values: YES, NO
Default value: NO

<b>dropFragCpuThreshold</b>
Threshold value, as a percentage of CPU usage, at which to drop packets that require fragmentation to use the IP tunnel. Applies only if dropFragparameter is set to NO. The default value, 0, specifies that this parameter is not set.
Minimum value: 1
Maximum value: 100

<b>srcIPRoundRobin</b>
Use a different source IP address for each new session through a particular IP tunnel, as determined by round robin selection of one of the SNIP addresses. This setting is ignored if a common global source IP address has been specified for all the IP tunnels. This setting does not apply to a tunnel for which a source IP address has been specified.
Possible values: YES, NO
Default value: NO

<b>enableStrictRx</b>
Strict PBR check for IPSec packets received through tunnel
Possible values: YES, NO
Default value: NO

<b>enableStrictTx</b>
Strict PBR check for packets to be sent IPSec protected
Possible values: YES, NO
Default value: NO



##Example

set ipTunnelParam -srcIP 10.100.20.48 -dropFrag YES -dropFragCpuThreshold 95

##unset ipTunnelParam

Use this command to remove  ipTunnelParam settings.Refer to the set  ipTunnelParam command for meanings of the arguments.


##Synopsys

unset ipTunnelParam [-srcIP] [-dropFrag] [-dropFragCpuThreshold] [-srcIPRoundRobin] [-enableStrictRx] [-enableStrictTx]


##show ipTunnelParam

Display the IP Tunnel global settings on the NetScaler


##Synopsys

show ipTunnelParam


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>srcIP</b>
Common source-IP address for all tunnels. For a specific tunnel, this global setting is overridden if you have specified another source IP address. Must be a MIP or SNIP address.

<b>dropFrag</b>
Drop any IP packet that requires fragmentation before it is sent through the tunnel.

<b>dropFragCpuThreshold</b>
Threshold value, as a percentage of CPU usage, at which to drop packets that require fragmentation to use the IP tunnel. Applies only if dropFragparameter is set to NO. The default value, 0, specifies that this parameter is not set.

<b>srcIPRoundRobin</b>
Use a different source IP address for each new session through a particular IP tunnel, as determined by round robin selection of one of the SNIP addresses. This setting is ignored if a common global source IP address has been specified for all the IP tunnels. This setting does not apply to a tunnel for which a source IP address has been specified.

<b>enableStrictRx</b>
Strict PBR check for IPSec packets received through tunnel

<b>enableStrictTx</b>
Strict PBR check for packets to be sent IPSec protected



##Example

Tunnel Source IP: 10.100.20.48Drop if Fragmentation Needed: YESCPU usage threshold to avoid fragmentation: 95

