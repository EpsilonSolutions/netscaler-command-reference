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



##unbind appfw global

Deactivates the specified application firewall policy. See the bind appfw policy command for descriptions of the parameters.


##Synopsys

unbind appfw global &lt;policyName> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Application Firewall policy name.

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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>devno</b>

<b>count</b>



