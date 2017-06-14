#tm global

The following operations can be performed on "tm global":


[bind](#bind-tm-global) | [unbind](#unbind-tm-global) | [show](#show-tm-global)

##bind tm global

Binds traffic, sessions, nslog, and syslog policies to traffic management (TM) Global.


##Synopsys

bind tm global [-policyName &lt;string>  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the policy that you are binding.



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


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>devno</b>

<b>count</b>



