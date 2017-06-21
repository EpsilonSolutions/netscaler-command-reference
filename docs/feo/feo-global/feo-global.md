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

<b>priority</b>
The priority assigned to the policy binding.
Minimum value: 1
Maximum value: 2147483647

<b>type</b>
Bind point, specifying where to bind the policy. This is relevant for advanced (default-syntax) policies only.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, NONE
Default value: NS_REQ_DEFAULT

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.
	o	If gotoPriorityExpression is not present or if it is equal to END then the policy bank evaluation ends here
	o	Else if the gotoPriorityExpression is equal to NEXT then the next policy in the priority order is evaluated.
	o	Else gotoPriorityExpression is evaluated. The result of gotoPriorityExpression (which has to be a number) is processed as follows:
		-	An UNDEF event is triggered if
			.	gotoPriorityExpression cannot be evaluated
			.	gotoPriorityExpression evaluates to number which is smaller than the maximum priority in the policy bank but is not same as any policy's priority
			.	gotoPriorityExpression evaluates to a priority that is smaller than the current policy's priority
		-	If the gotoPriorityExpression evaluates to the priority of the current policy then the next policy in the priority order is evaluated.
		-	If the gotoPriorityExpression evaluates to the priority of a policy further ahead in the list then that policy will be evaluated next.



##unbind feo global

Unbind a front end optimization policy globally.


##Synopsys

unbind feo global &lt;policyName> [-type &lt;type>  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the front end optimization policy.

<b>type</b>
Bindpoint, specifying from where to unbind the policy. Applicable only to advanced (default-syntax) policies.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, NONE

<b>priority</b>
Priority of the policy to be unbound.
Minimum value: 1
Maximum value: 2147483647



##show feo global

Display the globally bound front end optimization policies.


##Synopsys

show feo global [-type &lt;type>]


##Arguments

<b>type</b>
Bindpoint to which the policy is bound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, NONE



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

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



