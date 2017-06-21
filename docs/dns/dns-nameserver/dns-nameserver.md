#dns nameServer

The following operations can be performed on "dns nameServer":


[add](#add-dns-nameserver) | [set](#set-dns-nameserver) | [unset](#unset-dns-nameserver) | [rm](#rm-dns-nameserver) | [enable](#enable-dns-nameserver) | [disable](#disable-dns-nameserver) | [show](#show-dns-nameserver)

##add dns nameServer

Adds a name server to the appliance. Following are the two types of name servers that can be added:* IP address-based name server - An external name server to contact for domain name resolution. If multiple IP address-based name servers are configured on the appliance, and the local parameter is not set on any of them, incoming DNS queries are load balanced across all the name servers, in round robin fashion.* Virtual server-based name server - A DNS virtual server configured in the NetScaler appliance. If you want more fine-grained control on how external DNS name servers are load balanced (for example, you want a load balancing method other than round robin), you configure a DNS virtual server on the appliance, bind the external name servers as its services, and then specify the name of the virtual server in this command.


##Synopsys

add dns nameServer ((&lt;IP>  [-local]) | &lt;dnsVserverName>) [-state ( ENABLED | DISABLED )] [-type &lt;type>] [-dnsProfileName &lt;string>]


##Arguments

<b>IP</b>
IP address of an external name server or, if the Local parameter is set, IP address of a local DNS server (LDNS).

<b>dnsVserverName</b>
Name of a DNS virtual server. Overrides any IP address-based name servers configured on the NetScaler appliance.

<b>local</b>
Mark the IP address as one that belongs to a local recursive DNS server on the NetScaler appliance. The appliance recursively resolves queries received on an IP address that is marked as being local. For recursive resolution to work, the global DNS parameter, Recursion, must also be set. 
If no name server is marked as being local, the appliance functions as a stub resolver and load balances the name servers.

<b>state</b>
Administrative state of the name server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>type</b>
Protocol used by the name server. UDP_TCP is not valid if the name server is a DNS virtual server configured on the appliance.
Possible values: UDP, TCP, UDP_TCP
Default value: UDP

<b>dnsProfileName</b>
Name of the DNS profile to be associated with the name server



##Example

Adding an-IP based nameserver IP:	add nameserver 10.102.4.1,Adding a vserver-based name server:	add nameserver dns_vsvrwhere dns_vsvr is the name of a DNS vserver created in the system.

##set dns nameServer

Modifies the attributes of a DNS name server. Only IP based name server entities can be modified using this command. If the DNS name server is an LB VServer, modification to any of the attributes should be done using set lb vserver command


##Synopsys

set dns nameServer &lt;IP> [-dnsProfileName &lt;string>]


##Arguments

<b>IP</b>
IP address of an external name server or, if the Local parameter is set, IP address of a local DNS server (LDNS).

<b>dnsProfileName</b>
Name of the DNS profile to be associated with the name server



##Example

set dns nameserver 1.1.1.1 -dnsprofilename test2

##unset dns nameServer

Use this command to remove dns nameServer settings.Refer to the set dns nameServer command for meanings of the arguments.


##Synopsys

unset dns nameServer &lt;IP> [-dnsProfileName]


##rm dns nameServer

Removes a name server from the NetScaler appliance. If the name server is an IP-address based external name server, the name server entry is removed. If the name server is a DNS virtual server on the appliance, the virtual server is not removed, but it is no longer used to resolve domain names.


##Synopsys

rm dns nameServer (&lt;IP> | &lt;dnsVserverName>)


##Arguments

<b>IP</b>
IP address of the name server.

<b>dnsVserverName</b>
Name of the DNS virtual server.



##Example

Deleting an IP-based nameserver:	 rm nameserver 10.102.4.1, Deleting a vserver-based nameserver: 	rm nameserver dns_vsvr

##enable dns nameServer

Enables a name server.


##Synopsys

enable dns nameServer (&lt;IP> | &lt;dnsVserverName>)


##Arguments

<b>IP</b>
IP address of the name server.

<b>dnsVserverName</b>
Name of the DNS virtual server.



##Example

enable dns nameserver 10.14.43.149

##disable dns nameServer

Disables a name server.


##Synopsys

disable dns nameServer (&lt;IP> | &lt;dnsVserverName>)


##Arguments

<b>IP</b>
IP address of the name server.

<b>dnsVserverName</b>
Name of the DNS virtual server.



##Example

disable dns nameserver 10.14.43.149

##show dns nameServer

Displays the name servers configured on the NetScaler appliance, along with their administrative states.


##Synopsys

show dns nameServer [&lt;IP> | &lt;dnsVserverName>]


##Arguments

<b>IP</b>
IP address of the name server.

<b>dnsVserverName</b>
Name of the DNS virtual server.



##Outputs

<b>serviceName</b>
The name of the dns vserver.

<b>port</b>
Port of the service.

<b>type</b>
Protocol used by the name server. UDP_TCP is not valid if the name server is a DNS virtual server configured on the appliance.

<b>state</b>
Administrative state of the name server.

<b>nameserverstate</b>
State of the server.

<b>local</b>
ip is a local recursive nameserver.

<b>adminState</b>

<b>ClMonOwner</b>
Tells the mon owner of the service.

<b>ClMonView</b>
Tells the view id by which state of the service is updated.

<b>dnsProfileName</b>
Name of the DNS profile to be associated with the name server

<b>devno</b>

<b>count</b>

<b>stateflag</b>



