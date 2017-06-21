#arpparam

The following operations can be performed on "arpparam":


[set](#set-arpparam) | [unset](#unset-arpparam) | [show](#show-arpparam)

##set arpparam

Sets a global time-out value for dynamic ARP entries.


##Synopsys

set arpparam [-timeout &lt;positive_integer>] [-spoofValidation ( ENABLED | DISABLED )]


##Arguments

<b>timeout</b>
Time-out value (aging time) for the dynamically learned ARP entries, in seconds. The new value applies only to ARP entries that are dynamically learned after the new value is set. Previously existing ARP entries expire after the previously configured aging time.
Default value: 1200
Minimum value: 5
Maximum value: 1200

<b>spoofValidation</b>
enable/disable arp spoofing validation
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set arpparam -timeout 200 -spoofvalidate ENABLE

##unset arpparam

Use this command to remove  arpparam settings.Refer to the set  arpparam command for meanings of the arguments.


##Synopsys

unset arpparam [-timeout] [-spoofValidation]


##show arpparam

Display the global setting of dynamically learned ARP entries.


##Synopsys

show arpparam


##Outputs

<b>timeout</b>
The ARP table entry aging time, in seconds.

<b>spoofValidation</b>
enable/disable arp spoofing validation



##Example

show arpparam

