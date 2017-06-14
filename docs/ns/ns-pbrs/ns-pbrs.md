#ns pbrs

The following operations can be performed on "ns pbrs":


[renumber](#renumber-ns-pbrs) | [clear](#clear-ns-pbrs) | [apply](#apply-ns-pbrs)

##renumber ns pbrs

Renumbers the priorities of PBRs to multiples of 10.To commit this operation, you must apply the PBRs.Enables you to assign a new PBR a priority that is between two existing, consecutively numbered priorities. For example, if two PBRs, PBR1 and PBR2, have priorities 2 and 3 renumbering changes those priorities to 20 and 30. You can then add PBR3 with priority 25.


##Synopsys

renumber ns pbrs


##Example

renumber pbrs

##clear ns pbrs

Removes all PBRs from the NetScaler appliance. This operation does not require an explicit apply.


##Synopsys

clear ns pbrs


##Example

clear ns pbrs

##Related Commands

<ul><li><a href="../../..//">add ns pbr</a></li><li><a href="../../..//">rm ns pbr</a></li></ul>



##apply ns pbrs

Updates the PBR's memory tree (lookup table), adding any new PBR and applying any modifications to existing PBRs. The lookup table includes the configuration of all the extended PBRs on the NetScaler appliance. The NetScaler appliance uses the lookup table (not the configuration file) to filter the outgoing IPv4 packets.


##Synopsys

apply ns pbrs


##Example

apply ns pbrs

##Related Commands

<ul><li><a href="../../..//">add ns pbr</a></li><li><a href="../../..//">rm ns pbr</a></li><li><a href="../../..//">set ns pbr</a></li><li><a href="../../..//">enable ns pbr</a></li><li><a href="../../..//">disable ns pbr</a></li></ul>



