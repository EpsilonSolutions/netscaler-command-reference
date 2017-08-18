#policy param

The following operations can be performed on "policy param":


[set](#set-policy-param) | [unset](#unset-policy-param) | [show](#show-policy-param)

##set policy param

Sets the given Policy parameter(s).


##Synopsys

set policy param -timeout &lt;positive_integer>


##Arguments

<b>timeout</b>
Maximum time in milliseconds to allow for processing expressions without interruption. If the timeout is reached then the evaluation causes an UNDEF to be raised and no further processing is performed.
Minimum value: 1
Maximum value: 5000



##Example

set policy param -timeout 5

##unset policy param

Resets the given Policy parameter(s)..Refer to the set policy param command for meanings of the arguments.


##Synopsys

unset policy param -timeout


##Example

unset policy param -timeout

##show policy param

Displays the policy parameters.


##Synopsys

show policy param


##Outputs

<b>timeout</b>
Execution timeout.



##Example

show policy param

