#radiusNode

The following operations can be performed on "radiusNode":


[add](#add-radiusnode) | [set](#set-radiusnode) | [rm](#rm-radiusnode) | [show](#show-radiusnode)

##add radiusNode

add a radiusnode and its secret key configuration on NS


##Synopsys

add radiusNode &lt;nodePrefix> -radKey 


##Arguments

<b>nodePrefix</b>
IP address/IP prefix of radius node in CIDR format

<b>radKey</b>
The key shared between the RADIUS server and clients.
      Required for NetScaler appliance to communicate with the RADIUS nodes.



##Example

add radiusnode 10.102.10.0/8 -radkey secret_key1

##set radiusNode

set secret key configuration of radius node


##Synopsys

set radiusNode &lt;nodePrefix> -radKey 


##Arguments

<b>nodePrefix</b>
IP address/IP prefix of radius node in CIDR format

<b>radKey</b>
The key shared between the RADIUS server and clients.
      Required for NetScaler appliance to communicate with the RADIUS nodes.



##Example

set radiusnode 10.102.10.0/8 -radkey secret_key2

##rm radiusNode

remove radius node configuration from NS


##Synopsys

rm radiusNode &lt;nodePrefix>


##Arguments

<b>nodePrefix</b>
IP address/IP prefix of radius node in CIDR format



##Example

rm radiusnode 10.102.10.0/8

##show radiusNode

show radius node configuration


##Synopsys

show radiusNode [&lt;nodePrefix>]


##Arguments

<b>nodePrefix</b>
IP address/IP prefix of radius node in CIDR format



##Outputs

<b>radKey</b>
The key shared between the RADIUS server and clients.
      Required for NetScaler appliance to communicate with the RADIUS nodes.

<b>stateflag</b>
To maintain state

<b>devno</b>

<b>count</b>



##Example

show radius node 10.102.10.0/8

