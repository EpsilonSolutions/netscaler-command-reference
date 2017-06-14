#dns global

The following operations can be performed on "dns global":


[bind](#bind-dns-global) | [unbind](#unbind-dns-global) | [show](#show-dns-global)

##bind dns global

Binds the specified DNS policy globally.


##Synopsys

bind dns global &lt;policyName> &lt;priority> [-gotoPriorityExpression &lt;string>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the DNS policy to bind globally.



##Example

bind dns global pol9 9

##unbind dns global

Unbinds the specified DNS policy from the global bind point.


##Synopsys

unbind dns global &lt;policyName> [-type &lt;type>]


##Arguments

<b>policyName</b>
Name of the DNS policy to unbind.



##Example

unbind dns global pol9

##show dns global

Displays the DNS policies bound to the specified global bind point. If a global bind point is not specified, the command displays the global bind points that have policies bound to them, and the number of policies bound to each of those bind points.


##Synopsys

show dns global [-type &lt;type>]


##Arguments

<b>type</b>
Type of global bind point for which to show bound policies.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the dns policy.

<b>priority</b>
Specifies the priority of the policy with which it is bound. Maximum allowed priority should be less than 65535

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a priority number that is numerically higher than the highest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>invoke</b>
Invoke flag.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flowType</b>
flowtype of the bound rewrite policy.

<b>flags</b>

<b>upgraded</b>
It is internally used to tell that the policy is a upgraded policy.

<b>builtin</b>
Flag to determine whether DNS policy binding is default or not

<b>devno</b>

<b>count</b>



##Example

show dns globalshow dns global -type REQ_DEFAULTshow dns global -type RES_DEFAULT

