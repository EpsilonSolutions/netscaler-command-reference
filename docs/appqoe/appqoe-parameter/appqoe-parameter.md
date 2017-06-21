#appqoe parameter

The following operations can be performed on "appqoe parameter":


[set](#set-appqoe-parameter) | [unset](#unset-appqoe-parameter) | [show](#show-appqoe-parameter)

##set appqoe parameter

Sets the parameters for displaying appqoe information.


##Synopsys

set appqoe parameter [-sessionLife &lt;secs>] [-avgwaitingclient &lt;positive_integer>] [-MaxAltRespBandWidth &lt;positive_integer>] [-dosAttackThresh &lt;positive_integer>]


##Arguments

<b>sessionLife</b>
Time, in seconds, between the first time and the next time the AppQoE alternative content window is displayed. The alternative content window is displayed only once during a session for the same browser accessing a configured URL, so this parameter determines the length of a session.
Default value: 300
Minimum value: 1
Maximum value: 4294967294

<b>avgwaitingclient</b>
average number of client connections, that can sit in service waiting queue
Default value: 1000000
Minimum value: 0
Maximum value: 4294967294

<b>MaxAltRespBandWidth</b>
maximum bandwidth which will determine whether to send alternate content response
Default value: 100
Minimum value: 1
Maximum value: 4294967294

<b>dosAttackThresh</b>
average number of client connection that can queue up on vserver level without triggering DoS mitigation module
Default value: 2000
Minimum value: 0
Maximum value: 4294967294



##Example

set appqoe parameter -sessionlife 200 -avgwaitingclient 10

##unset appqoe parameter

Use this command to remove appqoe parameter settings.Refer to the set appqoe parameter command for meanings of the arguments.


##Synopsys

unset appqoe parameter [-sessionLife] [-avgwaitingclient] [-MaxAltRespBandWidth] [-dosAttackThresh]


##show appqoe parameter

Displays the values of the session life and filename parameters


##Synopsys

show appqoe parameter


##Outputs

<b>sessionLife</b>
appqoe session life (in seconds)

<b>avgwaitingclient</b>
average number of client connections, that can sit in service waiting queue

<b>MaxAltRespBandWidth</b>
maximum bandwidth which will determine whether to send alternate content response

<b>dosAttackThresh</b>
average number of client connection that can queue up on vserver level without triggering DoS mitigation module



##Example

show appqos parameter

