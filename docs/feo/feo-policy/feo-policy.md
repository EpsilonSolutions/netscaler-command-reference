#feo policy

The following operations can be performed on "feo policy":


[add](#add-feo-policy) | [rm](#rm-feo-policy) | [set](#set-feo-policy) | [unset](#unset-feo-policy) | [show](#show-feo-policy)

##add feo policy

Create a front end optimization policy.


##Synopsys

add feo policy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
The name of the front end optimization policy.

<b>rule</b>
The rule associated with the front end optimization policy.

<b>action</b>
The front end optimization action that has to be performed when the rule matches.



##rm feo policy

Remove a front end optimization policy.


##Synopsys

rm feo policy &lt;name>


##Arguments

<b>name</b>
The front end optimization policy to be removed.



##set feo policy

Modify a front end optimization policy.


##Synopsys

set feo policy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
The front end optimization policy to be modified.

<b>rule</b>
The new rule to be associated with the front end optimization policy.

<b>action</b>
The optimization to be associated with the front end optimization policy.



##unset feo policy

Use this command to remove feo policy settings.Refer to the set feo policy command for meanings of the arguments.


##Synopsys

unset feo policy &lt;name> [-rule] [-action]


##show feo policy

Display the configured front end optimization policies.


##Synopsys

show feo policy [&lt;name>]


##Arguments

<b>name</b>
The name of the front end optimization policy.

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>rule</b>
The rule associated with the front end optimization policy.

<b>action</b>
The front end optimization action that has to be performed when the rule matches.

<b>builtin</b>
Flag to determine if the front end optimization policy is built-in or not

<b>hits</b>
Total number of hits.

<b>undefHits</b>
Total number of undefined policy hits.

<b>activePolicy</b>
Indicates whether a policy is bound or not.

<b>boundTo</b>
Location where the policy is bound to.

<b>priority</b>
Priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>devno</b>

<b>count</b>



