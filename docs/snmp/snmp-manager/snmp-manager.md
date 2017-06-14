#snmp manager

The following operations can be performed on "snmp manager":


[add](#add-snmp-manager) | [rm](#rm-snmp-manager) | [set](#set-snmp-manager) | [unset](#unset-snmp-manager) | [show](#show-snmp-manager)

##add snmp manager

Specifies an SNMP manager to query the NetScaler appliance. The added manager complies with SNMP V1, V2, and V3. If you specify one or more SNMP managers, the appliance does not accept SNMP queries from any hosts except the specified SNMP managers. You can specify up to a maximum of 100 IP based SNMP managers or networks and a maximum of 5 host-name based SNMP managers.


##Synopsys

add snmp manager &lt;IPAddress> ... [-netmask &lt;netmask>] [-domainResolveRetry &lt;integer>]


##Arguments

<b>IPAddress</b>
IP address of the SNMP manager. Can be an IPv4 or IPv6 address. You can instead specify an IPv4 network address or IPv6 network prefix if you want the NetScaler appliance to respond to SNMP queries from any device on the specified network. Alternatively, instead of an IPv4 address, you can specify a host name that has been assigned to an SNMP manager. If you do so, you must add a DNS name server that resolves the host name of the SNMP manager to its IP address. 
Note: The NetScaler appliance does not support host names for SNMP managers that have IPv6 addresses.

<b>netmask</b>
Subnet mask associated with an IPv4 network address. If the IP address specifies the address or host name of a specific host, accept the default value of 255.255.255.255.
Default value: 0xFFFFFFFF

<b>domainResolveRetry</b>
Amount of time, in seconds, for which the NetScaler appliance waits before sending another DNS query to resolve the host name of the SNMP manager if the last query failed. This parameter is valid for host-name based SNMP managers only. After a query succeeds, the TTL determines the wait time.
Minimum value: 5
Maximum value: 20939



##Example

add snmp manager 192.168.1.20 192.168.2.42add snmp manager 192.168.2.16 -netmask 255.255.255.240add snmp manager hostnamemanager.com

##rm snmp manager

Removes an SNMP manager from the list of managers that are allowed to access the NetScaler appliance.


##Synopsys

rm snmp manager &lt;IPAddress> ... [-netmask &lt;netmask>]


##Arguments

<b>IPAddress</b>
IPv4 or IPv6 address (or IPv4 host name) of the SNMP manager, or the IPv4 network address or IPv6 network prefix of the SNMP managers.

<b>netmask</b>
Subnet mask associated with an IPv4 SNMP manager entry. For a specific host, the subnet mask is 255.255.255.255.
Default value: 0xFFFFFFFF



##Example

rm snmp manager 192.168.1.20rm snmp manager 192.168.2.16 -netmask 255.255.255.240rm snmp manager hostnamemanager.com

##set snmp manager

Modifies the Domain Resolve Retry parameter of any host-name based SNMP manager configured on the NetScaler appliance.


##Synopsys

set snmp manager &lt;IPAddress> [-netmask &lt;netmask>] [-domainResolveRetry &lt;integer>]


##Arguments

<b>IPAddress</b>
Host name of the SNMP manager for which you want to modify the Domain Resolve Retry parameter.

<b>netmask</b>
Subnet mask associated with an IPv4 network address. If the IP address specifies the address or host name of a specific host, accept the default value of 255.255.255.255.
Default value: 0xFFFFFFFF

<b>domainResolveRetry</b>
Amount of time, in seconds, for which the NetScaler appliance waits before sending another DNS query to resolve the host name of the SNMP manager if the last query failed. This parameter is valid for host-name based SNMP managers only. After a query succeeds, the TTL determines the wait time.
Minimum value: 5
Maximum value: 20939



##Example

set snmp manager www.example.com -domainResolveRetry 7

##unset snmp manager

Use this command to remove snmp manager settings.Refer to the set snmp manager command for meanings of the arguments.


##Synopsys

unset snmp manager &lt;IPAddress> -netmask &lt;netmask> -domainResolveRetry


##show snmp manager

Displays configuration information about all SNMP managers on the NetScaler appliance, or detailed information about the specified manager.


##Synopsys

show snmp manager [&lt;IPAddress>  [-netmask &lt;netmask>]]


##Arguments

<b>IPAddress</b>
IPv4 or IPv6 address (or IPv4 host name) of the SNMP manager, or the IPv4 network address or IPv6 network prefix of the SNMP managers, about which to display information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>IP</b>
The resolved IP address of the hostname manager

<b>domain</b>
IP address of manager. It will be zero for hostname manager

<b>domainResolveRetry</b>
Amount of time, in seconds, for which the NetScaler appliance waits before sending another DNS query to resolve the host name of the SNMP manager if the last query failed. This parameter is valid for host-name based SNMP managers only. After a query succeeds, the TTL determines the wait time.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show snmp manager

