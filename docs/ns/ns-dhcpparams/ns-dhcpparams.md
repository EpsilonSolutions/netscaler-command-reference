#ns dhcpParams

The following operations can be performed on "ns dhcpParams":


[set](#set-ns-dhcpparams) | [unset](#unset-ns-dhcpparams) | [show](#show-ns-dhcpparams)

##set ns dhcpParams

Sets the DHCP client parameters.


##Synopsys

set ns dhcpParams [-dhcpClient ( ON | OFF )] [-saveroute ( ON | OFF )]


##Arguments

<b>dhcpClient</b>
Enables DHCP client to acquire IP address from the DHCP server in the next boot. When set to OFF, disables the DHCP client in the next boot.
Possible values: ON, OFF
Default value: OFF

<b>saveroute</b>
DHCP acquired routes are saved on the NetScaler appliance.
Possible values: ON, OFF
Default value: OFF



##unset ns dhcpParams

Use this command to remove ns dhcpParams settings.Refer to the set ns dhcpParams command for meanings of the arguments.


##Synopsys

unset ns dhcpParams [-dhcpClient] [-saveroute]


##show ns dhcpParams

Displays the parameters configured for the DHCP client.


##Synopsys

show ns dhcpParams


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>dhcpClient</b>
ON, if DHCP client active on next reboot, else OFF

<b>IPAddress</b>
DHCP acquired IP

<b>netmask</b>
DHCP acquired Netmask

<b>hostRtGw</b>
DHCP acquired Gateway

<b>running</b>
DHCP mode

<b>saveroute</b>
DHCP acquired gateway save flag



