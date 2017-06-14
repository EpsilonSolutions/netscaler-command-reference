#ns timer

The following operations can be performed on "ns timer":


[add](#add-ns-timer) | [rm](#rm-ns-timer) | [set](#set-ns-timer) | [unset](#unset-ns-timer) | [bind](#bind-ns-timer) | [unbind](#unbind-ns-timer) | [show](#show-ns-timer) | [rename](#rename-ns-timer)

##add ns timer

Create a Timer.


##Synopsys

add ns timer &lt;name> (-interval &lt;integer>  [&lt;unit>]) [-comment &lt;string>]


##Arguments

<b>name</b>
Timer name.

<b>interval</b>
The frequency at which the policies bound to this timer are invoked. The minimum value is 20 msec. The maximum value is 20940 in seconds and 349 in minutes
Default value: 5
Minimum value: 1
Maximum value: 20940000

<b>comment</b>
Comments associated with this timer.



##Example

add timer policy timer -comment "Timer that would be invoked at interval 10 sec apart."

##rm ns timer

Remove a Timer.


##Synopsys

rm ns timer &lt;name>


##Arguments

<b>name</b>
Timer name.



##Example

rm ns timer timer

##set ns timer

Set a argument values for existing timer.


##Synopsys

set ns timer &lt;name> [-interval &lt;integer>] [&lt;unit>] [-comment &lt;string>]


##Arguments

<b>name</b>
Timer name.

<b>interval</b>
The frequency at which the policies bound to this timer are invoked. The minimum value is 20 msec. The maximum value is 20940 in seconds and 349 in minutes
Default value: 5
Minimum value: 1
Maximum value: 20940000

<b>unit</b>
Timer interval unit
Possible values: SEC, MIN
Default value: NSTMUNT_SEC

<b>comment</b>
Comments associated with this timer.



##Example

set ns timer timer -comment "Timer that would be invoked at interval 20 sec apart."

##unset ns timer

Unset comment for existing timer..Refer to the set ns timer command for meanings of the arguments.


##Synopsys

unset ns timer &lt;name> [-interval &lt;integer>] [&lt;unit>] [-comment &lt;string>]


##Example

unset ns timer timer -comment

##bind ns timer

Defines the binding relation among timer, and timer policy.


##Synopsys

bind ns timer &lt;name> -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-vServer &lt;string>] [-sampleSize &lt;positive_integer>] [-threshold &lt;positive_integer>]


##Arguments

<b>name</b>
Timer name.

<b>policyName</b>
The timer policy associated with the timer.



##Example

	i)	bind ns timer timer_trigger -policyName timer_pol -priority 1	ii)	bind ns timer timer_trigger -policyName timer_pol -priority 1

##unbind ns timer

Unbind entities from timer


##Synopsys

unbind ns timer &lt;name> -policyName &lt;string>


##Arguments

<b>name</b>
Timer name.

<b>policyName</b>
The timer policy associated with the timer.



##Example

unbind ns timer timer -policyName timer_pol

##show ns timer

Display the Timer entities.


##Synopsys

show ns timer [&lt;name>]


##Arguments

<b>name</b>
Timer name.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>interval</b>
The frequency at which the policies bound to this timer are invoked. The minimum value is 20 msec. The maximum value is 20940 in seconds and 349 in minutes

<b>unit</b>
Timer interval unit

<b>comment</b>
Comments associated with this timer.

<b>policyName</b>
The timer policy associated with the timer.

<b>priority</b>
Specifies the priority of the timer policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>vServer</b>
Name of the vserver which provides the context for the rule in timer policy. When not specified it is treated as a Global Default context.

<b>sampleSize</b>
Denotes the sample size. Sample size value of 'x' means that previous '(x - 1)' policy's rule evaluation results and the current evaluation result are present with the binding. For example, sample size of 10 means that there is a state of previous 9 policy evaluation results and also the current policy evaluation result.

<b>threshold</b>
Denotes the threshold. If the rule of the policy in the binding relation evaluates 'threshold size' number of times in 'sample size' to true, then the corresponding action is taken. Its value needs to be less than or equal to the sample size value.

<b>stateflag</b>

<b>bindPolicyType</b>

<b>devno</b>

<b>count</b>



##rename ns timer

Rename a timer.


##Synopsys

rename ns timer &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
The name of the timer.

<b>newName</b>
The new name of the timer.



##Example

rename ns timer oldname newname

