#vPathParam

The following operations can be performed on "vPathParam":


[set](#set-vpathparam) | [unset](#unset-vpathparam) | [show](#show-vpathparam)

##set vPathParam

Sets the global parameters for vPath


##Synopsys

set vPathParam [-srcIP &lt;ip_addr>] [-offload ( ENABLED | DISABLED )]


##Arguments

<b>srcIP</b>
source-IP address used for all vPath L3 encapsulations. Must be a MIP or SNIP address.

<b>offload</b>
enable/disable vPath offload feature
Possible values: ENABLED, DISABLED
Default value: 2



##Example

set vpathparam -srcip 2.2.2.2

##unset vPathParam

Use this command to remove  vPathParam settings.Refer to the set  vPathParam command for meanings of the arguments.


##Synopsys

unset vPathParam [-srcIP] [-offload]


##show vPathParam

Display the global parameters for vPath


##Synopsys

show vPathParam


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>srcIP</b>
srcIP used for vPath encapsulation.

<b>Encapsulation</b>
Global vPath encapsulation .

<b>offload</b>
enable/disable vPath offload feature



##Example

show vpathparam

