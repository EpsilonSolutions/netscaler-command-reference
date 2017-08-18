#vpn alwaysONProfile

The following operations can be performed on "vpn alwaysONProfile":


[add](#add-vpn-alwaysonprofile) | [rm](#rm-vpn-alwaysonprofile) | [set](#set-vpn-alwaysonprofile) | [unset](#unset-vpn-alwaysonprofile) | [show](#show-vpn-alwaysonprofile)

##add vpn alwaysONProfile

Creates an AlwaysON profile


##Synopsys

add vpn alwaysONProfile &lt;name> [-networkAccessOnVPNFailure ( onlyToGateway | fullAccess )] [-clientControl ( ALLOW | DENY )] [-locationBasedVPN ( Remote | Everywhere )]


##Arguments

<b>name</b>
name of AlwaysON profile

<b>networkAccessOnVPNFailure</b>
Option to block network traffic when tunnel is not established(and the config requires that tunnel be established). When set to onlyToGateway, the network traffic to and from the client (except Gateway IP) is blocked. When set to fullAccess, the network traffic is not blocked
Possible values: onlyToGateway, fullAccess
Default value: fullAccess,

<b>clientControl</b>
Allow/Deny user to log off and connect to another Gateway
Possible values: ALLOW, DENY
Default value: DENY

<b>locationBasedVPN</b>
Option to decide if tunnel should be established when in enterprise network. When locationBasedVPN is remote, client tries to detect if it is located in enterprise network or not and establishes the tunnel if not in enterprise network. Dns suffixes configured using -add dns suffix- are used to decide if the client is in the enterprise network or not. If the resolution of the DNS suffix results in private IP, client is said to be in enterprise network. When set to EveryWhere, the client skips the check to detect if it is on the enterprise network and tries to establish the tunnel
Possible values: Remote, Everywhere
Default value: Remote



##rm vpn alwaysONProfile

Removes a previously created AlwaysON device profile.


##Synopsys

rm vpn alwaysONProfile &lt;name>


##Arguments

<b>name</b>
Name of AlwaysON profile to remove



##set vpn alwaysONProfile

Modifies the specified parameters for AlwaysON profile.


##Synopsys

set vpn alwaysONProfile &lt;name> [-networkAccessOnVPNFailure ( onlyToGateway | fullAccess )] [-clientControl ( ALLOW | DENY )] [-locationBasedVPN ( Remote | Everywhere )]


##Arguments

<b>name</b>
Name for the AlwaysON profile

<b>networkAccessOnVPNFailure</b>
Option to block network traffic when tunnel is not established(and the config requires that tunnel be established). When set to onlyToGateway, the network traffic to and from the client (except Gateway IP) is blocked. When set to fullAccess, the network traffic is not blocked
Possible values: onlyToGateway, fullAccess
Default value: fullAccess,

<b>clientControl</b>
Allow/Deny user to log off and connect to another Gateway
Possible values: ALLOW, DENY
Default value: DENY

<b>locationBasedVPN</b>
Option to decide if tunnel should be established when in enterprise network. When locationBasedVPN is remote, client tries to detect if it is located in enterprise network or not and establishes the tunnel if not in enterprise network. Dns suffixes configured using -add dns suffix- are used to decide if the client is in the enterprise network or not. If the resolution of the DNS suffix results in private IP, client is said to be in enterprise network. When set to EveryWhere, the client skips the check to detect if it is on the enterprise network and tries to establish the tunnel
Possible values: Remote, Everywhere
Default value: Remote



##unset vpn alwaysONProfile

Use this command to remove vpn alwaysONProfile settings.Refer to the set vpn alwaysONProfile command for meanings of the arguments.


##Synopsys

unset vpn alwaysONProfile &lt;name> [-networkAccessOnVPNFailure] [-clientControl] [-locationBasedVPN]


##show vpn alwaysONProfile

Displays information on AlwaysON profile


##Synopsys

show vpn alwaysONProfile [&lt;name>]


##Arguments

<b>name</b>
name of AlwaysON profile.



##Outputs

<b>networkAccessOnVPNFailure</b>
Option to block network traffic when tunnel is not established(and the config requires that tunnel be established). When set to onlyToGateway, the network traffic to and from the client (except Gateway IP) is blocked. When set to fullAccess, the network traffic is not blocked

<b>clientControl</b>
Allow/Deny user to log off and connect to another Gateway

<b>locationBasedVPN</b>
Option to decide if tunnel should be established when in enterprise network. When locationBasedVPN is remote, client tries to detect if it is located in enterprise network or not and establishes the tunnel if not in enterprise network. Dns suffixes configured using -add dns suffix- are used to decide if the client is in the enterprise network or not. If the resolution of the DNS suffix results in private IP, client is said to be in enterprise network. When set to EveryWhere, the client skips the check to detect if it is on the enterprise network and tries to establish the tunnel

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show vpn alwaysONProfile AP1

