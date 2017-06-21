#tm trafficPolicy

The following operations can be performed on "tm trafficPolicy":


[add](#add-tm-trafficpolicy) | [rm](#rm-tm-trafficpolicy) | [set](#set-tm-trafficpolicy) | [unset](#unset-tm-trafficpolicy) | [show](#show-tm-trafficpolicy) | [stat](#stat-tm-trafficpolicy)

##add tm trafficPolicy

Adds a traffic policy to use for setting connection timeout, single sign-on, and initiating logout. The policy sets the characteristics of application traffic at run time.


##Synopsys

add tm trafficPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the traffic policy. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the action to apply to requests or connections that match this policy.



##rm tm trafficPolicy

Removes an existing traffic policy.


##Synopsys

rm tm trafficPolicy &lt;name>


##Arguments

<b>name</b>
Name of the traffic policy to remove.



##set tm trafficPolicy

Modifies the specified parameters of an existing traffic policy.


##Synopsys

set tm trafficPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the traffic policy to modify.

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the action to apply to requests or connections that match this policy.



##unset tm trafficPolicy

Use this command to remove tm trafficPolicy settings.Refer to the set tm trafficPolicy command for meanings of the arguments.


##Synopsys

unset tm trafficPolicy &lt;name> [-rule] [-action]


##show tm trafficPolicy

Displays information about all configured traffic management (TM) traffic policies, or displays detailed information about the specified TM traffic policy.


##Synopsys

show tm trafficPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the traffic policy for which to display detailed information.



##Outputs

<b>rule</b>
The rule used by the vpn traffic policy. Rules are combinations of Expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide

<b>action</b>
The action to be performed when the rule is matched.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>hits</b>
Number of hits.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##stat tm trafficPolicy

Display Traffic Management traffic policy statistics.


##Synopsys

stat tm trafficPolicy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
The name of the TM traffic policy for which statistics will be displayed.  If not given statistics are shown for all policies.

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



##Example

stat tm trafficpolicy.

