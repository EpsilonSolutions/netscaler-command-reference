#ica global

The following operations can be performed on "ica global":


[bind](#bind-ica-global) | [unbind](#unbind-ica-global) | [show](#show-ica-global)

##bind ica global

This command binds the ICA policy to one of the two global lists of ICA policies. A policy becomes active only after it is bound.


##Synopsys

bind ica global -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-type ( ICA_REQ_OVERRIDE | ICA_REQ_DEFAULT )]


##Arguments

<b>policyName</b>
Name of the ICA policy to be bound.

<b>priority</b>
Integer specifying the priority of the policy. The lower the number, the higher the priority. By default, policies in the list are evaluated in the order of their priority numbers.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the priority of the next policy, within the policy list, to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher numbered priority.
* END - Stop evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy list. If the final goto in the invoked policy list has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy list performs a NEXT.
* An expression that evaluates to a number.
If you specify an expression, it's evaluation result determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, that policy is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher priority number is evaluated next.
* If the expression evaluates to a priority number that is numerically higher than the highest priority number, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
The bind point to which to bind the policy.
Possible values: ICA_REQ_OVERRIDE, ICA_REQ_DEFAULT



##Example

      i      bind ica global -policyName pol9 -priority 9        

##unbind ica global

Unbinds entities from an ICA global bind point.


##Synopsys

unbind ica global (-policyName &lt;string>  [-type ( ICA_REQ_OVERRIDE | ICA_REQ_DEFAULT )]  [-priority &lt;positive_integer>])


##Arguments

<b>policyName</b>
Name of the policy to be unbound.

<b>type</b>
Bind point from which to unbind the policy.
Possible values: ICA_REQ_OVERRIDE, ICA_REQ_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound.  Applicable only if a NOPOLICY has been bound to the bind point.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind ica global -policyName pol9

##show ica global

Displays the ICA global bind points and the number of policies bound to each global bind point, or more detailed information about the specified bind point.


##Synopsys

show ica global [-type ( ICA_REQ_OVERRIDE | ICA_REQ_DEFAULT )]


##Arguments

<b>type</b>
Global bind point for which to show detailed information about the policies bound to the bind point.
Possible values: ICA_REQ_OVERRIDE, ICA_REQ_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the ICA policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flowType</b>
Flow type of the bound ICA policy.

<b>flags</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show ica global

