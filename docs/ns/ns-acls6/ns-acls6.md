#ns acls6

The following operations can be performed on "ns acls6":


[clear](#clear-ns-acls6) | [apply](#apply-ns-acls6) | [renumber](#renumber-ns-acls6)

##clear ns acls6

Removes all simple ACL6 rules from the NetScaler appliance. This operation does not require an explicit apply.


##Synopsys

clear ns acls6


##Example

clear ns acls6

##Related Commands

<ul><li><a href="../../..//">add ns acl6</a></li><li><a href="../../..//">rm ns acl6</a></li></ul>



##apply ns acls6

Updates the ACL6 rules' memory tree (lookup table), adding any new ACL6 rules and applying any modifications to existing ACL rules. The lookup table includes the configuration of all the ACL6 rules on the NetScaler appliance. The NetScaler appliance uses the lookup table (not the configuration file) to filter the incoming IPv4 packets.


##Synopsys

apply ns acls6


##Example

apply ns acls6

##Related Commands

<ul><li><a href="../../..//">add ns acl6</a></li><li><a href="../../..//">rm ns acl6</a></li><li><a href="../../..//">set ns acl6</a></li><li><a href="../../../s/s">enable ns acl6</a></li><li><a href="../../../ns/ns">disable ns acl6</a></li></ul>



##renumber ns acls6

Renumbers the priorities of ACL6 rules to multiples of 10. To commit this operation, you must apply the ACL6s.Enables you to assign a new ACL6 rule a priority that is between two existing, consecutively numbered priorities. For example, if two ACL6s, ACL6-1 and ACL6-2, have priorities 2 and 3 renumbering changes those priorities to 20 and 30. You can then add ACL6-3 with priority 25.


##Synopsys

renumber ns acls6


##Example

renumber acls6

