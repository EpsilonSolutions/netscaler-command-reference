#pq policy

The following operations can be performed on "pq policy":


[add](#add-pq-policy) | [rm](#rm-pq-policy) | [set](#set-pq-policy) | [unset](#unset-pq-policy) | [show](#show-pq-policy) | [stat](#stat-pq-policy)

##add pq policy

Adds a priority queuing policy to the appliance.Note: To use the priority queuing policy on a virtual server, the virtual server must have priority queuing enabled and the priority queuing policy must be bound to the load balancing virtual server. To enable priority queuing on the virtual server and to bind the policy, use the set lb vserver and bind lb vserver commands. NOTE: This command is deprecated.Priority Queuing feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>policyName</b>
Name for the priority queuing policy. Must begin with a letter, number, or the underscore symbol (_). Other characters allowed, after the first character, are the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), and colon (:) characters.

<b>rule</b>
Expression or name of a named expression, against which the request is evaluated. The priority queuing policy is applied if the rule evaluates to true.
Note:
* On the command line interface, if the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you will not have to escape the double quotation marks.
* Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'

<b>priority</b>
Priority for queuing the request. If server resources are not available for a request that matches the configured rule, this option specifies a priority for queuing the request until the server resources are available again. Enter the value of positive_integer as 1, 2 or 3. The highest priority level is 1 and the lowest priority value is 3.
Minimum value: 1
Maximum value: 3

<b>weight</b>
Weight of the priority. Each priority is assigned a weight according to which it is served when server resources are available. The weight for a higher priority request must be set higher than that of a lower priority request.
To prevent delays for low-priority requests across multiple priority levels, you can configure weighted queuing for serving requests. The default weights for the priorities
are:
* Gold - Priority 1 - Weight 3
* Silver - Priority 2 - Weight 2
* Bronze - Priority 3 - Weight 1
Specify the weights as 0 through 101. A weight of 0 indicates that the particular priority level should be served only when there are no requests in any of the priority queues.
A weight of 101 specifies a weight of infinity. This means that this priority level is served irrespective of the number of clients waiting in other priority queues.
Minimum value: 0
Maximum value: 101

<b>qDepth</b>
Queue depth threshold value. When the queue size (number of requests in the queue) on the virtual server to which this policy is bound, increases to the specified qDepth value, subsequent requests are dropped to the lowest priority level.
Default value: 0
Minimum value: 0
Maximum value: 4294967294

<b>polqDepth</b>
Policy queue depth threshold value. When the policy queue size (number of requests in all the queues belonging to this policy) increases to the specified polqDepth value, subsequent requests are dropped to the lowest priority level.
Default value: 0
Minimum value: 0
Maximum value: 4294967294



##rm pq policy

Removes a priority queuing policy from the appliance. NOTE: This command is deprecated.Priority Queuing feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>policyName</b>
Name of the priority queuing policy to be removed.



##set pq policy

Modifies the attributes of a priority queuing policy. NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>policyName</b>
Name of the priority queuing policy to be modified.

<b>weight</b>
Weight of the priority. Each priority is assigned a weight according to which it is served when server resources are available. The weight for a higher priority request must be set higher than that of a lower priority request.
To prevent delays for low-priority requests across multiple priority levels, you can configure weighted queuing for serving requests. The default weights for the priorities
are:
* Gold - Priority 1 - Weight 3
* Silver - Priority 2 - Weight 2
* Bronze - Priority 3 - Weight 1
Specify the weights as 0 through 101. A weight of 0 indicates that the particular priority level should be served only when there are no requests in any of the priority queues.
A weight of 101 specifies a weight of infinity. This means that this priority level is served irrespective of the number of clients waiting in other priority queues.
Minimum value: 0
Maximum value: 101

<b>qDepth</b>
Queue depth threshold value. When the queue size (number of requests in the queue) on the virtual server to which this policy is bound, increases to the specified qDepth value, subsequent requests are dropped to the lowest priority level.
Default value: 0
Minimum value: 0
Maximum value: 4294967294

<b>polqDepth</b>
Policy queue depth threshold value. When the policy queue size (number of requests in all the queues belonging to this policy) increases to the specified polqDepth value, subsequent requests are dropped to the lowest priority level.
Default value: 0
Minimum value: 0
Maximum value: 4294967294



##unset pq policy

Use this command to remove pq policy settings.Refer to the set pq policy command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##show pq policy

Displays information about the priority queuing policy. NOTE: This command is deprecated.Priority Queuing feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>policyName</b>
Name of the priority queuing policy about which to display information. If a name is not provided, information about all priority queuing policies is shown.



##Outputs

<b>stateflag</b>

<b>rule</b>
The condition for applying the policy.

<b>priority</b>
The priority of queuing the request.

<b>weight</b>
Weight.

<b>qDepth</b>
Queue Depth.

<b>polqDepth</b>
Policy Queue Depth.

<b>hits</b>
Total number of hits.

<b>devno</b>

<b>count</b>



##stat pq policy

Displays statistics of the priority queuing policy. NOTE: This command is deprecated.Priority Queuing feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>policyName</b>
Name of the priority queuing policy whose statistics must be displayed. If a name is not provided, statistics of all priority queuing policies are shown.

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

<b>Toatal queue wait time (QWaitTim)</b>
Amount of time spent by priority queuing clients waiting in the priority queue.

<b>Avg queue wait time (AvWtTime)</b>
Average wait time for clients for this priority queuing policy.

<b>Avg clt transaction time (AvgTime)</b>
Average time taken by a priority queuing client to complete its transaction for this  priority queuing policy.

<b>Vserver IP (VsIP)</b>
IP address of the virtual server to which this priority queuing policy is bound.

<b>Vserver port (VsPort)</b>
Port number of the virtual server to which this priority queuing policy is bound.

<b>Current queue depth (Qdepth)</b>
Number of clients waiting currently for this priority queuing policy.

<b>Current server connections (ServCons)</b>
Current number of server connections established for serving clients for this priority queuing policy.

<b>Server TCP connections (TotServCon)</b>
Total number of server connections established for serving clients for this priority queuing policy.

<b>Client requests dropped (Dropped)</b>
Total number of dropped transactions for this priority queuing policy.

<b>Client HTTP transactions (CltTrns)</b>
Total number of client transactions for this priority queuing policy.

<b>Queue depth (TotQLen)</b>
Total number of waiting clients for this priority queuing policy.

<b>Avg clt transaction time (us) (AvgTime)</b>
Average time taken by a priority queuing client to complete its transaction for this priority queuing policy.



##Related Commands

<ul><li><a href="../../..//">stat pq</a></li></ul>



