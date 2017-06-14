#ns acls

The following operations can be performed on "ns acls":


[renumber](#renumber-ns-acls) | [clear](#clear-ns-acls) | [apply](#apply-ns-acls)

##renumber ns acls

Renumbers the priorities of extended ACL rules to multiples of 10. To commit this operation, you must apply the extended ACLs.Enables you to assign a new extended ACL rule a priority that is between two existing, consecutively numbered priorities. For example, if two extended ACLs, ACL1 and ACL2, have priorities 2 and 3 renumbering changes those priorities to 20 and 30. You can then add ACL3 with priority 25.


##Synopsys

renumber ns acls


##Example

renumber acls

##clear ns acls

Removes all simple ACL rules from the NetScaler appliance. This operation does not require an explicit apply.


##Synopsys

clear ns acls


##Example

clear ns acls

##Related Commands

<ul><li><a href="../../..//">add ns acl</a></li><li><a href="../../..//">rm ns acl</a></li></ul>



##apply ns acls

Updates the extended ACL rule's memory tree (lookup table), adding any new extended ACL rules and applying any modifications to existing ACL rules. The lookup table includes the configuration of all the extended ACL rules on the NetScaler appliance. The NetScaler appliance uses the lookup table (not the configuration file) to filter the incoming IPv4 packets.


##Synopsys

apply ns acls


##Example

apply ns acls

##Related Commands

<ul><li><a href="../../..//">add ns acl</a></li><li><a href="../../..//">rm ns acl</a></li><li><a href="../../..//">set ns acl</a></li><li><a href="../../..//">enable ns acl</a></li><li><a href="../../..//">disable ns acl</a></li></ul>



