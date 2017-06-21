#authentication loginSchemaPolicy

The following operations can be performed on "authentication loginSchemaPolicy":


[add](#add-authentication-loginschemapolicy) | [rm](#rm-authentication-loginschemapolicy) | [set](#set-authentication-loginschemapolicy) | [unset](#unset-authentication-loginschemapolicy) | [show](#show-authentication-loginschemapolicy) | [stat](#stat-authentication-loginschemapolicy) | [rename](#rename-authentication-loginschemapolicy)

##add authentication loginSchemaPolicy

Adds a LoginSchema policy for use in login parameter selection.


##Synopsys

add authentication loginSchemaPolicy &lt;name> -rule &lt;expression> -action &lt;string> [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the LoginSchema policy. This is used for selecting parameters for user logon. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
Expression which is evaluated to choose a profile for authentication.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the profile to apply to requests or connections that match this policy.
* NOOP - Do not take any specific action when this policy evaluates to true. This is useful to implicitly go to a different policy set.
* RESET - Reset the client connection by closing it. The client program, such as a browser, will handle this and may inform the user. The client may then resend the request if desired.
* DROP - Drop the request without sending a response to the user.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##rm authentication loginSchemaPolicy

Removes an existing LoginSchema policy.


##Synopsys

rm authentication loginSchemaPolicy &lt;name>


##Arguments

<b>name</b>
Name of the policy to remove.



##set authentication loginSchemaPolicy

Modifies the specified parameters of an existing policy.


##Synopsys

set authentication loginSchemaPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name of the policy to modify.

<b>rule</b>
Expression which is evaluated to choose a profile for authentication.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the profile to apply to requests or connections that match this policy.
* NOOP - Do not take any specific action when this policy evaluates to true. This is useful to implicitly go to a different policy set.
* RESET - Reset the client connection by closing it. The client program, such as a browser, will handle this and may inform the user. The client may then resend the request if desired.
* DROP - Drop the request without sending a response to the user.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##unset authentication loginSchemaPolicy

Removes the settings of an existing policy. Attributes for which a default value is available revert to their default values. See the set LoginSchemaPolicy command for a description of the parameters..Refer to the set authentication loginSchemaPolicy command for meanings of the arguments.


##Synopsys

unset authentication loginSchemaPolicy &lt;name> [-undefAction] [-comment] [-logAction]


##Example

unset LoginSchemaPolicy pol9 -undefAction

##show authentication loginSchemaPolicy

Displays information about all configured LoginSchema policies, or displays detailed information about the specified policy.


##Synopsys

show authentication loginSchemaPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the LoginSchema policy for which to display detailed information.



##Outputs

<b>rule</b>
The rule used by the LoginSchema authentication policy. Rules are combinations of Expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide

<b>action</b>
The action to be performed when the rule is matched.

<b>stateflag</b>

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>hits</b>
Number of hits.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>undefHits</b>
Number of Undef hits.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>builtin</b>
Flag to determine if policy is built-in or not

<b>devno</b>

<b>count</b>



##stat authentication loginSchemaPolicy

Display LoginSchema policy statistics.


##Synopsys

stat authentication loginSchemaPolicy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
The name of the LoginSchema policy for which statistics will be displayed.  If not given statistics are shown for all policies.

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

stat authentication loginschemapolicy.

##Related Commands

<ul><li><a href="../../../ation-policy.html#stat-authentication-p/ation-policy.html#stat-authentication-p">stat authentication Policy</a></li><li><a href="../../../ation-vserver.html#stat-authentication-vs/ation-vserver.html#stat-authentication-vs">stat authentication vserver</a></li><li><a href="../../../ation-samlidppolicy.html#stat-authentication-samlidpp/ation-samlidppolicy.html#stat-authentication-samlidpp">stat authentication samlIdPPolicy</a></li><li><a href="../../../ation-policylabel.html#stat-authentication-policy/ation-policylabel.html#stat-authentication-policy">stat authentication policylabel</a></li></ul>



##rename authentication loginSchemaPolicy

Renames the specified LoginSchema policy.


##Synopsys

rename authentication loginSchemaPolicy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the LoginSchema policy.

<b>newName</b>
New name for the LoginSchema policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my loginschemapolicy policy" or 'my loginschemapolicy policy').



##Example

rename loginschemapolicy oldname newname

