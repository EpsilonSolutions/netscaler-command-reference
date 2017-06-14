#fis

The following operations can be performed on "fis":


[add](#add-fis) | [rm](#rm-fis) | [bind](#bind-fis) | [unbind](#unbind-fis) | [show](#show-fis)

##add fis

Adds a failover interface set (FIS) to the NetScaler appliance. A FIS is a logical group of interfaces. In an HA configuration, using a FIS is a way to prevent failover by grouping interfaces so that, when one interface fails, other functioning interfaces are still available. A FIS can also be configured for the nodes of a NetScaler cluster.


##Synopsys

add fis &lt;name> [-ownerNode &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the FIS to be created. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ). Note: In a cluster setup, the FIS name on each node must be unique.

<b>ownerNode</b>
ID of the cluster node for which you are creating the FIS. Can be configured only through the cluster IP address.
Default value: VAL_NOT_SET
Minimum value: 0
Maximum value: 31



##rm fis

Removes an FIS from the NetScaler appliance. When an FIS is removed, its interfaces are marked as critical interfaces.


##Synopsys

rm fis &lt;name>


##Arguments

<b>name</b>
Name of the FIS that you want to remove from the NetScaler appliance.



##bind fis

Binds the specified interfaces to a FIS.


##Synopsys

bind fis &lt;name> &lt;ifnum> ...


##Arguments

<b>name</b>
The name of the FIS to which you want to bind interfaces.

<b>ifnum</b>
Interface to be bound to the FIS, specified in slot/port notation (for example, 1/3).



##unbind fis

Unbinds the specified interfaces from a FIS. An unbound interface becomes a critical interface if it is enabled and HA MON is on.


##Synopsys

unbind fis &lt;name> &lt;ifnum> ...


##Arguments

<b>name</b>
Name of the FIS from which to unbind interfaces.

<b>ifnum</b>
Interfaces to unbind from the FIS, specified in slot/port notation (for example, 1/3). Use spaces to separate multiple entries.



##show fis

Displays the configured FISs.


##Synopsys

show fis [&lt;name>]


##Arguments

<b>name</b>
The name of the FIS configured on the appliance.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>ifaces</b>
Interfaces to be bound to the FIS, in slot/port notation (for example, 1/3).

<b>stateflag</b>
Used internally for display.

<b>ifnum</b>
Interface to be bound to the FIS, specified in slot/port notation (for example, 1/3)

<b>ownerNode</b>
ID of the cluster node for which you are creating the FIS. Can be configured only through the cluster IP address.

<b>devno</b>

<b>count</b>



##Example

&gt;show fis1)      FIS: fis1        Member Interfaces : 1/1Done

