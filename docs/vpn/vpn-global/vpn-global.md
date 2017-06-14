#vpn global

The following operations can be performed on "vpn global":


[bind](#bind-vpn-global) | [unbind](#unbind-vpn-global) | [show](#show-vpn-global)

##bind vpn global

Binds NetScaler Gateway entities, including policies, globally.


##Synopsys

bind vpn global [-policyName &lt;string>  [-priority &lt;positive_integer>]  [-secondary]  [-groupExtraction]] [-intranetDomain &lt;string>] [-intranetApplication &lt;string>] [-nextHopServer &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-staServer &lt;URL>  [-staAddressType ( IPV4 | IPV6 )]] [-appController &lt;URL>] [-sharefile &lt;string>]


##Arguments

<b>policyName</b>
Name of the policy to bind globally.

<b>intranetDomain</b>
Intranet domain name for single sign-on.

<b>intranetApplication</b>
Name of the intranet application to bind globally.

<b>nextHopServer</b>
Name of the next hop server to bind globally.

<b>urlName</b>
Name of the URL of the virtual server to bind globally.

<b>intranetIP</b>
Range of IP addresses in an address pool or individual IP addresses to bind globally.

<b>staServer</b>
Web address of the Secure Ticketing Authority (STA) server to be bound globally, in the following format: 'http(s)://FQDN/URLPATH'

<b>appController</b>
App Controller server, in the format 'http(s)://IP/FQDN'

<b>sharefile</b>
ShareFile server, in the format 'IP:PORT / FQDN:PORT'



##unbind vpn global

Unbinds NetScaler Gateway policies to the virtual server globally.


##Synopsys

unbind vpn global [-policyName &lt;string>  [-secondary]  [-groupExtraction]] [-intranetDomain &lt;string>] [-intranetApplication &lt;string>] [-nextHopServer &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-staServer &lt;URL>] [-appController &lt;URL>] [-sharefile &lt;string>]


##Arguments

<b>policyName</b>
Name of the policy to unbind globally.

<b>intranetDomain</b>
A conflicting intranet domain name to be unbound.

<b>intranetApplication</b>
The name of a VPN intranet application to be unbound.

<b>nextHopServer</b>
The name of the next hop server to be unbound globally.

<b>urlName</b>
The name of a VPN url to be unbound from vpn global.

<b>intranetIP</b>
The intranet IP address or range to be unbound.

<b>staServer</b>
Secure Ticketing Authority (STA) server to be removed, in the format 'http(s)://IP/FQDN/URLPATH'

<b>appController</b>
App Controller server to be removed, in the format 'http(s)://IP/FQDN'

<b>sharefile</b>
ShareFile server to be removed, in the format 'IP:PORT / FQDN:PORT'



##show vpn global

Shows the NetScaler Gateway policies that are bound to the virtual server globally.


##Synopsys

show vpn global


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>policyName</b>
The name of the policy.

<b>priority</b>
The priority of the policy.

<b>intranetDomain</b>
The conflicting intranet domain name.

<b>intranetApplication</b>
The intranet vpn application.

<b>nextHopServer</b>
The name of the next hop server bound to vpn global.

<b>urlName</b>
The intranet url.

<b>intranetIP</b>
The intranet ip address or range.

<b>netmask</b>
The intranet ip address or range's netmask.

<b>staServer</b>
Configured Secure Ticketing Authority (STA) server.

<b>staAddressType</b>
Type of the STA server address(ipv4/v6).

<b>staAuthID</b>
Authority ID of the STA Server. Authority ID is used to match incoming STA Tickets in the SOCKS/CGP protocol with the right STA Server.

<b>appController</b>
Configured App Controller server.

<b>sharefile</b>
Configured Sharefile server, in the format IP:PORT / FQDN:PORT

<b>type</b>
Bindpoint to which the policy is bound

<b>policySubType</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>secondary</b>
Bind the authentication policy as the secondary policy to use in a two-factor configuration. A user must then authenticate not only to a primary authentication server but also to a secondary authentication server. User groups are aggregated across both authentication servers. The user name must be exactly the same on both authentication servers, but the authentication servers can require different passwords.

<b>groupExtraction</b>
Bind the Authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called it primary and/or secondary authentication has succeeded.

<b>policyType</b>
Policy type (Classic/Advanced) to be bound.Used for display.

<b>devno</b>

<b>count</b>



