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

<b>priority</b>
Integer specifying the policy's priority. The lower the number, the higher the priority.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.
Default value: "END"

<b>type</b>
Global bind point to which to bind the default syntax policy. If CONTROL_OVERRIDE or DATA_OVERRIDE is selected, the global control or data policy overrides the control or data policy bound to the virtual server or service.
Possible values: CONTROL_OVERRIDE, CONTROL_DEFAULT, DATA_OVERRIDE, DATA_DEFAULT

<b>invoke</b>
Invoke policies bound to a virtual server, service, or policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority.

<b>labelType</b>
Type of policy label to invoke. Specify virtual server for a policy label associated with a virtual server, or policy label for a user-defined policy label.
Possible values: vserver, service, policylabel

<b>labelName</b>
Name of the virtual server or user-defined policy label to invoke if the policy evaluates to TRUE.



##Example

bind ssl global -policyName certInsert_pol -priority 100

##unbind ssl global

Unbinds a globally bound SSL policy.


##Synopsys

unbind ssl global [-policyName &lt;string>  [-type &lt;type>]  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the SSL policy to unbind.

<b>type</b>
Global bind point from which the policy is to be unbound.
Possible values: CONTROL_OVERRIDE, CONTROL_DEFAULT, DATA_OVERRIDE, DATA_DEFAULT

<b>priority</b>
Priority of the NOPOLICY (built-in policy) to be unbound. Not required if you are unbinding a user-defined policy.
Minimum value: 1
Maximum value: 2147483647



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

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show ssl global        1 Globally Active SSL Policy:1)      Name: certInsert_pol        Priority: 100

