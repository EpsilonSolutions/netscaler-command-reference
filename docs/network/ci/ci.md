#ci

The following operations can be performed on "ci":


##show ci

Displays all the critical interfaces of the NetScaler appliance. In a High Availability configuration, an interface that has HA MON enabled and is not bound to any FIS, is a critical interface. Failure of any critical interface triggers HA failover.


##Synopsys

show ci


##Outputs

<b>ifaces</b>
Interfaces that are critical for the appliance to operate in high availability mode.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

&gt;show ciCritical Interfaces: LO/1 1/2

