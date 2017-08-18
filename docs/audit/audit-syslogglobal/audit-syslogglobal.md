#audit syslogGlobal

The following operations can be performed on "audit syslogGlobal":


[bind](#bind-audit-syslogglobal) | [unbind](#unbind-audit-syslogglobal) | [show](#show-audit-syslogglobal)

##bind audit syslogGlobal

binds audit syslog policy to audit syslogGlobal


##Synopsys

bind audit syslogGlobal -policyName &lt;string> -priority &lt;positive_integer> [-globalBindType &lt;globalBindType>]


##Arguments

<b>policyName</b>
Name of the audit syslog policy.

<b>priority</b>
Specifies the priority of the policy.
Minimum value: 1
Maximum value: 2147483647

<b>globalBindType</b>



##Example

bind audit syslogGlobal -policyname pol9 -priority 9

##unbind audit syslogGlobal

Unbind the specified audit syslog policy from audit syslogGlobal.


##Synopsys

unbind audit syslogGlobal [&lt;policyName>] [-globalBindType &lt;globalBindType>]


##Arguments

<b>policyName</b>
Name of the policy to unbind.

<b>globalBindType</b>



##Example

unbind audit syslogGlobal pol9

##show audit syslogGlobal

Displays the list of policies bound to the specified audit syslogGlobal bind point.


##Synopsys

show audit syslogGlobal


##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the audit syslog policy.

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

show audit syslogGlobal

