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



##unbind cache global

Deactivate the policy by unbinding it from a global bind point.


##Synopsys

unbind cache global &lt;policy> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policy</b>
Name of the policy to unbind.

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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>policyName</b>
Name of the cache policy.NOTE: This attribute is deprecated.Replaced by Policy field

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
The request/response rule that will trigger the given action.NOTE: This attribute is deprecated.

<b>action</b>
The integrated cache action to be applied when the system sees content that matches the rules.NOTE: This attribute is deprecated.

<b>storeInGroup</b>
The content group to store the object when the action directive is CACHE.NOTE: This attribute is deprecated.

<b>invalGroups</b>
The content group(s) to be invalidated when the action directive is INVAL.NOTE: This attribute is deprecated.

<b>invalObjects</b>
The content group(s) whose objects will be invalidated when the action directive is INVAL.

<b>hits</b>
Hits.NOTE: This attribute is deprecated.

<b>flags</b>
Flags.NOTE: This attribute is deprecated.

<b>precedeDefRules</b>
Override the default request/response cacheability rules.NOTE: This attribute is deprecated.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

show cache global

