#ica latencyprofile

The following operations can be performed on "ica latencyprofile":


[add](#add-ica-latencyprofile) | [rm](#rm-ica-latencyprofile) | [set](#set-ica-latencyprofile) | [unset](#unset-ica-latencyprofile) | [show](#show-ica-latencyprofile)

##add ica latencyprofile

This command creates an ica latencyprofile with the options specified.


##Synopsys

add ica latencyprofile &lt;name> [-l7LatencyMonitoring ( ENABLED | DISABLED )] [-l7LatencyThresholdFactor &lt;positive_integer>] [-l7LatencyWaitTime &lt;positive_integer>] [-l7LatencyNotifyInterval &lt;positive_integer>] [-l7LatencyMaxNotifyCount &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the ICA latencyprofile. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and
the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the ICA latency profile is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my ica l7latencyprofile" or 'my ica l7latencyprofile').

<b>l7LatencyMonitoring</b>
Enable/Disable L7 Latency monitoring for L7 latency notifications
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>l7LatencyThresholdFactor</b>
L7 Latency threshold factor. This is the factor by which the active latency should be greater than the minimum observed value to determine that the latency is high and may need to be reported
Default value: 4
Minimum value: 2
Maximum value: 65535

<b>l7LatencyWaitTime</b>
L7 Latency Wait time. This is the time for which the Netscaler waits after the threshold is exceeded before it sends out a Notification to the Insight Center.
Default value: 20
Minimum value: 1
Maximum value: 65535

<b>l7LatencyNotifyInterval</b>
L7 Latency Notify Interval. This is the interval at which the Netscaler sends out notifications to the Insight Center after the wait time has passed.
Default value: 20
Minimum value: 1
Maximum value: 65535

<b>l7LatencyMaxNotifyCount</b>
L7 Latency Max notify Count. This is the upper limit on the number of notifications sent to the Insight Center within an interval where the Latency is above the threshold.
Default value: 5
Minimum value: 1
Maximum value: 65535



##Example

add ica latencyprofile profile1 -l7latencythresholdfactor 4

##rm ica latencyprofile

This command removes the specified ica l7latencyprofile.


##Synopsys

rm ica latencyprofile &lt;name>


##Arguments

<b>name</b>
Name of the ICA l7latencyprofile.



##Example

rm ica l7latencyprofile profile1

##set ica latencyprofile

This command modifies the specified parameters of the specified ica l7latencyprofile.


##Synopsys

set ica latencyprofile &lt;name> [-l7LatencyMonitoring ( ENABLED | DISABLED )] [-l7LatencyThresholdFactor &lt;positive_integer>] [-l7LatencyWaitTime &lt;positive_integer>] [-l7LatencyNotifyInterval &lt;positive_integer>] [-l7LatencyMaxNotifyCount &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the profile that you want to modify.

<b>l7LatencyMonitoring</b>
Enable/Disable L7 Latency monitoring for L7 latency notifications
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>l7LatencyThresholdFactor</b>
L7 Latency threshold factor. This is the factor by which the active latency should be greater than the minimum observed value to determine that the latency is high and may need to be reported
Default value: 4
Minimum value: 2
Maximum value: 65535

<b>l7LatencyWaitTime</b>
L7 Latency Wait time. This is the time for which the Netscaler waits after the threshold is exceeded before it sends out a Notification to the Insight Center.
Default value: 20
Minimum value: 1
Maximum value: 65535

<b>l7LatencyNotifyInterval</b>
L7 Latency Notify Interval. This is the interval at which the Netscaler sends out notifications to the Insight Center after the wait time has passed.
Default value: 20
Minimum value: 1
Maximum value: 65535

<b>l7LatencyMaxNotifyCount</b>
L7 Latency Max notify Count. This is the upper limit on the number of notifications sent to the Insight Center within an interval where the Latency is above the threshold.
Default value: 5
Minimum value: 1
Maximum value: 65535



##Example

set ica l7latencyprofile profile1 -latencyThresholdfactor 20

##unset ica latencyprofile

Use this command to remove ica latencyprofile settings.Refer to the set ica latencyprofile command for meanings of the arguments.


##Synopsys

unset ica latencyprofile &lt;name> [-l7LatencyMonitoring] [-l7LatencyThresholdFactor] [-l7LatencyWaitTime] [-l7LatencyNotifyInterval] [-l7LatencyMaxNotifyCount]


##show ica latencyprofile

Displays details of the specified ica l7latencyprofile. If no l7latencyprofile is specified, displays a list of ica l7latencyprofiles on the NetScaler appliance.


##Synopsys

show ica latencyprofile [&lt;name>]


##Arguments

<b>name</b>
Name of the ica l7latencyprofile.



##Outputs

<b>stateflag</b>

<b>l7LatencyMonitoring</b>
Enable/Disable L7 Latency monitoring for L7 latency notifications

<b>l7LatencyThresholdFactor</b>
L7 Latency threshold factor. This is the factor by which the active latency should be greater than the minimum observed value to determine that the latency is high and may need to be reported

<b>l7LatencyWaitTime</b>
L7 Latency Wait time. This is the time for which the Netscaler waits after the threshold is exceeded before it sends out a Notification to the Insight Center.

<b>l7LatencyNotifyInterval</b>
L7 Latency Notify Interval. This is the interval at which the Netscaler sends out notifications to the Insight Center after the wait time has passed.

<b>l7LatencyMaxNotifyCount</b>
L7 Latency Max notify Count. This is the upper limit on the number of notifications sent to the Insight Center within an interval where the Latency is above the threshold.

<b>refCnt</b>
Number of entities using this l7latencyprofile

<b>builtin</b>
Indicates that the ICA latencyprofile is a built-in (SYSTEM INTERNAL) type.

<b>isDefault</b>
A value of true is returned if it is a default l7latencyprofile

<b>devno</b>

<b>count</b>



##Example

sh ica l7latencyprofile profile1

