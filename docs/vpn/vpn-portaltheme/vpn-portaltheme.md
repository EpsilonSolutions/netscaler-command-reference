#vpn portaltheme

The following operations can be performed on "vpn portaltheme":


[add](#add-vpn-portaltheme) | [rm](#rm-vpn-portaltheme) | [show](#show-vpn-portaltheme)

##add vpn portaltheme

Add a new portaltheme entity. The base theme should be either Default,Greenbubble,X1 or RfWebUI


##Synopsys

add vpn portaltheme &lt;name> -basetheme &lt;basetheme>


##Arguments

<b>name</b>
Name of the uitheme

<b>basetheme</b>



##Example

add vpn portaltheme theme1 -basetheme Default

##rm vpn portaltheme

Removes a portaltheme entity


##Synopsys

rm vpn portaltheme &lt;name>


##Arguments

<b>name</b>
Name of the portal theme to remove.



##Example

rm vpn portaltheme theme1

##show vpn portaltheme

Displays information about all the configured portalthemes.


##Synopsys

show vpn portaltheme [&lt;name>]


##Arguments

<b>name</b>
Name of portal theme to be displayed



##Outputs

<b>basetheme</b>

<b>builtin</b>
Flag to determine if portaltheme is built-in or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



