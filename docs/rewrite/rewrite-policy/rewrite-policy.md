#rewrite policy

The following operations can be performed on "rewrite policy":


[add](#add-rewrite-policy) | [rm](#rm-rewrite-policy) | [set](#set-rewrite-policy) | [unset](#unset-rewrite-policy) | [show](#show-rewrite-policy) | [stat](#stat-rewrite-policy) | [rename](#rename-rewrite-policy)

##add rewrite policy

Creates a rewrite policy, which specifies which requests or responses to rewrite.


##Synopsys

add rewrite policy &lt;name> &lt;rule> &lt;action> [&lt;undefAction>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the rewrite policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the rewrite policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rewrite policy" or ?my rewrite policy?).

<b>rule</b>
Expression against which traffic is evaluated. Written in default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the rewrite action to perform if the request or response matches this rewrite policy.
There are also some built-in actions which can be used. These are:
* NOREWRITE - Send the request from the client to the server or response from the server to the client without making any changes in the message.
* RESET - Resets the client connection by closing it. The client program, such as a browser, will handle this and may inform the user. The client may then resend the request if desired.
* DROP - Drop the request without sending a response to the user.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this rewrite policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##Example

i)	add rewrite policy pol9 "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh3\\\\")" act_insertii)	add rewrite policy pol9 "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh3\\\\")" act_insert NOREWRITEiii)	add rewrite policy pol9 "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh3\\\\")" act_insert RESETiii)	add rewrite policy pol9 "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh3\\\\")" act_insert DROP

##rm rewrite policy

Removes the specified rewrite policy.


##Synopsys

rm rewrite policy &lt;name>


##Arguments

<b>name</b>
Name of the rewrite policy to be removed.



##Example

rm rewrite policy pol9

##set rewrite policy

Modifies the specified parameters of a rewrite policy.


##Synopsys

set rewrite policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name of the rewrite policy to modify.

<b>rule</b>
Expression against which traffic is evaluated. Written in default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the rewrite action to perform if the request or response matches this rewrite policy.
There are also some built-in actions which can be used. These are:
* NOREWRITE - Send the request from the client to the server or response from the server to the client without making any changes in the message.
* RESET - Resets the client connection by closing it. The client program, such as a browser, will handle this and may inform the user. The client may then resend the request if desired.
* DROP - Drop the request without sending a response to the user.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this rewrite policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##Example

set rewrite policy pol9 -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset rewrite policy

Removes the settings of an existing rewrite policy. Attributes for which a default value is available revert to their default values. See the set rewrite policy command for a description of the parameters..Refer to the set rewrite policy command for meanings of the arguments.


##Synopsys

unset rewrite policy &lt;name> [-undefAction] [-comment] [-logAction]


##Example

unset rewrite policy pol9 -undefAction

##show rewrite policy

Displays the current settings for the specified rewrite policy.If no policy name is provided, displays a list of all rewrite policies currently configured on the NetScaler appliance.


##Synopsys

show rewrite policy [&lt;name>]show rewrite policy stats - alias for 'stat rewrite policy'


##Arguments

<b>name</b>
Name of the rewrite policy.



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression against which traffic is evaluated. Written in default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters>" + "&lt;string of 245 characters>"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Rewrite action associated with the policy.

<b>undefAction</b>
Undef Action associated with the policy.

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of Undef hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>description</b>
Description of the policy

<b>comment</b>
Any comments to preserve information about this rewrite policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.

<b>bindPolicyType</b>

<b>isDefault</b>
A value of true is returned if it is a default rewritepolicy.

<b>vserverType</b>

<b>builtin</b>
Flag to determine if rewrite policy is built-in or not

<b>devno</b>

<b>count</b>



##Example

show rewrite policy

##stat rewrite policy

Displays statistics for the specified rewrite policy.If no policy name is specified, displays abbreviated statistics for all rewrite policies currently configured on the NetScaler appliance.


##Synopsys

stat rewrite policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the rewrite policy.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Policy hits (Hits)</b>
Number of hits on the policy

<b>Policy undef hits (Undefhits)</b>
Number of undef hits on the policy



##Example

stat rewrite policy

##Related Commands

<ul><li><a href="../../../bel.html#stat-rewrite-policy/bel.html#stat-rewrite-policy">stat rewrite policylabel</a></li></ul>



##rename rewrite policy

Renames the specified rewrite policy. You must restart the NetScaler appliance to put new name in effect.


##Synopsys

rename rewrite policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the rewrite policy.

<b>newName</b>
New name for the rewrite policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rewrite policy" or ?my rewrite policy?).



##Example

rename rewrite policy oldname newname

