#ns spParams

The following operations can be performed on "ns spParams":


[set](#set-ns-spparams) | [unset](#unset-ns-spparams) | [show](#show-ns-spparams)

##set ns spParams

Sets surge protection attributes on the appliance.


##Synopsys

set ns spParams [-baseThreshold &lt;integer>] [-throttle &lt;throttle>]


##Arguments

<b>baseThreshold</b>
Maximum number of server connections that can be opened before surge protection is activated.
Default value: 200
Maximum value: 32767

<b>throttle</b>
Rate at which the system opens connections to the server.
Possible values: Aggressive, Normal, Relaxed
Default value: NORM_SP_TABLE



##Example

set ns spparams -baseThreshold 1000 -throttle aggressiveset ns spparams -throttle relaxed

##unset ns spParams

Use this command to remove ns spParams settings.Refer to the set ns spParams command for meanings of the arguments.


##Synopsys

unset ns spParams [-baseThreshold] [-throttle]


##show ns spParams

Displays the surge protection configuration on the appliance. Surge protection parameters are set by using the 'set ns spParams' command.


##Synopsys

show ns spParams


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>baseThreshold</b>
The base threshold. This is the maximum number of server connections that can be open before surge protection is activated.

<b>throttle</b>
Rate at which the system opens connections to the server.

<b>Table</b>
Table.



##Example

&gt; show ns spparams		Surge Protection parameters:		BaseThreshold:	200		Throttle:  Normal  Done

