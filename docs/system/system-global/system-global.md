#system global

The following operations can be performed on "system global":


[bind](#bind-system-global) | [unbind](#unbind-system-global) | [show](#show-system-global)

##bind system global

Binds policies globally.


##Synopsys

bind system global [&lt;policyName>  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the policy to bind globally.



##unbind system global

Unbinds a globally bound policy.


##Synopsys

unbind system global &lt;policyName>


##Arguments

<b>policyName</b>
Name of the globally bound policy to unbind.



##show system global

Displays information about all global policy bindings.


##Synopsys

show system global


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>policyName</b>
The name of the  command policy.

<b>priority</b>
The priority of the command policy.

<b>bindPolicyType</b>
Bound policy type

<b>policySubType</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



