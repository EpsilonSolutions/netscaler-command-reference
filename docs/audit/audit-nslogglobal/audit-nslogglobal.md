#audit nslogGlobal

The following operations can be performed on "audit nslogGlobal":


[bind](#bind-audit-nslogglobal) | [unbind](#unbind-audit-nslogglobal) | [show](#show-audit-nslogglobal)

##bind audit nslogGlobal

binds audit nslog policy to audit nslogGlobal


##Synopsys

bind audit nslogGlobal -policyName &lt;string> -priority &lt;positive_integer> [-globalBindType &lt;globalBindType>]


##Arguments

<b>policyName</b>
Name of the audit nslog policy.

<b>priority</b>
Specifies the priority of the policy.
Minimum value: 1
Maximum value: 2147483647

<b>globalBindType</b>



##Example

bind audit nslogGlobal -policyname pol9 -priority 9

##unbind audit nslogGlobal

Unbind the specified audit nslog policy from audit nslogGlobal.


##Synopsys

unbind audit nslogGlobal [&lt;policyName>] [-globalBindType &lt;globalBindType>]


##Arguments

<b>policyName</b>
Name of the policy to unbind.

<b>globalBindType</b>



##Example

unbind audit nslogGlobal pol9

##show audit nslogGlobal

Displays the list of policies bound to audit nslogGlobal bind point.


##Synopsys

show audit nslogGlobal


##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the audit nslog policy.

<b>priority</b>
Specifies the priority of the policy.

<b>numpol</b>
number of polices bound to label.

<b>flags</b>

<b>globalBindType</b>

<b>type</b>
The bindpoint to which the policy is bound

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>



##Example

show audit nslogGlobal

