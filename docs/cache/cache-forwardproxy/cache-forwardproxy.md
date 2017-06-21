#cache forwardProxy

The following operations can be performed on "cache forwardProxy":


[add](#add-cache-forwardproxy) | [rm](#rm-cache-forwardproxy) | [show](#show-cache-forwardproxy)

##add cache forwardProxy

Allows the cache to act as a forward proxy for other NetScaler appliances or cache servers.


##Synopsys

add cache forwardProxy &lt;IPAddress> &lt;port>


##Arguments

<b>IPAddress</b>
IP address of the NetScaler appliance or a cache server for which the cache acts as a proxy. Requests coming to the NetScaler with the configured IP address are forwarded to the particular address, without involving the Integrated Cache in any way.

<b>port</b>
Port on the NetScaler appliance or a server for which the cache acts as a proxy
Minimum value: 1



##rm cache forwardProxy

Removes the forward proxy address from the Integrated Cache. The cache does not act as a proxy to the specified IP address.


##Synopsys

rm cache forwardProxy &lt;IPAddress> &lt;port>


##Arguments

<b>IPAddress</b>
IP address of the NetScaler appliance or a server for which the cache was as a proxy.

<b>port</b>
Port on the NetScaler appliance or a server for which the cache acts as a proxy
Minimum value: 1



##show cache forwardProxy

Displays the IP address and the corresponding ports for which the cache acted as a forward proxy.


##Synopsys

show cache forwardProxy


##Outputs

<b>IPAddress</b>
IP address of the NetScaler appliance or a cache server for which the cache acts as a proxy. Requests coming to the NetScaler with the configured IP address are forwarded to the particular address, without involving the Integrated Cache in any way.

<b>port</b>
Forward proxy port.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



