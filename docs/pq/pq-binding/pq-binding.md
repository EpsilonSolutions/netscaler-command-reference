#pq binding

The following operations can be performed on "pq binding":


##show pq binding

Displays the information about the priority queuing policy bound to the virtual server. NOTE: This command is deprecated.Deprecated as cluster dont support reverse binding


##Synopsys




##Arguments

<b>vServerName</b>
Name of the load balancing virtual server for which to display the priority queuing policy.



##Outputs

<b>stateflag</b>

<b>policyName</b>
The name of the priority queuing policy.

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



