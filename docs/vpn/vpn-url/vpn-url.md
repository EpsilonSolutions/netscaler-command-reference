#vpn url

The following operations can be performed on "vpn url":


[add](#add-vpn-url) | [rm](#rm-vpn-url) | [set](#set-vpn-url) | [unset](#unset-vpn-url) | [show](#show-vpn-url)

##add vpn url

Creates a bookmark link to an external or internal resource that appears on the Access Interface, according to type, as a web site link or file share link.


##Synopsys

add vpn url &lt;urlName> &lt;linkName> &lt;actualURL> [-clientlessAccess ( ON | OFF )] [-comment &lt;string>]


##Arguments

<b>urlName</b>
Name of the bookmark link.

<b>linkName</b>
Description of the bookmark link. The description appears in the Access Interface.

<b>actualURL</b>
Web address for the bookmark link.

<b>clientlessAccess</b>
If clientless access to the resource hosting the link is allowed, also use clientless access for the bookmarked web address in the Secure Client Access based session. Allows single sign-on and other HTTP processing on NetScaler Gateway for HTTPS resources.
Possible values: ON, OFF
Default value: OFF

<b>comment</b>
Any comments associated with the bookmark link.



##Example

add vpn url ggl search www.google.com.

##rm vpn url

Removes a bookmark link to an internal resource that appears in the Access Interface.


##Synopsys

rm vpn url &lt;urlName>


##Arguments

<b>urlName</b>
Name of the bookmark link to remove.



##Example

rm vpn url ggl

##set vpn url

Modifies the specified parameters of a bookmark link to an internal resource that appears in the Access Interface.


##Synopsys

set vpn url &lt;urlName> [-linkName &lt;string>] [-actualURL &lt;string>] [-clientlessAccess ( ON | OFF )] [-comment &lt;string>]


##Arguments

<b>urlName</b>
Name of the bookmark link.

<b>linkName</b>
Description of the bookmark link. The description appears in the Access Interface.

<b>actualURL</b>
Web address for the bookmark link.

<b>clientlessAccess</b>
If clientless access to the resource hosting the link is allowed, also use clientless access for the bookmarked web address in the Secure Client Access based session. Allows single sign-on and other HTTP processing on NetScaler Gateway for HTTPS resources.
Possible values: ON, OFF
Default value: OFF

<b>comment</b>
Any comments associated with the bookmark link.



##Example

set vpn url wiurl -clientlessAccess on

##unset vpn url

Use this command to remove vpn url settings.Refer to the set vpn url command for meanings of the arguments.


##Synopsys

unset vpn url &lt;urlName> [-clientlessAccess] [-comment]


##show vpn url

Displays information about all the configured bookmark links to internal resources that appear in the Access Interface, or displays detailed information about the specified bookmark link.


##Synopsys

show vpn url [&lt;urlName>]


##Arguments

<b>urlName</b>
Name of the bookmark link for which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>linkName</b>
Description of the bookmark link. The description appears in the Access Interface.

<b>actualURL</b>
Web address for the bookmark link.

<b>clientlessAccess</b>
Whether clientless access is enabled for the url in other modes or not.

<b>comment</b>
Comments associated with this virtual server.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



