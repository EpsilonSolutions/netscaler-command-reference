#appfw global

The following operations can be performed on "appfw global":


[bind](#bind-appfw-global) | [unbind](#unbind-appfw-global) | [show](#show-appfw-global)

##bind appfw global

Activates an application firewall policy.


##Synopsys

bind appfw global &lt;policyName> &lt;priority> [-state ( ENABLED | DISABLED )] [&lt;gotoPriorityExpression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the policy.

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Must be unique within the group of policies that are bound to the global bind point. Policies are evaluated in the order of their priority numbers.
Minimum value: 0
Maximum value: 2147483647

<b>state</b>
Enable or disable the binding to activate or deactivate the policy. This is applicable to classic policies only.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is smaller than the current policy's priority number.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
Bind point to which to bind the policy. Can be used only with NetScaler default policies. NetScaler classic policies are not supported. Available settings function as follows:
* REQ_OVERRIDE. Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT. Binds the policy to the default request queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, NONE

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of policy label to invoke if the current policy evaluates to TRUE and the invoke parameter is set. Available settings function as follows:
* reqvserver. Invoke the unnamed policy label associated with the specified request virtual server.
* policylabel. Invoke the specified user-defined policy label.
Possible values: reqvserver, policylabel

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is set to Policy Label.



##unbind appfw global

Deactivates the specified application firewall policy. See the bind appfw policy command for descriptions of the parameters.


##Synopsys

unbind appfw global &lt;policyName> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Application Firewall policy name.

<b>type</b>
The bindpoint from which the policy is to be unbound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, NONE

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##show appfw global

Displays a list of application firewall policies that are bound to the specified bind point. If no bind point is specified, displays a list of all application firewall policies


##Synopsys

show appfw global [-type &lt;type>]


##Arguments

<b>type</b>
Bind point to which to policy is bound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, NONE



##Outputs

<b>policyName</b>
Name of the policy.

<b>priority</b>
The priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>state</b>
Enable or disable the binding to activate or deactivate the policy. This is applicable to classic policies only.

<b>bindPolicyType</b>
The type of the policy.

<b>policySubType</b>

<b>stateflag</b>
stateflag

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is set to Policy Label.

<b>flowType</b>
flowtype of the bound application firewall policy.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flags</b>

<b>policyType</b>

<b>flag</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



