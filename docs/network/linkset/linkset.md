#linkset

The following operations can be performed on "linkset":


[add](#add-linkset) | [rm](#rm-linkset) | [bind](#bind-linkset) | [unbind](#unbind-linkset) | [show](#show-linkset)

##add linkset

Adds a linkset to the NetScaler cluster.


##Synopsys

add linkset &lt;id>


##Arguments

<b>id</b>
Unique identifier for the linkset. Must be of the form LS/x, where x can be an integer from 1 to 32.



##Example

add linkset LS/1

##rm linkset

Removes a linkset from the cluster.


##Synopsys

rm linkset &lt;id>


##Arguments

<b>id</b>
ID of the linkset to be removed.



##Example

rm linkset LS/1

##bind linkset

Binds interfaces to the linkset.


##Synopsys

bind linkset &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
ID of the linkset to which to bind the interfaces.

<b>ifnum</b>
The interfaces to be bound to the linkset.



##Example

bind linkset LS/1 -ifnum 1/1/1

##unbind linkset

Unbinds interfaces from the linkset.


##Synopsys

unbind linkset &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
ID of the linkset from which to unbind the interfaces.

<b>ifnum</b>
Interfaces to be unbound from the linkset.



##Example

unbind linkset LS/1 -ifnum 1/1/1

##show linkset

Displays information about all linksets, or displays information about the specified linkset.


##Synopsys

show linkset [&lt;id>]


##Arguments

<b>id</b>
ID of the linkset for which to display information. If an ID is not provided, the display includes information about all linksets that are available in the cluster.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>ifnum</b>
The interfaces to be bound to the linkset.

<b>stateflag</b>
state flag

<b>devno</b>

<b>count</b>



##Example

show linkset

