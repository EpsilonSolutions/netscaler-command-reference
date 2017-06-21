#appqoe policy

The following operations can be performed on "appqoe policy":


[add](#add-appqoe-policy) | [rm](#rm-appqoe-policy) | [set](#set-appqoe-policy) | [show](#show-appqoe-policy) | [stat](#stat-appqoe-policy)

##add appqoe policy

Add a new AppQoE policy for binding rule with action


##Synopsys

add appqoe policy &lt;name> -rule &lt;expression> -action &lt;string>


##Arguments

<b>name</b>

<b>rule</b>
Expression or name of a named expression, against which the request is evaluated. The policy is applied if the rule evaluates to true.

<b>action</b>
Configured AppQoE action to trigger



##rm appqoe policy

Remove an AppQoE policy.


##Synopsys

rm appqoe policy &lt;name>


##Arguments

<b>name</b>
Name of the AppQoE policy to be removed.



##set appqoe policy




##Synopsys

set appqoe policy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>

<b>rule</b>
Expression or name of a named expression, against which the request is evaluated. The policy is applied if the rule evaluates to true.

<b>action</b>
Configured AppQoE action to trigger



##show appqoe policy

Display all the configured AppQoE policies.


##Synopsys

show appqoe policy [&lt;name>]


##Arguments

<b>name</b>



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression or name of a named expression, against which the request is evaluated. The policy is applied if the rule evaluates to true.

<b>action</b>
Configured AppQoE action to trigger

<b>hits</b>
Number of hits.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>bindPriority</b>
Specifies the binding  of the policy. use only in display

<b>boundTo</b>
The name of the entity to which the policy is bound.

<b>activePolicy</b>

<b>devno</b>

<b>count</b>



##stat appqoe policy

Displays collected brief statistics for all AppQoE policies, or detailed statistics for only the specified policy.


##Synopsys

stat appqoe policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
policyName

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

<b>Server TTFB (SvrTTFB)</b>
Server Time-To-First-Byte in milliseconds calculated for this AppQoE policy.

<b>Server TTLB (SvrTTLB)</b>
Server Time-To-Last-Byte in milliseconds calculated for this AppQoE policy.

<b>Client TTLB (CltTTLB)</b>
Client Time-To-Last-Byte in milliseconds calculated for this AppQoE policy.

<b>Average Server TTFB (SvrTTFB)</b>
Average Server Time-To-First-Byte in milliseconds calculated for this AppQoE policy.

<b>Average Server TTLB (SvrTTLB)</b>
Average Server Time-To-Last-Byte in milliseconds calculated for this AppQoE policy.

<b>Average Client TTLB (CltTTLB)</b>
Average Client Time-To-Last-Byte in milliseconds calculated for this AppQoE policy.

<b>ThroughPut(Kbps) (ThroughPut)</b>
Throughput in Kbps calculated on this AppQoE policy

<b>Server TCP connections (TotSvr)</b>
Total number of server connections that were established through this AppQoE Policy

<b>Client TCP connections (TotClt)</b>
Total number of client connections that were requested through this AppQoE Policy

<b>Requests received (TotReq)</b>
Total number of requests that were requested through this AppQoE policy

<b>Requests bytes (TotReqBytes)</b>
Total number of requests bytes that were requested through this AppQoE policy

<b>Responses received (TotRsp)</b>
Total number of responses received by this AppQoE policy

<b>Response bytes (TotRspBytes)</b>
Total number of response bytes received by this AppQoE policy

<b>Alternate responses sent (TotJSsent)</b>
Total number of in-memory responses sent instead of expected responses through this AppQoE policy

<b>Alternate responses bytes sent (TotJSBytessent)</b>
Total bytes of in-memory responses sent through this AppQoE policy

<b>Policy hits (Hits)</b>
Number of hits on the policy

<b>Client HTTP transactions</b>
Total number of client transactions processed by this AppQoE policy.

<b>Svr HTTP transactions</b>
Total number of server transactions processed by this AppQoE policy.



##Example

stat appqos policy

##Related Commands

<ul><li><a href="../../../a/a">stat appqoe</a></li></ul>



