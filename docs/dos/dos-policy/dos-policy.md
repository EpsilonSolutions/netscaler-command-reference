#dos policy

The following operations can be performed on "dos policy":


[add](#add-dos-policy) | [rm](#rm-dos-policy) | [set](#set-dos-policy) | [unset](#unset-dos-policy) | [show](#show-dos-policy) | [stat](#stat-dos-policy)

##add dos policy

Adds a DoS protection policy to the appliance.Note: To apply DoS protection to a service, bind the DoS policy to the service by using the bind service command.


##Synopsys

add dos policy &lt;name> -qDepth &lt;positive_integer> [-cltDetectRate &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the HTTP DoS protection policy. Must begin with a letter, number, or the underscore character (_). Other characters allowed, after the first character, are the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), and colon (:) characters.

<b>qDepth</b>
Queue depth. The queue size (the number of outstanding service requests on the system) before DoS protection is activated on the service to which the DoS protection policy is bound.
Minimum value: 21

<b>cltDetectRate</b>
Client detect rate. Integer representing the percentage of traffic to which the HTTP DoS policy is to be applied after the queue depth condition is satisfied.
Minimum value: 0
Maximum value: 100



##Example

add dos policy dospol -qdepth 100 -cltDetectRate 90

##rm dos policy

Removes a DoS protection policy from the appliance.


##Synopsys

rm dos policy &lt;name>


##Arguments

<b>name</b>
Name of the DoS protection policy to be removed.



##Example

rm dos policy dospol

##set dos policy

Modifies the attributes of a DoS protection policy.


##Synopsys

set dos policy &lt;name> [-qDepth &lt;positive_integer>] [-cltDetectRate &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the DoS protection policy to be modified.

<b>qDepth</b>
Queue depth. The queue size (the number of outstanding service requests on the system) before DoS protection is activated on the service to which the DoS protection policy is bound.
Minimum value: 21

<b>cltDetectRate</b>
Client detect rate. Integer representing the percentage of traffic to which the HTTP DoS policy is to be applied after the queue depth condition is satisfied.
Minimum value: 1
Maximum value: 100



##Example

set dos policy dospol -qdepth 1000

##unset dos policy

Use this command to remove dos policy settings.Refer to the set dos policy command for meanings of the arguments.


##Synopsys

unset dos policy &lt;name> -cltDetectRate


##show dos policy

Displays information about a DoS protection policy.


##Synopsys

show dos policy [&lt;name>]


##Arguments

<b>name</b>
Name of the DoS protection policy about which to display information. If a name is not provided, information about all DoS protection policies is shown.



##Outputs

<b>qDepth</b>
Queue depth. The queue size (the number of outstanding service requests on the system) before DoS protection is activated on the service to which the DoS protection policy is bound.

<b>cltDetectRate</b>
Client detect rate. Integer representing the percentage of traffic to which the HTTP DoS policy is to be applied after the queue depth condition is satisfied.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

&gt; show dos policy        1 configured DoS policy:1)      Policy: dospol  QDepth: 100     ClientDetectRate: 90 Done

##stat dos policy

Displays statistics of the DoS protection policy.


##Synopsys

stat dos policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
The name of the DoS protection policy whose statistics must be displayed. If a name is not provided, statistics of all the DoS protection policies are displayed.

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

<b>Client detect rate (ClDtRate)</b>
Current ratio of JavaScript send rate to the server response rate (Client detect rate)

<b>Physical service IP (SvcIP)</b>
IP address of the service to which this policy is bound.

<b>Physical service port (SvcPort)</b>
Port address of the service to which this policy is bound.

<b>Current server queue size (CurQSize)</b>
Current queue size of the server to which this policy is bound.

<b>DOS transactions (DosTrans)</b>
Total number of DoS JavaScript transactions performed for this policy.

<b>Client detect rate mismatch (JsRefusd)</b>
Number of times the DoS JavaScript was not sent because the set JavaScript rate was not met for this policy.

<b>Valid clients (TotValCl)</b>
Total number of valid DoS cookies received for this policy.

<b>DOS JavaScript bytes served (JsBytSnt)</b>
Total number of DoS JavaScript bytes sent for this policy.

<b>Non GET, POST requests</b>
Number of non-GET and non-POST requests for which DOS JavaScript was sent.

<b>DOS JavaScript send rate (JSRate)</b>
Current rate at which JavaScript is being sent in response to client requests.

<b>Server response rate (RespRate)</b>
Current rate at which the server to which this policy is bound is responding.



##Related Commands

<ul><li><a href="../../..//">stat dos</a></li></ul>



