#ns rateControl

The following operations can be performed on "ns rateControl":


[set](#set-ns-ratecontrol) | [unset](#unset-ns-ratecontrol) | [show](#show-ns-ratecontrol)

##set ns rateControl

Sets the UDP/TCP/ICMP packet rate controls for any application that is not configured at System (direct access to the backend through System).


##Synopsys

set ns rateControl [-tcpThreshold &lt;positive_integer>] [-udpThreshold &lt;positive_integer>] [-icmpThreshold &lt;positive_integer>] [-tcprstThreshold &lt;positive_integer>]


##Arguments

<b>tcpThreshold</b>
Number of SYNs permitted per 10 milliseconds.
Minimum value: 0

<b>udpThreshold</b>
Number of UDP packets permitted per 10 milliseconds.
Minimum value: 0

<b>icmpThreshold</b>
Number of ICMP packets permitted per 10 milliseconds.
Default value: 100
Minimum value: 0

<b>tcprstThreshold</b>
The number of TCP RST packets permitted per 10 milli second. zero means rate control is disabled and 0xffffffff means every thing is rate controlled
Default value: 100
Minimum value: 0



##Example

	The following command will set the SYN rate to 100, icmp rate to 10 and the udp rate to unlimited.	set ns ratecontrol -tcpThreshold 100 -udpThreshold 0 -icmpThreshold 10	The 'show ns rate control' command can be used to view the current settings of the rate controls.&gt; show ns ratecontrol		UDP threshold:			0 per 10 ms		TCP threshold:			0 per 10 ms		ICMP threshold: 		100 per 10 ms Done

##unset ns rateControl

Use this command to remove ns rateControl settings.Refer to the set ns rateControl command for meanings of the arguments.


##Synopsys

unset ns rateControl [-tcpThreshold] [-udpThreshold] [-icmpThreshold] [-tcprstThreshold]


##show ns rateControl

Displays the values configured for rate control on the appliance.


##Synopsys

show ns rateControl


##Outputs

<b>tcpThreshold</b>
Number of SYNs permitted per 10 milliseconds.

<b>udpThreshold</b>
Number of UDP packets permitted per 10 milliseconds.

<b>icmpThreshold</b>
Number of ICMP packets permitted per 10 milliseconds.

<b>tcprstThreshold</b>
The number of TCP RST packets permitted per 10 milli second. zero means rate control is disabled and 0xffffffff means every thing is rate controlled



##Example

By default, there is no rate control for TCP/UDP and for ICMP it will be 100.  The output of the "show ns ratecontrol" command, with default setting,&gt; show ns ratecontrol		UDP threshold:			0 per 10 ms		TCP threshold:			0 per 10 ms		ICMP threshold: 		100 per 10 ms Done

