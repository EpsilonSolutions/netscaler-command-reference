#ns serviceFunction

The following operations can be performed on "ns serviceFunction":


[add](#add-ns-servicefunction) | [set](#set-ns-servicefunction) | [rm](#rm-ns-servicefunction) | [show](#show-ns-servicefunction)

##add ns serviceFunction

Add a service function.


##Synopsys

add ns serviceFunction &lt;serviceFunctionName> -ingressVLAN &lt;positive_integer>


##Arguments

<b>serviceFunctionName</b>
Name of the service function to be created. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ).

<b>ingressVLAN</b>
VLAN ID on which the traffic from service function reaches Netscaler.
Minimum value: 1
Maximum value: 4094



##Example

add servicefunction tcpopt -ingressVLAN vlan1

##set ns serviceFunction

Set operation on a service function.


##Synopsys

set ns serviceFunction &lt;serviceFunctionName> [-ingressVLAN &lt;positive_integer>]


##Arguments

<b>serviceFunctionName</b>
Name of the service function to be created. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ).

<b>ingressVLAN</b>
VLAN ID on which the traffic from service function reaches Netscaler.
Minimum value: 1
Maximum value: 4094



##Example

set servicefunction tcpopt -ingressVLAN vlan2

##rm ns serviceFunction

Removes specified service function.


##Synopsys

rm ns serviceFunction &lt;serviceFunctionName>


##Arguments

<b>serviceFunctionName</b>
Name of the service function to be created. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ).



##Example

rm servicefunction tcpopt

##show ns serviceFunction

displays specified service function.


##Synopsys

show ns serviceFunction [&lt;serviceFunctionName>]


##Arguments

<b>serviceFunctionName</b>
Name of the service function to be created. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ).



##Outputs

<b>ingressVLAN</b>
VLAN ID on which the traffic from service function reaches Netscaler.

<b>stateflag</b>
the field for stateflags.

<b>devno</b>

<b>count</b>



##Example

show servicefunction tcpopt

