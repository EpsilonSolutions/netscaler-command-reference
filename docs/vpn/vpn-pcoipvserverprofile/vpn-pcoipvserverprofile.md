#vpn pcoipVserverProfile

The following operations can be performed on "vpn pcoipVserverProfile":


[add](#add-vpn-pcoipvserverprofile) | [rm](#rm-vpn-pcoipvserverprofile) | [set](#set-vpn-pcoipvserverprofile) | [unset](#unset-vpn-pcoipvserverprofile) | [show](#show-vpn-pcoipvserverprofile)

##add vpn pcoipVserverProfile

Creates an PCoIP vserver profile


##Synopsys

add vpn pcoipVserverProfile &lt;name> -loginDomain &lt;string> [-udpPort &lt;port|*>]


##Arguments

<b>name</b>
name of PCoIP vserver profile

<b>loginDomain</b>
Login domain for PCoIP users

<b>udpPort</b>
UDP port for PCoIP data traffic
Default value: 4172



##rm vpn pcoipVserverProfile

Removes a previously created PCoIP vserver profile.


##Synopsys

rm vpn pcoipVserverProfile &lt;name>


##Arguments

<b>name</b>
Name of PCoIP vserver profile to remove



##set vpn pcoipVserverProfile

Modifies the specified parameters for PCoIP vserver profile.


##Synopsys

set vpn pcoipVserverProfile &lt;name> [-udpPort &lt;port|*>] [-loginDomain &lt;string>]


##Arguments

<b>name</b>
Name for the PCoIP session profile

<b>udpPort</b>
UDP port for PCoIP data traffic
Default value: 4172

<b>loginDomain</b>
Login domain for PCoIP users



##unset vpn pcoipVserverProfile

Use this command to remove vpn pcoipVserverProfile settings.Refer to the set vpn pcoipVserverProfile command for meanings of the arguments.


##Synopsys

unset vpn pcoipVserverProfile &lt;name> -udpPort


##show vpn pcoipVserverProfile

Displays information on PCoIP vserver profile


##Synopsys

show vpn pcoipVserverProfile [&lt;name>]


##Arguments

<b>name</b>
name of PCoIP vserver profile.



##Outputs

<b>udpPort</b>
UDP port for PCoIP data traffic

<b>loginDomain</b>
Login domain for PCoIP users

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show vpn pcoipserverprofile Prof1

