#HA failover

The following operations can be performed on "HA failover":


##force HA failover

Forces an HA failover. Can be initiated from either node. A forced failover is not propagated or synchronized., Note: This command fails under any of the following conditions:* The secondary node is disabled or configured to remain secondary.* The primary node is configured to remain primary.* The state of the peer node is unknown.* You run the command on a standalone appliance.


##Synopsys

force HA failover [-force]


##Arguments

<b>force</b>
Force a failover without prompting for confirmation.



