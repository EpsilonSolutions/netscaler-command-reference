#rnatparam

The following operations can be performed on "rnatparam":


[set](#set-rnatparam) | [unset](#unset-rnatparam) | [show](#show-rnatparam)

##set rnatparam

Sets global parameters of RNAT rules on the NetScaler appliance.


##Synopsys

set rnatparam [-tcpproxy ( ENABLED | DISABLED )] [-srcippersistency ( ENABLED | DISABLED )]


##Arguments

<b>tcpproxy</b>
Enable TCP proxy, which enables the NetScaler appliance to optimize the RNAT TCP traffic by using Layer 4 features.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>srcippersistency</b>
Enable source ip persistency, which enables the NetScaler appliance to use the RNAT ips using source ip.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set rnatparam -tcpproxy ENABLED or set rnatparam -srcippersistency ENABLED.

##unset rnatparam

Use this command to remove  rnatparam settings.Refer to the set  rnatparam command for meanings of the arguments.


##Synopsys

unset rnatparam [-tcpproxy] [-srcippersistency]


##show rnatparam

Show the rnat parameter.


##Synopsys

show rnatparam


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>tcpproxy</b>
Enable TCP proxy, which enables the NetScaler appliance to optimize the RNAT TCP traffic by using Layer 4 features.

<b>srcippersistency</b>
Enable source ip persistency, which enables the NetScaler appliance to use the RNAT ips using source ip.



##Example

show rnat parameter

