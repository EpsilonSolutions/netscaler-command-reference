#tm sessionPolicy

The following operations can be performed on "tm sessionPolicy":


[add](#add-tm-sessionpolicy) | [rm](#rm-tm-sessionpolicy) | [set](#set-tm-sessionpolicy) | [unset](#unset-tm-sessionpolicy) | [show](#show-tm-sessionpolicy)

##add tm sessionPolicy

Creates a traffic management (TM) session policy, which is applied after the user logs on to the AAA virtual server, to customize user sessions.


##Synopsys

add tm sessionPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the session policy. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after a session policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to be applied to connections that match this policy.



##rm tm sessionPolicy

Removes an existing traffic management (TM) session policy.


##Synopsys

rm tm sessionPolicy &lt;name>


##Arguments

<b>name</b>
Name of the session policy to remove.



##set tm sessionPolicy

Modifies the rule or action of an existing traffic management (TM) session policy.


##Synopsys

set tm sessionPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the session policy to modify.

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to be applied to connections that match this policy.



##unset tm sessionPolicy

Use this command to remove tm sessionPolicy settings.Refer to the set tm sessionPolicy command for meanings of the arguments.


##Synopsys

unset tm sessionPolicy &lt;name> [-rule] [-action]


##show tm sessionPolicy

Displays information about all the configured traffic management (TM) session policies, or displays detailed information about the specified TM session policy.


##Synopsys

show tm sessionPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the session policy for which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters>" + "&lt;string of 245 characters>"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to be applied to connections that match this policy.

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



