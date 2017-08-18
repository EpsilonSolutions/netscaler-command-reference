#tm global

The following operations can be performed on "tm global":


[bind](#bind-tm-global) | [unbind](#unbind-tm-global) | [show](#show-tm-global)

##bind tm global

Binds traffic, sessions, nslog, and syslog policies to traffic management (TM) Global.


##Synopsys

bind tm global [-policyName &lt;string>  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]]


##Arguments

<b>policyName</b>
Name of the policy that you are binding.

<b>priority</b>
Integer specifying the policy's priority. The lower the number, the higher the priority. Policies are evaluated in the order of their priority numbers.
Minimum value: 0

<b>gotoPriorityExpression</b>
Applicable only to advance tmsession policy. Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* A default syntax expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a priority number that is numerically higher than the highest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.



##unbind tm global

Unbinds a globally bound traffic session policy.


##Synopsys

unbind tm global -policyName &lt;string>


##Arguments

<b>policyName</b>
Name of the policy to unbind.



##show tm global

Displays information about TM global bindings.


##Synopsys

show tm global


##Outputs

<b>policyName</b>
The name of the policy.

<b>priority</b>
The priority of the policy.

<b>type</b>
Bindpoint to which the policy is bound

<b>policySubType</b>

<b>stateflag</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>bindPolicyType</b>
Bound policy type

<b>globalBindType</b>

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>devno</b>

<b>count</b>



