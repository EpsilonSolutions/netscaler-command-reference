#ca global

The following operations can be performed on "ca global":


[bind](#bind-ca-global) | [unbind](#unbind-ca-global) | [show](#show-ca-global)

##bind ca global

Activates the specified content accelerator policy for all requests sent to the NetScaler appliance.


##Synopsys

bind ca global -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-type &lt;type>]


##Arguments

<b>policyName</b>
Name of the content accelerator policy.

<b>priority</b>
Specifies the priority of the content accelerator policy.
Minimum value: 0

<b>gotoPriorityExpression</b>

<b>type</b>



##Example

	i)	bind ca global pol9 9

##unbind ca global

Unbind the specified content accelerator policy from ContentAccelerator global.


##Synopsys

unbind ca global &lt;policyName> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Name of the policy to unbind.

<b>type</b>
The bindpoint from which the policy is to be unbound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind ca global pol9

##show ca global

Shows the content accelerator policies that are globally-bound to the NetScaler appliance.


##Synopsys

show ca global [-type &lt;type>]


##Arguments

<b>type</b>



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the content accelerator policy.

<b>priority</b>
Specifies the priority of the content accelerator policy.

<b>gotoPriorityExpression</b>

<b>flowType</b>
flowtype of the bound content accelerator policy.

<b>numpol</b>
Number of polices bound to label.

<b>flags</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show ca global

