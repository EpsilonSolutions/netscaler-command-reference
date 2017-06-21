#audit nslogPolicy

The following operations can be performed on "audit nslogPolicy":


[add](#add-audit-nslogpolicy) | [rm](#rm-audit-nslogpolicy) | [set](#set-audit-nslogpolicy) | [show](#show-audit-nslogpolicy)

##add audit nslogPolicy

Adds a policy that defines which messages to log to the specified nslog server.


##Synopsys

add audit nslogPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the policy. 
Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the nslog policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my nslog policy? or ?my nslog policy?).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that defines the messages to be logged to the nslog server.

<b>action</b>
Nslog server action that is performed when this policy matches.
NOTE: An nslog server action must be associated with an nslog audit policy.



##rm audit nslogPolicy

Removes the specified nslog policy and associated configuration.


##Synopsys

rm audit nslogPolicy &lt;name>


##Arguments

<b>name</b>
Name of the nslog policy to remove.



##set audit nslogPolicy

Modifies the specified parametrers of an existing nslog policy.


##Synopsys

set audit nslogPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the nslog policy to modify.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that defines the messages to be logged to the nslog server.

<b>action</b>
Nslog server action that is performed when this policy matches.
NOTE: An nslog server action must be associated with an nslog audit policy.



##show audit nslogPolicy

Displays the current configuration of the specified nslog policy.If no nslog policy is specified, displays a list of all nslog policies currently configured on the NetScaler appliance.


##Synopsys

show audit nslogPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the policy.



##Outputs

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that defines the messages to be logged to the nslog server.

<b>action</b>
Nslog server action that is performed when this policy matches.
NOTE: An nslog server action must be associated with an nslog audit policy.

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



