#transform policy

The following operations can be performed on "transform policy":


[add](#add-transform-policy) | [rm](#rm-transform-policy) | [set](#set-transform-policy) | [unset](#unset-transform-policy) | [show](#show-transform-policy) | [stat](#stat-transform-policy) | [rename](#rename-transform-policy)

##add transform policy

Creates a URL Transformation policy, which specifies the requests and responses to be transformed by the associated profile.


##Synopsys

add transform policy &lt;name> &lt;rule> &lt;profileName> [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the URL Transformation policy.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the URL Transformation policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform policy? or ?my transform policy).

<b>rule</b>
Expression, or name of a named expression, against which to evaluate traffic. Can be written in either default or classic syntax. Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>profileName</b>
Name of the URL Transformation profile to use to transform requests and responses that match the policy.

<b>comment</b>
Any comments to preserve information about this URL Transformation policy.

<b>logAction</b>
Log server to use to log connections that match this policy.



##rm transform policy

Removes the specified URL Transformation policy.


##Synopsys

rm transform policy &lt;name>


##Arguments

<b>name</b>
Name of the policy to remove.



##Example

rm transform policy trans_pol

##set transform policy

Modifies the specified parameters of a URL Transformation policy.


##Synopsys

set transform policy &lt;name> [-rule &lt;expression>] [-profileName &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name of the policy to modify.

<b>rule</b>
Expression, or name of a named expression, against which to evaluate traffic. Can be written in either default or classic syntax. Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>profileName</b>
Name of the URL Transformation profile to use to transform requests and responses that match the policy.

<b>comment</b>
Any comments to preserve information about this URL Transformation policy.

<b>logAction</b>
Log server to use to log connections that match this policy.



##Example

set transform policy pol9 -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset transform policy

Removes the settings of an existing URL Transformation policy. Attributes for which a default value is available revert to their default values. See the set transform policy command for a description of the parameters..Refer to the set transform policy command for meanings of the arguments.


##Synopsys

unset transform policy &lt;name> [-comment] [-logAction]


##Example

unset transform policy pol9 -undefAction

##show transform policy

Displays the current settings for the specified URL Transformation policy.If no policy name is specified, displays a list of all URL Transformation policies currently configured on the NetScaler appliance.


##Synopsys

show transform policy [&lt;name>]


##Arguments

<b>name</b>
Name of the URL Transformation policy.



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression, or name of a named expression, against which to evaluate traffic. Can be written in either default or classic syntax. Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters>" + "&lt;string of 245 characters>"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>profileName</b>
Name of the URL Transformation profile to use to transform requests and responses that match the policy.

<b>priority</b>
Specifies the priority of the policy.

<b>hits</b>
Number of hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>comment</b>
Any comments to preserve information about this URL Transformation policy.

<b>logAction</b>
Log server to use to log connections that match this policy.

<b>bindPolicyType</b>

<b>isDefault</b>
A value of true is returned if it is a default transform policy.

<b>vserverType</b>

<b>devno</b>

<b>count</b>



##stat transform policy

Displays statistics for the specified URL Transformation policy.If no policy name is specified, displays abbreviated statistics for all URL Transformation policies currently configured on the NetScaler appliance.


##Synopsys

stat transform policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the policy.

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

stat transform policy

##Related Commands

<ul><li><a href="../../../cylabel.html#stat-transform-policy/cylabel.html#stat-transform-policy">stat transform policylabel</a></li></ul>



##rename transform policy

Renames a URL Transformation policy.


##Synopsys

rename transform policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the policy.

<b>newName</b>
New name for the policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform policy? or ?my transform policy).



##Example

rename transform policy oldname newname

