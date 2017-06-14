#ns hostName

The following operations can be performed on "ns hostName":


[set](#set-ns-hostname) | [show](#show-ns-hostname)

##set ns hostName

Sets the hostname for the NetScaler appliance. The hostname is displayed on the shell prompt.


##Synopsys

set ns hostName &lt;hostName> [-ownerNode &lt;positive_integer>]


##Arguments

<b>hostName</b>
Host name for the NetScaler appliance.

<b>ownerNode</b>
ID of the cluster node for which you are setting the hostname. Can be configured only through the cluster IP address.
Default value: 255
Minimum value: 0
Maximum value: 31



##Example

set ns hostname nspri

##show ns hostName

Displays the host name of the system.


##Synopsys

show ns hostName


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>hostName</b>
Host name

<b>ownerNode</b>
ID of the cluster node for which you are setting the hostname. Can be configured only through the cluster IP address.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ns hostname

