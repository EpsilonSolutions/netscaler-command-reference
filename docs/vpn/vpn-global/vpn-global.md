#vpn global

The following operations can be performed on "vpn global":


[bind](#bind-vpn-global) | [unbind](#unbind-vpn-global) | [show](#show-vpn-global)

##bind vpn global

Binds NetScaler Gateway entities, including policies, globally.


##Synopsys

bind vpn global [-policyName &lt;string>  [-priority &lt;positive_integer>]  [-secondary]  [-groupExtraction]  [-gotoPriorityExpression &lt;expression>]] [-intranetDomain &lt;string>] [-intranetApplication &lt;string>] [-nextHopServer &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  &lt;numaddr>] [-staServer &lt;URL>  [-staAddressType ( IPV4 | IPV6 )]] [-appController &lt;URL>] [-sharefile &lt;string>] [-portaltheme &lt;string>] [-eula &lt;string>]


##Arguments

<b>policyName</b>
Name of the policy to bind globally.

<b>priority</b>
Integer specifying the policy's priority. The lower the priority number, the higher the policy's priority. Maximum value for default syntax policies is 2147483647 and for classic policies is 64000.
Minimum value: 0
Maximum value: 2147483647

<b>secondary</b>
Bind the authentication policy as the secondary policy to use in a two-factor configuration. A user must then authenticate not only to a primary authentication server but also to a secondary authentication server. User groups are aggregated across both authentication servers. The user name must be exactly the same on both authentication servers, but the authentication servers can require different passwords.

<b>groupExtraction</b>
Bind the Authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called it primary and/or secondary authentication has succeeded.

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

<b>netmask</b>
The intranet ip or range's netmask.

<b>intranetIP6</b>
Starting address in the range of IPv6 addresses in an address pool or individual IPv6 addresses to bind globally.

<b>numaddr</b>
The intranet ipv6 address.
Minimum value: 1

<b>staServer</b>
Web address of the Secure Ticketing Authority (STA) server to be bound globally, in the following format: 'http(s)://FQDN/URLPATH'

<b>staAddressType</b>
Type of the STA server address(ipv4/v6).
Possible values: IPV4, IPV6

<b>appController</b>
App Controller server, in the format 'http(s)://IP/FQDN'

<b>sharefile</b>
ShareFile server, in the format 'IP:PORT / FQDN:PORT'

<b>gotoPriorityExpression</b>
Applicable only to advance vpn session policy. An expression or other value specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>portaltheme</b>
Portaltheme name to bind globally

<b>eula</b>
EULA name to bind globally



##unbind vpn global

Unbinds NetScaler Gateway policies to the virtual server globally.


##Synopsys

unbind vpn global [-policyName &lt;string>  [-secondary]  [-groupExtraction]] [-intranetDomain &lt;string>] [-intranetApplication &lt;string>] [-nextHopServer &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  &lt;numaddr>] [-staServer &lt;URL>] [-appController &lt;URL>] [-sharefile &lt;string>] [-portaltheme &lt;string>] [-eula &lt;string>]


##Arguments

<b>policyName</b>
Name of the policy to unbind globally.

<b>secondary</b>
Bind the authentication policy as the secondary policy to use in a two-factor configuration. A user must then authenticate not only to a primary authentication server but also to a secondary authentication server. User groups are aggregated across both authentication servers. The user name must be exactly the same on both authentication servers, but the authentication servers can require different passwords.

<b>groupExtraction</b>
Bind the Authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called it primary and/or secondary authentication has succeeded.

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

<b>netmask</b>
The intranet IP or range's netmask to be unbound from vpn global.

<b>intranetIP6</b>
The intranet ip address or range to be unbound.

<b>numaddr</b>
The intranet ip or range's netmask to be unbound from vpn global.
Minimum value: 1

<b>staServer</b>
Secure Ticketing Authority (STA) server to be removed, in the format 'http(s)://IP/FQDN/URLPATH'

<b>appController</b>
App Controller server to be removed, in the format 'http(s)://IP/FQDN'

<b>sharefile</b>
ShareFile server to be removed, in the format 'IP:PORT / FQDN:PORT'

<b>portaltheme</b>
Name of the Portal theme to unbind from vpnglobal

<b>eula</b>
Name of the EULA to unbind from vpnglobal



##show vpn global

Shows the NetScaler Gateway policies that are bound to the virtual server globally.


##Synopsys

show vpn global


##Outputs

<b>stateflag</b>

<b>policyName</b>
The name of the policy.

<b>priority</b>
Integer specifying the policy's priority. The lower the priority number, the higher the policy's priority. Maximum value for default syntax policies is 2147483647 and for classic policies is 64000.

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

<b>intranetIP6</b>
The intranet ip address or range.

<b>numaddr</b>
The intranet ip address or range's netmask.

<b>staServer</b>
Configured Secure Ticketing Authority (STA) server.

<b>staAddressType</b>
Type of the STA server address(ipv4/v6).

<b>staAuthID</b>
Authority ID of the STA Server. Authority ID is used to match incoming STA Tickets in the SOCKS/CGP protocol with the right STA Server.

<b>staState</b>
State of the STA Server. If Authority ID is set then STA Server is UP else DOWN.

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

<b>gotoPriorityExpression</b>
Applicable only to advance vpn session policy. An expression or other value specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>globalBindType</b>

<b>portaltheme</b>
Name of the portal theme bound to vpnglobal

<b>eula</b>
Name of the EULA bound to vpnglobal

<b>devno</b>

<b>count</b>



