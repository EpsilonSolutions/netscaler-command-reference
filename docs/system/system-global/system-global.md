#system global

The following operations can be performed on "system global":


[bind](#bind-system-global) | [unbind](#unbind-system-global) | [show](#show-system-global)

##bind system global

Binds policies globally.


##Synopsys

bind system global [&lt;policyName>  [-priority &lt;positive_integer>]  [-nextFactor &lt;string>]  [-gotoPriorityExpression &lt;expression>]]


##Arguments

<b>policyName</b>
Name of the policy to bind globally.

<b>priority</b>
Integer specifying the priority of the policy. A lower number specifies a higher priority. Policies are evaluated in the order of their priority numbers. Note that priority range 64001 to 65535 is reserved for internal system usage of binding policies by default
Minimum value: 0

<b>nextFactor</b>
On success invoke label. Applicable for advanced authentication policy binding

<b>gotoPriorityExpression</b>
Applicable only to advance authentication policy. Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.



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

<b>globalBindType</b>

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE. Applicable only for advanced authentication policies

<b>nextFactor</b>
On success invoke label. Applicable for advanced authentication policy binding

<b>devno</b>

<b>count</b>



