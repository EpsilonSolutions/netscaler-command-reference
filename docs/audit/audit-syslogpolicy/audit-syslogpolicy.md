#audit syslogPolicy

The following operations can be performed on "audit syslogPolicy":


[add](#add-audit-syslogpolicy) | [rm](#rm-audit-syslogpolicy) | [set](#set-audit-syslogpolicy) | [show](#show-audit-syslogpolicy)

##add audit syslogPolicy

Adds a policy that defines which messages to log to the specified syslog server.


##Synopsys

add audit syslogPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the policy. 
Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the syslog policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my syslog policy? or ?my syslog policy).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that defines the messages to be logged to the syslog server.

<b>action</b>
Syslog server action to perform when this policy matches traffic.
NOTE: A syslog server action must be associated with a syslog audit policy.



##rm audit syslogPolicy

Removes the specified syslog policy and associated configuration.


##Synopsys

rm audit syslogPolicy &lt;name>


##Arguments

<b>name</b>
Name of the syslog policy to remove.



##set audit syslogPolicy

Configures an existing syslog policy.


##Synopsys

set audit syslogPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the syslog policy to be configured.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that defines the messages to be logged to the syslog server.

<b>action</b>
Syslog server action to perform when this policy matches traffic.
NOTE: A syslog server action must be associated with a syslog audit policy.



##show audit syslogPolicy

Displays the current configuration of the specified syslog policy.If no syslog policy is specified, displays a list of all syslog policies currently configured on the NetScaler appliance.


##Synopsys

show audit syslogPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the policy.



##Outputs

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that defines the messages to be logged to the syslog server.

<b>action</b>
Syslog server action to perform when this policy matches traffic.
NOTE: A syslog server action must be associated with a syslog audit policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



