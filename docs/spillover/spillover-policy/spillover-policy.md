#spillover policy

The following operations can be performed on "spillover policy":


[add](#add-spillover-policy) | [rm](#rm-spillover-policy) | [set](#set-spillover-policy) | [unset](#unset-spillover-policy) | [show](#show-spillover-policy) | [rename](#rename-spillover-policy) | [stat](#stat-spillover-policy)

##add spillover policy

Add a spillover policy. SPILLOVER policies that can be added are based on vserver expressions.


##Synopsys

add spillover policy &lt;name> -rule &lt;expression> -action &lt;string> [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the spillover policy.

<b>rule</b>
Expression to be used by the spillover policy.

<b>action</b>
Action for the spillover policy. Action is created using add spillover action command

<b>comment</b>
Any comments that you might want to associate with the spillover policy.



##Example

add spillover policy pol1 -rule "SYS.VSERVER("abc").ACTIVESERVICES.LE(2) -action act1add spillover policy pol2 -rule "SYS.VSERVER("abc").CONNECTIONS.GT(500) -action act2"

##rm spillover policy

Removes a spillover policy.


##Synopsys

rm spillover policy &lt;name>


##Arguments

<b>name</b>
Name of the spillover policy.



##set spillover policy

Used to change the expression or other parameters of an existingpolicy.


##Synopsys

set spillover policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the spillover policy.

<b>rule</b>
Expression to be used by the spillover policy.

<b>action</b>
Action for the spillover policy. Action is created using add spillover action command

<b>comment</b>
Any comments that you might want to associate with the spillover policy.



##Example

set spillover policy pol1 -rule "SYS.VSERVER("abc").ACTIVESERVICS.LE(1)"set spillover policy pol2 -action act4"

##unset spillover policy

Use this command to remove spillover policy settings.Refer to the set spillover policy command for meanings of the arguments.


##Synopsys

unset spillover policy &lt;name> -comment


##show spillover policy

Displaying the policy-related information.


##Synopsys

show spillover policy [&lt;name>]


##Arguments

<b>name</b>
Name of the spillover policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression to be used by the spillover policy.

<b>action</b>
Action for the spillover policy. Action is created using add spillover action command

<b>boundTo</b>
The name of the entity to which the policy is bound.

<b>hits</b>
The number of times the policy has been hit.

<b>undefHits</b>
Number of policy UNDEF hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>comment</b>
Any comments that you might want to associate with the spillover policy.

<b>builtin</b>
Flag to determine if compression policy is builtin or not

<b>gslbBindings</b>
Number of times the policy bound to a gslb vserver

<b>devno</b>

<b>count</b>



##rename spillover policy

Renames a spillover policy.


##Synopsys

rename spillover policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the policy.

<b>newName</b>
New name for the spillover policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
Choose a name that reflects the function that the policy performs. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').



##Example

rename spillover policy oldname newname

##stat spillover policy

Displays statistics for all spillover policies currently configured on the NetScaler appliance, or detailed statistics for the specified policy.


##Synopsys

stat spillover policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the spillover policy for which to show detailed statistics.

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



