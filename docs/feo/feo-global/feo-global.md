#feo global

The following operations can be performed on "feo global":


[bind](#bind-feo-global) | [unbind](#unbind-feo-global) | [show](#show-feo-global)

##bind feo global

Bind a front end optimization policy globally.


##Synopsys

bind feo global &lt;policyName> &lt;priority> [-type &lt;type>] [&lt;gotoPriorityExpression>]


##Arguments

<b>policyName</b>
Name of the front end optimization policy.



##unbind feo global

Unbind a front end optimization policy globally.


##Synopsys

unbind feo global &lt;policyName> [-type &lt;type>  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the front end optimization policy.



##show feo global

Display the globally bound front end optimization policies.


##Synopsys

show feo global [-type &lt;type>]


##Arguments

<b>type</b>
Bindpoint to which the policy is bound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, NONE

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>policyName</b>
The name of the globally bound front end optimization policy.

<b>priority</b>
The priority assigned to the policy binding.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>devno</b>

<b>count</b>



