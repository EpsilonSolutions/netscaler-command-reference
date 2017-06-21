#cache global

The following operations can be performed on "cache global":


[bind](#bind-cache-global) | [unbind](#unbind-cache-global) | [show](#show-cache-global)

##bind cache global

Binds the cache policy to one of the two global bind points (an unnamed policy label invoked at request time and an unnamed policy label invoked at the response time). The flow type of the policy implicitly determines which label it gets bound to. A policy becomes active only when it is bound. A globally bound policy, it is available to all virtual servers on the NetScaler appliance. All HTTP traffic is evaluated against the global policy labels. Each label contains an ordered list ordered by policies' priority values.


##Synopsys

bind cache global &lt;policy> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policy</b>
Name of the policy to bind. (A policy must be created before it can be bound.)

<b>priority</b>
Priority to assign to the policy. The appliance might disallow some priority values, depending on what you have already configured. For example, a response cache policy cannot have a higher priority than a request cache policy. Priority helps in dictating the order of policy evaluation.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the priority of the next policy to evaluate if the current policy rule evaluates to TRUE. Specify one of the following values:
* END. Terminate evaluation of this policy bank. This setting is equivalent to omitting the parameter. 
* NEXT. Evaluate the policy with the next higher priority.
* An expression whose evaluation results in a number.
Evaluation of an expression determines the next action as follows:
* If the expression evaluates to a priority number larger than the highest priority number in the policy bank, the next policy bank is evaluated. 
* If the expression evaluates to the priority of a policy with a lower priority (higher number) within the same policy bank, that policy is evaluated next. 
* If the expression evaluates to the priority of the current policy, the policy with the next-lower priority is evaluated next.
Any of the following results trigger an UNDEF condition
* The expression cannot be evaluated.
* The expression evaluates to a number that is smaller than the current policy's priority number

<b>type</b>
Bind point, specifying where to bind the policy.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority. Applicable only to default-syntax policies.

<b>labelType</b>
Type of policy label to invoke.
Possible values: reqvserver, resvserver, policylabel

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE. (To invoke a label associated with a virtual server, specify the name of the virtual server.)



##unbind cache global

Deactivate the policy by unbinding it from a global bind point.


##Synopsys

unbind cache global &lt;policy> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policy</b>
Name of the policy to unbind.

<b>type</b>
Bind point from which to unbind the policy.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound. Required only you want to unbind a NOPOLICY that might have been bound to this policy label.
Minimum value: 1
Maximum value: 2147483647



##show cache global

Displays the global bindings for cache policies.


##Synopsys

show cache global [-type &lt;type>]


##Arguments

<b>type</b>
The bind point to which policy is bound. When you specify the type, detailed information about that bind point appears.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT



##Outputs

<b>policyName</b>
Name of the cache policy.

<b>policy</b>
Name of the cache policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority. Applicable only to default-syntax policies.

<b>labelType</b>
Type of policy label to invoke.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE. (To invoke a label associated with a virtual server, specify the name of the virtual server.)

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flowType</b>
flowtype of the bound cache policy.

<b>rule</b>
The request/response rule that will trigger the given action.

<b>action</b>
The integrated cache action to be applied when the system sees content that matches the rules.

<b>storeInGroup</b>
The content group to store the object when the action directive is CACHE.

<b>invalGroups</b>
The content group(s) to be invalidated when the action directive is INVAL.

<b>invalObjects</b>
The content group(s) whose objects will be invalidated when the action directive is INVAL.

<b>hits</b>
Hits.

<b>flags</b>
Flags.

<b>precedeDefRules</b>
Override the default request/response cacheability rules.

<b>stateflag</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show cache global

