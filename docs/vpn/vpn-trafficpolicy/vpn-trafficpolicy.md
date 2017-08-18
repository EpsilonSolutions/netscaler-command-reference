#vpn trafficPolicy

The following operations can be performed on "vpn trafficPolicy":


[add](#add-vpn-trafficpolicy) | [rm](#rm-vpn-trafficpolicy) | [set](#set-vpn-trafficpolicy) | [unset](#unset-vpn-trafficpolicy) | [show](#show-vpn-trafficpolicy)

##add vpn trafficPolicy

Creates a traffic policy. A traffic policy conditionally sets NetScaler Gateway traffic characteristics at run time. For an intranet resource, for example, the traffic policy parameters define the destination IP address, destination port, amount of time a user can stay logged on to the application, and HTTP compression.


##Synopsys

add vpn trafficPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the traffic policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to apply to traffic that matches the policy.



##rm vpn trafficPolicy

Removes an existing traffic policy from NetScaler Gateway.


##Synopsys

rm vpn trafficPolicy &lt;name>


##Arguments

<b>name</b>
Name of the traffic policy to remove.



##set vpn trafficPolicy

Modifies the specified parameters of an existing traffic policy.


##Synopsys

set vpn trafficPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the traffic policy to modify.

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to apply to traffic that matches the policy.



##unset vpn trafficPolicy

Use this command to remove vpn trafficPolicy settings.Refer to the set vpn trafficPolicy command for meanings of the arguments.


##Synopsys

unset vpn trafficPolicy &lt;name> [-rule] [-action]


##show vpn trafficPolicy

Displays information about all NetScaler Gateway traffic policies, or detailed information about the specified policy.


##Synopsys

show vpn trafficPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the traffic policy for which to display detailed information.



##Outputs

<b>rule</b>
The rule used by the vpn traffic policy. Rules are combinations of expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide

<b>action</b>
The action to be performed when the rule is matched.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>expressionType</b>
Type of policy (Classic/Advanced)

<b>hits</b>
Number of hits.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



