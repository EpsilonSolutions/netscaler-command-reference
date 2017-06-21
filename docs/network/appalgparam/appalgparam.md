#appAlgParam

The following operations can be performed on "appAlgParam":


[set](#set-appalgparam) | [unset](#unset-appalgparam) | [show](#show-appalgparam)

##set appAlgParam

Sets the global parameters for APP ALG


##Synopsys

set appAlgParam -pptpGreIdleTimeout &lt;positive_integer>


##Arguments

<b>pptpGreIdleTimeout</b>
Interval in sec, after which data sessions of PPTP GRE is cleared.
Default value: 9000
Minimum value: 1
Maximum value: 9000



##Example

set appalgparam -pptpGreIdleTimeout 15000

##unset appAlgParam

Use this command to remove  appAlgParam settings.Refer to the set  appAlgParam command for meanings of the arguments.


##Synopsys

unset appAlgParam -pptpGreIdleTimeout


##show appAlgParam

Display the global parameters for APP ALG


##Synopsys

show appAlgParam


##Outputs

<b>pptpGreIdleTimeout</b>
Interval in sec, after which data sessions of PPTP GRE is cleared.



##Example

show appalgparam

