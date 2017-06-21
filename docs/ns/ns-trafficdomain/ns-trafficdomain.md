#ns trafficDomain

The following operations can be performed on "ns trafficDomain":


[add](#add-ns-trafficdomain) | [rm](#rm-ns-trafficdomain) | [clear](#clear-ns-trafficdomain) | [bind](#bind-ns-trafficdomain) | [unbind](#unbind-ns-trafficdomain) | [enable](#enable-ns-trafficdomain) | [disable](#disable-ns-trafficdomain) | [show](#show-ns-trafficdomain) | [stat](#stat-ns-trafficdomain)

##add ns trafficDomain

Configure Traffic Domain on the system.


##Synopsys

add ns trafficDomain &lt;td> [-aliasName &lt;string>] [-vmac ( ENABLED | DISABLED )]


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094

<b>aliasName</b>
Name of traffic domain  being added.

<b>vmac</b>
Associate the traffic domain with a VMAC address instead of with VLANs. The NetScaler ADC then sends the VMAC address of the traffic domain in all responses to ARP queries for network entities in that domain. As a result, the ADC can segregate subsequent incoming traffic for this traffic domain on the basis of the destination MAC address, because the destination MAC address is the VMAC address of the traffic domain. After creating entities on a traffic domain, you can easily manage and monitor them by performing traffic domain level operations.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add ns trafficDomain 1 -aliasName td1

##rm ns trafficDomain

Remove Traffic Domain configured.


##Synopsys

rm ns trafficDomain &lt;td>


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094



##Example

rm ns trafficDomain 1

##clear ns trafficDomain

Remove Traffic Domain configuration.


##Synopsys

clear ns trafficDomain &lt;td>


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094



##bind ns trafficDomain

bind vlan or bridgegroup entities with traffic domain.


##Synopsys

bind ns trafficDomain &lt;td> [-vlan &lt;positive_integer>] [-bridgegroup &lt;positive_integer>] [-vxlan &lt;positive_integer>]


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094

<b>vlan</b>
ID of the VLAN to bind to this traffic domain. More than one VLAN can be bound to a traffic domain, but the same VLAN cannot be a part of multiple traffic domains.
Minimum value: 1
Maximum value: 4094

<b>bridgegroup</b>
ID of the configured bridge to bind to this traffic domain. More than one bridge group can be bound to a traffic domain, but the same bridge group cannot be a part of multiple traffic domains.
Minimum value: 1
Maximum value: 1000

<b>vxlan</b>
ID of the VXLAN to bind to this traffic domain. More than one VXLAN can be bound to a traffic domain, but the same VXLAN cannot be a part of multiple traffic domains.
Minimum value: 1
Maximum value: 16777215



##Example

bind ns trafficDomain 1 -vlan 2

##unbind ns trafficDomain

Unbind vlan or bridgegroup entities from traffic domain


##Synopsys

unbind ns trafficDomain &lt;td> [-vlan &lt;positive_integer>] [-bridgegroup &lt;positive_integer>] [-vxlan &lt;positive_integer>]


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094

<b>vlan</b>
ID of the VLAN to bind to this traffic domain. More than one VLAN can be bound to a traffic domain, but the same VLAN cannot be a part of multiple traffic domains.
Minimum value: 1
Maximum value: 4094

<b>bridgegroup</b>
ID of the configured bridge to bind to this traffic domain. More than one bridge group can be bound to a traffic domain, but the same bridge group cannot be a part of multiple traffic domains.
Minimum value: 1
Maximum value: 1000

<b>vxlan</b>
ID of the VXLAN to bind to this traffic domain. More than one VXLAN can be bound to a traffic domain, but the same VXLAN cannot be a part of multiple traffic domains.
Minimum value: 1
Maximum value: 16777215



##Example

unbind ns trafficDomain 1 -vlan 2

##enable ns trafficDomain

Enable TrafficDomain.


##Synopsys

enable ns trafficDomain &lt;td>


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094



##Example

enable ns trafficdomain 1

##disable ns trafficDomain

Disable TrafficDomain.


##Synopsys

disable ns trafficDomain &lt;td>


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094



##Example

disable ns trafficdomain 1

##show ns trafficDomain

Display Traffic Domain configuration.


##Synopsys

show ns trafficDomain [&lt;td>]


##Arguments

<b>td</b>
Integer value that uniquely identifies a traffic domain.
Minimum value: 1
Maximum value: 4094



##Outputs

<b>aliasName</b>
Name of traffic domain  being added.

<b>vmac</b>
Associate the traffic domain with a VMAC address instead of with VLANs. The NetScaler ADC then sends the VMAC address of the traffic domain in all responses to ARP queries for network entities in that domain. As a result, the ADC can segregate subsequent incoming traffic for this traffic domain on the basis of the destination MAC address, because the destination MAC address is the VMAC address of the traffic domain. After creating entities on a traffic domain, you can easily manage and monitor them by performing traffic domain level operations.

<b>stateflag</b>
Used internally for display.

<b>vlan</b>
ID of the VLAN to bind to this traffic domain. More than one VLAN can be bound to a traffic domain, but the same VLAN cannot be a part of multiple traffic domains.

<b>vxlan</b>
ID of the VXLAN to bind to this traffic domain. More than one VXLAN can be bound to a traffic domain, but the same VXLAN cannot be a part of multiple traffic domains.

<b>bridgegroup</b>
ID of the configured bridge to bind to this traffic domain. More than one bridge group can be bound to a traffic domain, but the same bridge group cannot be a part of multiple traffic domains.

<b>state</b>
The state of TrafficDmain.

<b>devno</b>

<b>count</b>



##Example

An example of the output of the show trafficDomain command is as follows:1)      Traffic Domain: 1        Alias Name:     State: ENABLED        Vlans : 502)      Traffic Domain: 2		Alias Name:     State: ENABLED		Vlans : 2		Bridge Group : 1Done

##stat ns trafficDomain

Display statistics for Traffic Domains(s).


##Synopsys

stat ns trafficDomain [&lt;td>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>td</b>
An integer specifying the Traffic Domain ID. Possible values: 1 through 4094.
Minimum value: 1
Maximum value: 4094

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

<b>Packets received (TdRxPkts)</b>
Packets received on this TD.

<b>Packets sent (TdTxPkts)</b>
Packets transmitted from this TD.

<b>Packets dropped (TdDropPkts)</b>
Inbound packets dropped on this TD by reception.



##Example

stat ns trafficdomain 1

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../t-ns-part/t-ns-part">stat ns partition</a></li></ul>



