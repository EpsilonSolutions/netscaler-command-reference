#vpn pcoipProfile

The following operations can be performed on "vpn pcoipProfile":


[add](#add-vpn-pcoipprofile) | [rm](#rm-vpn-pcoipprofile) | [set](#set-vpn-pcoipprofile) | [unset](#unset-vpn-pcoipprofile) | [show](#show-vpn-pcoipprofile)

##add vpn pcoipProfile

Creates an PCoIP profile


##Synopsys

add vpn pcoipProfile &lt;name> -conServerUrl &lt;URL> [-icvVerification ( ENABLED | DISABLED )] [-sessionIdleTimeout &lt;positive_integer>]


##Arguments

<b>name</b>
name of PCoIP profile

<b>conServerUrl</b>
Connection server URL

<b>icvVerification</b>
ICV verification for PCOIP transport packets.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessionIdleTimeout</b>
PCOIP Idle Session timeout
Default value: 180
Minimum value: 30
Maximum value: 240



##rm vpn pcoipProfile

Removes a previously created PCoIP profile.


##Synopsys

rm vpn pcoipProfile &lt;name>


##Arguments

<b>name</b>
Name of PCoIP profile to remove



##set vpn pcoipProfile

Modifies the specified parameters for PCoIP profile.


##Synopsys

set vpn pcoipProfile &lt;name> [-conServerUrl &lt;URL>] [-icvVerification ( ENABLED | DISABLED )] [-sessionIdleTimeout &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the PCoIP profile

<b>conServerUrl</b>
Connection server URL

<b>icvVerification</b>
ICV verification for PCOIP transport packets.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessionIdleTimeout</b>
PCOIP Idle Session timeout
Default value: 180
Minimum value: 30
Maximum value: 240



##unset vpn pcoipProfile

Use this command to remove vpn pcoipProfile settings.Refer to the set vpn pcoipProfile command for meanings of the arguments.


##Synopsys

unset vpn pcoipProfile &lt;name> [-icvVerification] [-sessionIdleTimeout]


##show vpn pcoipProfile

Displays information on PCoIP profile


##Synopsys

show vpn pcoipProfile [&lt;name>]


##Arguments

<b>name</b>
name of PCoIP profile.



##Outputs

<b>conServerUrl</b>
Connection server URL

<b>icvVerification</b>
ICV verification for PCOIP transport packets.

<b>sessionIdleTimeout</b>
PCOIP Idle Session timeout

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show vpn pcoipprofile Prof1

