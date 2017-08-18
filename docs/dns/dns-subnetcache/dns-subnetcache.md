#dns subnetcache

The following operations can be performed on "dns subnetcache":


[flush](#flush-dns-subnetcache) | [show](#show-dns-subnetcache)

##flush dns subnetcache

FLushes a specified ECS subnet or all cached ECS subnets from the DNS cache on the NetScaler appliance.


##Synopsys

flush dns subnetcache (&lt;ecsSubnet> | -all)


##Arguments

<b>ecsSubnet</b>
ECS Subnet.

<b>all</b>
Flush all the ECS subnets from the DNS cache.



##show dns subnetcache

Displays all the domains for which ECS records are cached for the given ECS subnet. It also displays the type of dns records cached for every domain associated with the subnet. If a subnet is not specified, all the configured ECS subnets on the NetScaler appliance are shown. 


##Synopsys

show dns subnetcache [&lt;ecsSubnet>]


##Arguments

<b>ecsSubnet</b>
ECS Subnet.



##Outputs

<b>hostName</b>
Domain name.

<b>nextRecs</b>
An array of record types associated with the domain name.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



