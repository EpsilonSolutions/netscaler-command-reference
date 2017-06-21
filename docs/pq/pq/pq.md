#pq

The following operations can be performed on "pq":


##stat pq

Displays statistics of priority queuing.


##Synopsys

stat pq [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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

<b>Policy hits (PolMatch)</b>
Number of times the Netscaler appliance matched an incoming request using any priority queuing policy.

<b>Threshold failed (ThrsFail)</b>
Number of times the Netscaler appliance failed to match an incoming request to any of priority queing policy.

<b>Priority 1 requests (Pri1Req)</b>
Number of priority 1 requests that the Netscaler appliance received.

<b>Priority 2 requests (Pri2Req)</b>
Number of priority 2 requests that the Netscaler appliance received.

<b>Priority 3 requests (Pri3Req)</b>
Number of priority 3 requests that the Netscaler appliance received.



##Related Commands

<ul><li><a href="../../../q-p/q-p">stat pq policy</a></li></ul>



