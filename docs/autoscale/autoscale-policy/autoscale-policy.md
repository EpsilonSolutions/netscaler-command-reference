#autoscale policy

The following operations can be performed on "autoscale policy":


[add](#add-autoscale-policy) | [rm](#rm-autoscale-policy) | [set](#set-autoscale-policy) | [unset](#unset-autoscale-policy) | [show](#show-autoscale-policy) | [stat](#stat-autoscale-policy) | [rename](#rename-autoscale-policy)

##add autoscale policy

Create a autoscale policy.


##Synopsys

add autoscale policy &lt;name> -rule &lt;expression> -action &lt;string> [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
The name of the autoscale policy.

<b>rule</b>
The rule associated with the policy.

<b>action</b>
The autoscale profile associated with the policy.

<b>comment</b>
Comments associated with this autoscale policy.

<b>logAction</b>
The log action associated with the autoscale policy



##rm autoscale policy

Remove a autoscale policy.


##Synopsys

rm autoscale policy &lt;name>


##Arguments

<b>name</b>
The name of the autoscale policy.



##Example

rm autoscale policy pol

##set autoscale policy

Set a new rule/action/comment for an existing autoscale policy.


##Synopsys

set autoscale policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
The name of the autoscale policy.

<b>rule</b>
The rule associated with the policy.

<b>action</b>
The autoscale profile associated with the policy.

<b>comment</b>
Comments associated with this autoscale policy.

<b>logAction</b>
The log action associated with the autoscale policy



##Example

set autoscaler policy pol -rule true

##unset autoscale policy

Unset comment/logaction for existing autoscale policy..Refer to the set autoscale policy command for meanings of the arguments.


##Synopsys

unset autoscale policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Example

unset autoscale policy pol9 -undefAction

##show autoscale policy

Display the autoscale policies.


##Synopsys

show autoscale policy [&lt;name>]


##Arguments

<b>name</b>
The name of the autoscale policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
The rule associated with the policy.

<b>action</b>
The autoscale profile associated with the policy.

<b>comment</b>
Comments associated with this autoscale policy.

<b>logAction</b>
The log action associated with the autoscale policy

<b>stateflag</b>

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of Undef hits.

<b>priority</b>
Specifies the priority of the policy.

<b>boundTo</b>
Location where policy is bound

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>devno</b>

<b>count</b>



##stat autoscale policy

Display autoscale policy statistics.


##Synopsys

stat autoscale policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
The name of the autoscale policy for which statistics will be displayed.  If not given statistics are shown for all autoscale policies.

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

stat autoscale policy

##rename autoscale policy

Rename a autoscale policy.


##Synopsys

rename autoscale policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
The name of the autoscale policy.

<b>newName</b>
The new name of the autoscale policy.



##Example

rename autoscale policy oldname newname

