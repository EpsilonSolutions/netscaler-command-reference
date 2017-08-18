#videooptimization policy

The following operations can be performed on "videooptimization policy":


[add](#add-videooptimization-policy) | [rm](#rm-videooptimization-policy) | [set](#set-videooptimization-policy) | [unset](#unset-videooptimization-policy) | [show](#show-videooptimization-policy) | [rename](#rename-videooptimization-policy) | [stat](#stat-videooptimization-policy)

##add videooptimization policy

Creates a videooptimization policy, which specifies requests that the NetScaler appliance intercepts and tries to detect media type.


##Synopsys

add videooptimization policy &lt;name> -rule &lt;expression> -action &lt;string> [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the videooptimization policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.Can be modified, removed or renamed.

<b>rule</b>
Expression that determines which request or response match the video optimization policy. Written in default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character.
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the videooptimization action to perform if the request matches this videooptimization policy. Built-in actions should be used. These are:
* DETECT_CLEARTEXT_PD - Cleartext PD is detected and increment related counters.
* DETECT_CLEARTEXT_ABR - Cleartext ABR is detected and increment related counters.
* DETECT_ENCRYPTED_ABR - Encrypted ABR is detected and increment related counters.
* TRIGGER_ENC_ABR_DETECTION - This is possible encrypted ABR. Internal traffic heuristics algorithms will further process traffic to confirm detection.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any type of information about this videooptimization policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.



##Example

i) add videooptimization policy pol1 -rule "HTTP.REQ.URL.CONTAINS(\\".mov\\")" -action DETECT_CLEARTEXT_PD

##rm videooptimization policy

Removes the specified videooptimization policy.


##Synopsys

rm videooptimization policy &lt;name>


##Arguments

<b>name</b>
Name for the videooptimization policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.Can be modified, removed or renamed.



##Example

rm videooptimization policy pol1

##set videooptimization policy

Modifies the specified parameter of the videooptimization policy.


##Synopsys

set videooptimization policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the videooptimization policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.Can be modified, removed or renamed.

<b>rule</b>
Expression that determines which request or response match the video optimization policy. Written in default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character.
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the videooptimization action to perform if the request matches this videooptimization policy. Built-in actions should be used. These are:
* DETECT_CLEARTEXT_PD - Cleartext PD is detected and increment related counters.
* DETECT_CLEARTEXT_ABR - Cleartext ABR is detected and increment related counters.
* DETECT_ENCRYPTED_ABR - Encrypted ABR is detected and increment related counters.
* TRIGGER_ENC_ABR_DETECTION - This is possible encrypted ABR. Internal traffic heuristics algorithms will further process traffic to confirm detection.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any type of information about this videooptimization policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.



##Example

set videooptimization policy pol1 -rule "HTTP.REQ.URL.CONTAINS(\\".flv\\")" -action DETECT_CLEARTEXT_PD

##unset videooptimization policy

Removes the settings of an existing videooptimization policy. Attributes for which a default value is available revert to their default values. See the set video opt policy command for descriptions of the parameters..Refer to the set videooptimization policy command for meanings of the arguments.


##Synopsys

unset videooptimization policy &lt;name> [-undefAction] [-comment] [-logAction]


##Example

unset videooptimization policy media_pol1 -undefAction

##show videooptimization policy

Displays the current settings for the specified videooptimization policy.


##Synopsys

show videooptimization policy [&lt;name>]show videooptimization policy stats - alias for 'stat videooptimization policy'


##Arguments

<b>name</b>
Name of the video opt policy for which to display settings.Must provide policy name.



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression that determines which request or response match the video optimization policy. Written in default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters>" + "&lt;string of 245 characters>"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character.
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the videooptimization action to perform if the request matches this videooptimization policy. Built-in actions should be used. These are:
* DETECT_CLEARTEXT_PD - Cleartext PD is detected and increment related counters.
* DETECT_CLEARTEXT_ABR - Cleartext ABR is detected and increment related counters.
* DETECT_ENCRYPTED_ABR - Encrypted ABR is detected and increment related counters.
* TRIGGER_ENC_ABR_DETECTION - This is possible encrypted ABR. Internal traffic heuristics algorithms will further process traffic to confirm detection.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of policy UNDEF hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>comment</b>
Any type of information about this videooptimization policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>vserverType</b>

<b>builtin</b>
Flag to determine if videooptimization policy is built-in or not

<b>devno</b>

<b>count</b>



##Example

show videooptimization policy pol1

##rename videooptimization policy

Renames the specified videooptimization policy.


##Synopsys

rename videooptimization policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the videooptimization policy.

<b>newName</b>
New name for the videooptimization policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.



##Example

rename videooptimization policy oldname newname

##stat videooptimization policy

Displays statistics for all video optimization policies currently configured on the NetScaler appliance, or detailed statistics for the specified policy.


##Synopsys

stat videooptimization policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the Video Optimization policy for which to show detailed statistics.

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



##Related Commands

<ul><li><a href="../../../ptimization.html#stat-videooptimiz/ptimization.html#stat-videooptimiz">stat videooptimization</a></li><li><a href="../../../ptimization-policylabel.html#stat-videooptimization-policy/ptimization-policylabel.html#stat-videooptimization-policy">stat videooptimization policylabel</a></li></ul>



