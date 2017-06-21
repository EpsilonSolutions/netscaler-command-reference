#aaa preauthenticationpolicy

The following operations can be performed on "aaa preauthenticationpolicy":


[add](#add-aaa-preauthenticationpolicy) | [rm](#rm-aaa-preauthenticationpolicy) | [set](#set-aaa-preauthenticationpolicy) | [show](#show-aaa-preauthenticationpolicy)

##add aaa preauthenticationpolicy

Adds a preauthentication policy. The policy defines expressions to be evaluated by the endpoint analysis (EPA) tool.


##Synopsys

add aaa preauthenticationpolicy &lt;name> &lt;rule> [&lt;reqAction>]


##Arguments

<b>name</b>
Name for the preauthentication policy. Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the preauthentication policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my policy? or ?my policy?).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, defining connections that match the policy.

<b>reqAction</b>
Name of the action that the policy is to invoke when a connection matches the policy.



##rm aaa preauthenticationpolicy

Removes the specified preauthentication policy.


##Synopsys

rm aaa preauthenticationpolicy &lt;name>


##Arguments

<b>name</b>
Name of the preauthentication policy to remove.



##set aaa preauthenticationpolicy

Modifies the Request Action of a preauthentication policy.


##Synopsys

set aaa preauthenticationpolicy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the preauthentication policy to modifiy.

<b>rule</b>
The new rule to be associated with the policy.

<b>reqAction</b>
Name of the action that the policy is to invoke when a connection matches the policy.



##show aaa preauthenticationpolicy

Displays the properties of either the specified preauthentication policy or (if none is specified) a list of all configured preauthentication policies.


##Synopsys

show aaa preauthenticationpolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the preauthentication policy whose properties you want to view.



##Outputs

<b>rule</b>
The new rule associated with the policy.

<b>reqAction</b>
The Pre-authentication action associated with the policy.

<b>hits</b>
No of hits.

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



