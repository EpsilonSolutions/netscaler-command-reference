#rdp serverprofile

The following operations can be performed on "rdp serverprofile":


[add](#add-rdp-serverprofile) | [set](#set-rdp-serverprofile) | [unset](#unset-rdp-serverprofile) | [show](#show-rdp-serverprofile) | [rm](#rm-rdp-serverprofile)

##add rdp serverprofile

Add an rdp server profile.


##Synopsys

add rdp serverprofile &lt;name> [-rdpIP &lt;ip_addr|ipv6_addr|*>] [-rdpPort &lt;positive_integer>] -psk 


##Arguments

<b>name</b>
The name of the rdp server profile

<b>rdpIP</b>
IPv4 or IPv6 address of RDP listener. This terminates client RDP connections.

<b>rdpPort</b>
TCP port on which the RDP connection is established.
Default value: 3389
Minimum value: 1
Maximum value: 65535

<b>psk</b>
Pre shared key value



##set rdp serverprofile

Modifies the specified parameters for RDP profile.


##Synopsys

set rdp serverprofile &lt;name> [-rdpIP &lt;ip_addr|ipv6_addr|*>] [-rdpPort &lt;positive_integer>] [-psk ]


##Arguments

<b>name</b>
The name of the rdp server profile

<b>rdpIP</b>
IPv4 or IPv6 address of RDP listener. This terminates client RDP connections.

<b>rdpPort</b>
TCP port on which the RDP connection is established.
Default value: 3389
Minimum value: 1
Maximum value: 65535

<b>psk</b>
Pre shared key value



##unset rdp serverprofile

Use this command to remove rdp serverprofile settings.Refer to the set rdp serverprofile command for meanings of the arguments.


##Synopsys

unset rdp serverprofile &lt;name> [-rdpIP] [-rdpPort] [-psk]


##show rdp serverprofile

Display all rdp profiles


##Synopsys

show rdp serverprofile [&lt;name>]


##Arguments

<b>name</b>
The name of the rdp server profile



##Outputs

<b>rdpIP</b>
IPv4 or IPv6 address of RDP listener. This terminates client RDP connections.

<b>rdpPort</b>
TCP port on which the RDP connection is established.

<b>psk</b>
Pre shared key value

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show rdp profile

##rm rdp serverprofile

Remove an rdp server profile


##Synopsys

rm rdp serverprofile &lt;name>


##Arguments

<b>name</b>
The name of the rdp server profile.



##Example

rm rdp serverprofile 

