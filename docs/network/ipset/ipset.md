#ipset

The following operations can be performed on "ipset":


[add](#add-ipset) | [rm](#rm-ipset) | [bind](#bind-ipset) | [unbind](#unbind-ipset) | [show](#show-ipset)

##add ipset

Creates an IP set to which you can bind subnet IP (SNIP) or mapped IP (MIP) addresses that have been configured on the NetScaler appliance.


##Synopsys

add ipset &lt;name> [-td &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the IP set. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the IP set is created. Choose a name that helps identify the IP set.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

add ipset pool1

##rm ipset

Removes an IP set from the NetScaler appliance.


##Synopsys

rm ipset &lt;name> ...


##Arguments

<b>name</b>
Name of the IP set to be removed.



##Example

rm ipset pool1

##bind ipset

Binds specified IP addresses to an IP set.


##Synopsys

bind ipset &lt;name> &lt;IPAddress>@ ...


##Arguments

<b>name</b>
Name of the IP set to which to bind IP addresses.

<b>IPAddress</b>
SNIP or MIP addresses, configured on the NetScaler appliance, to be bound to the IP set. (If using the CLI, use spaces to separate multiple addresses.)



##Example

bind ipset ipset_1 10.102.1.10

##unbind ipset

Unbinds the associated IP addresses from an IP set.


##Synopsys

unbind ipset &lt;name> &lt;IPAddress>@ ...


##Arguments

<b>name</b>
Name of the IP set from which to unbind IP addresses.

<b>IPAddress</b>
IP addresses to be unbound from the IP set. (If using the CLI, use spaces to separate multiple addresses.)



##Example

unbind ipset ipset_1 10.102.1.10

##show ipset

Displays the settings of all IP sets configured on the NetScaler appliance, or of the specified IP set.


##Synopsys

show ipset [&lt;name>]


##Arguments

<b>name</b>
Name of the IP set whose details you want to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>IPAddress</b>
One or more IP addresses bound to the IP set.

<b>stateflag</b>
state flag

<b>flags</b>

<b>ipSetRefcount</b>
Used to keep reference count of IP

<b>devno</b>

<b>count</b>



##Example

show network ipset

