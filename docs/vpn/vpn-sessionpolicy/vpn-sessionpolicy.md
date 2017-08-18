#vpn sessionPolicy

The following operations can be performed on "vpn sessionPolicy":


[add](#add-vpn-sessionpolicy) | [rm](#rm-vpn-sessionpolicy) | [set](#set-vpn-sessionpolicy) | [unset](#unset-vpn-sessionpolicy) | [show](#show-vpn-sessionpolicy)

##add vpn sessionPolicy

Creates a new session policy that, if bound, is applied after the user logs on to NetScaler Gateway, and that determines the properties of the user session.


##Synopsys

add vpn sessionPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the new session policy that is applied after the user logs on to NetScaler Gateway.

<b>rule</b>
Expression, or name of a named expression, specifying the traffic that matches the policy. Can be written in either default or classic syntax. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to be applied by the new session policy if the rule criteria are met.



##rm vpn sessionPolicy

Removes the session policy that is applied after the user logs on to NetScaler Gateway.


##Synopsys

rm vpn sessionPolicy &lt;name>


##Arguments

<b>name</b>
Name of the session policy to remove.



##set vpn sessionPolicy

Modifies the rule or action of a session policy.


##Synopsys

set vpn sessionPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the session policy to modify.

<b>rule</b>
Expression, or name of a named expression, specifying the traffic that matches the policy. Can be written in either default or classic syntax. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to be applied by the new session policy if the rule criteria are met.



##unset vpn sessionPolicy

Use this command to remove vpn sessionPolicy settings.Refer to the set vpn sessionPolicy command for meanings of the arguments.


##Synopsys

unset vpn sessionPolicy &lt;name> [-rule] [-action]


##show vpn sessionPolicy

Displays a session policy.


##Synopsys

show vpn sessionPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the session policy to display.



##Outputs

<b>rule</b>
The new rule associated with the policy. Rules are combinations of expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide.

<b>action</b>
The new vpn session action the policy is using.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>expressionType</b>
Type of policy (Classic/Advanced)

<b>hits</b>
Number of hits.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



