#policy expression

The following operations can be performed on "policy expression":


[add](#add-policy-expression) | [rm](#rm-policy-expression) | [set](#set-policy-expression) | [unset](#unset-policy-expression) | [show](#show-policy-expression)

##add policy expression

Creates a classic or default syntax named expression, which can be used in multiple policies. For example, you can create the following named expressions, ExpressionA and ExpressionB:ExpressionA: http.req.body(100).contains("A")ExpressionB: http.req.body(100).contains("B")You could then create an expression of the form: &lt;ExpressionA || ExpressionB>


##Synopsys

add policy expression &lt;name> &lt;value> [-comment &lt;string>] [-clientSecurityMessage &lt;string>]


##Arguments

<b>name</b>
Unique name for the expression. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters. Must not begin with 're' or 'xp' or be a word reserved for use as a default syntax expression qualifier prefix (such as HTTP) or enumeration value (such as ASCII). Must not be the name of an existing named expression, pattern set, dataset, stringmap, or HTTP callout.

<b>value</b>
Expression string. For example: http.req.body(100).contains("this").

<b>comment</b>
Any comments associated with the expression. Displayed upon viewing the policy expression.

<b>clientSecurityMessage</b>
Message to display if the expression fails. Allowed for classic end-point check expressions only.



##rm policy expression

Removes a named policy expression. If the expression is used by a policy or filter, you must remove the policy or filter before removing the expression.


##Synopsys

rm policy expression &lt;name> ...


##Arguments

<b>name</b>
Name of the policy expression to be removed.



##set policy expression

Modifies the attributes of a named policy expression.


##Synopsys

set policy expression &lt;name> [&lt;value>] [-comment &lt;string>] [-clientSecurityMessage &lt;string>]


##Arguments

<b>name</b>
Name of the policy expression to be modified.

<b>value</b>
The expression string.

<b>comment</b>
Any comments associated with the expression. Displayed upon viewing the policy expression.

<b>clientSecurityMessage</b>
The client security message that will be displayed on failure of this expression. Only relevant for end point check expressions.



##unset policy expression

Use this command to remove policy expression settings.Refer to the set policy expression command for meanings of the arguments.


##Synopsys

unset policy expression &lt;name> [-comment] [-clientSecurityMessage]


##show policy expression

Displays information about the available named policy expressions.


##Synopsys

show policy expression [&lt;name> | -type ( CLASSIC | ADVANCED )]


##Arguments

<b>name</b>
Name of the policy expression to display. If a name is not provided, information about all policy expressions is shown.

<b>type</b>
Type of expression. Can be a classic or default syntax (advanced) expression.
Possible values: CLASSIC, ADVANCED



##Outputs

<b>value</b>
The expression string.

<b>hits</b>
The total number of hits.

<b>piHits</b>
The total number of hits.

<b>type</b>
The type of expression. This is for output only.

<b>clientSecurityMessage</b>
The client security message that will be displayed on failure of the client security check.

<b>description</b>
Description for the expression.

<b>comment</b>
Any comments associated with the expression. Displayed upon viewing the policy expression.

<b>stateflag</b>

<b>flag</b>

<b>isDefault</b>
A value of true is returned if it is a default policy expression.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>



