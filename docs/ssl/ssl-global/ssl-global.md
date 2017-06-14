#ssl global

The following operations can be performed on "ssl global":


[bind](#bind-ssl-global) | [unbind](#unbind-ssl-global) | [show](#show-ssl-global)

##bind ssl global

Binds an SSL policy globally.


##Synopsys

bind ssl global [-policyName &lt;string>] [-priority &lt;positive_integer>] [-gotoPriorityExpression &lt;expression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the SSL policy.



##Example

bind ssl global -policyName certInsert_pol -priority 100

##unbind ssl global

Unbinds a globally bound SSL policy.


##Synopsys

unbind ssl global [-policyName &lt;string>  [-type &lt;type>]  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the SSL policy to unbind.



##Example

unbind ssl global -policyName certInsert_pol

##show ssl global

Displays globally bound SSL policies.


##Synopsys

show ssl global [-type &lt;type>]


##Arguments

<b>type</b>
Global bind point to which the policy is bound.
Possible values: CONTROL_OVERRIDE, CONTROL_DEFAULT, DATA_OVERRIDE, DATA_DEFAULT

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>policyName</b>
The name for the SSL policy.

<b>priority</b>
The priority of the policy binding.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE

<b>invoke</b>
Invoke flag. This attribute is relevant only for ADVANCED policies

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>devno</b>

<b>count</b>



##Example

show ssl global        1 Globally Active SSL Policy:1)      Name: certInsert_pol        Priority: 100

