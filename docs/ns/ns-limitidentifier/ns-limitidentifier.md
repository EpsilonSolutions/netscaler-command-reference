#ns limitIdentifier

The following operations can be performed on "ns limitIdentifier":


[add](#add-ns-limitidentifier) | [rm](#rm-ns-limitidentifier) | [set](#set-ns-limitidentifier) | [unset](#unset-ns-limitidentifier) | [show](#show-ns-limitidentifier) | [stat](#stat-ns-limitidentifier)

##add ns limitIdentifier

Adds a limit identifier to check if the amount of traffic exceeds a specified value, within a particular time interval.


##Synopsys

add ns limitIdentifier &lt;limitIdentifier> [-threshold &lt;positive_integer>] [-timeSlice &lt;positive_integer>] [-mode &lt;mode>  [-limitType ( BURSTY | SMOOTH )]] [-selectorName &lt;string>] [-maxBandwidth &lt;positive_integer>] [-trapsInTimeSlice &lt;positive_integer>]


##Arguments

<b>limitIdentifier</b>
Name for a rate limit identifier. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters. Reserved words must not be used.

<b>threshold</b>
Maximum number of requests that are allowed in the given timeslice when requests (mode is set as REQUEST_RATE) are tracked per timeslice.
When connections (mode is set as CONNECTION) are tracked, it is the total number of connections that would be let through.
Default value: 1
Minimum value: 1

<b>timeSlice</b>
Time interval, in milliseconds, specified in multiples of 10, during which requests are tracked to check if they cross the threshold. This argument is needed only when the mode is set to REQUEST_RATE.
Default value: 1000
Minimum value: 10

<b>mode</b>
Defines the type of traffic to be tracked.
* REQUEST_RATE - Tracks requests/timeslice.
* CONNECTION - Tracks active transactions.
Examples
1. To permit 20 requests in 10 ms and 2 traps in 10 ms:
add limitidentifier limit_req -mode request_rate -limitType smooth -timeslice 1000 -Threshold 2000 -trapsInTimeSlice 200
2. To permit 50 requests in 10 ms:
set  limitidentifier limit_req -mode request_rate -timeslice 1000 -Threshold 5000 -limitType smooth
3. To permit 1 request in 40 ms:
set limitidentifier limit_req -mode request_rate -timeslice 2000 -Threshold 50 -limitType smooth
4. To permit 1 request in 200 ms and 1 trap in 130 ms:
set limitidentifier limit_req -mode request_rate -timeslice 1000 -Threshold 5 -limitType smooth -trapsInTimeSlice 8
5. To permit 5000 requests in 1000 ms and 200 traps in 1000 ms:
set limitidentifier limit_req  -mode request_rate -timeslice 1000 -Threshold 5000 -limitType BURSTY
Possible values: CONNECTION, REQUEST_RATE, NONE
Default value: PEMGMT_RLT_MODE_REQ_RATE

<b>limitType</b>
Smooth or bursty request type.
* SMOOTH - When you want the permitted number of requests in a given interval of time to be spread evenly across the timeslice
* BURSTY - When you want the permitted number of requests to exhaust the quota anytime within the timeslice.
This argument is needed only when the mode is set to REQUEST_RATE.
Possible values: BURSTY, SMOOTH
Default value: PEMGMT_RLT_REQ_RATE_TYPE_BURSTY

<b>selectorName</b>
Name of the rate limit selector. If this argument is NULL, rate limiting will be applied on all traffic received by the virtual server or the NetScaler (depending on whether the limit identifier is bound to a virtual server or globally) without any filtering.

<b>maxBandwidth</b>
Maximum bandwidth permitted, in kbps.
Maximum value: 4294967287

<b>trapsInTimeSlice</b>
Number of traps to be sent in the timeslice configured. A value of 0 indicates that traps are disabled.
Maximum value: 65535



##Example

add ns limitIdentifier limit_id -threshold 2 -timeSlice 5000 -mode CONNECTION  -selectorName sel_1 -maxBandwidth 24 -trapsInTimeSlice 8

##rm ns limitIdentifier

Removes a rate limit identifier from the appliance.


##Synopsys

rm ns limitIdentifier &lt;limitIdentifier>


##Arguments

<b>limitIdentifier</b>
Name of the rate limit identifier to be removed.



##Example

rm ns limitIdentifier limit_id

##set ns limitIdentifier

Modifies the attributes of a rate limit identifier.


##Synopsys

set ns limitIdentifier &lt;limitIdentifier> [-threshold &lt;positive_integer>] [-timeSlice &lt;positive_integer>] [-mode &lt;mode>  [-limitType ( BURSTY | SMOOTH )]] [-selectorName &lt;string>] [-maxBandwidth &lt;positive_integer>] [-trapsInTimeSlice &lt;positive_integer>]


##Arguments

<b>limitIdentifier</b>
Name of the rate limit identifier to be modified.

<b>threshold</b>
Maximum number of requests that are allowed in the given timeslice when requests (mode is set as REQUEST_RATE) are tracked per timeslice.
When connections (mode is set as CONNECTION) are tracked, it is the total number of connections that would be let through.
Default value: 1
Minimum value: 1

<b>timeSlice</b>
Time interval, in milliseconds, specified in multiples of 10, during which requests are tracked to check if they cross the threshold. This argument is needed only when the mode is set to REQUEST_RATE.
Default value: 1000
Minimum value: 10

<b>mode</b>
Defines the type of traffic to be tracked.
* REQUEST_RATE - Tracks requests/timeslice.
* CONNECTION - Tracks active transactions.
Examples
1. To permit 20 requests in 10 ms and 2 traps in 10 ms:
add limitidentifier limit_req -mode request_rate -limitType smooth -timeslice 1000 -Threshold 2000 -trapsInTimeSlice 200
2. To permit 50 requests in 10 ms:
set  limitidentifier limit_req -mode request_rate -timeslice 1000 -Threshold 5000 -limitType smooth
3. To permit 1 request in 40 ms:
set limitidentifier limit_req -mode request_rate -timeslice 2000 -Threshold 50 -limitType smooth
4. To permit 1 request in 200 ms and 1 trap in 130 ms:
set limitidentifier limit_req -mode request_rate -timeslice 1000 -Threshold 5 -limitType smooth -trapsInTimeSlice 8
5. To permit 5000 requests in 1000 ms and 200 traps in 1000 ms:
set limitidentifier limit_req  -mode request_rate -timeslice 1000 -Threshold 5000 -limitType BURSTY
Possible values: CONNECTION, REQUEST_RATE, NONE
Default value: PEMGMT_RLT_MODE_REQ_RATE

<b>selectorName</b>
Name of the rate limit selector. If this argument is NULL, rate limiting will be applied on all traffic received by the virtual server or the NetScaler (depending on whether the limit identifier is bound to a virtual server or globally) without any filtering.

<b>maxBandwidth</b>
Maximum bandwidth permitted, in kbps.
Maximum value: 4294967287

<b>trapsInTimeSlice</b>
Number of traps to be sent in the timeslice configured. A value of 0 indicates that traps are disabled.
Maximum value: 65535



##Example

set ns limitIdentifier limit_id -threshold 2 -timeSlice 5000 -mode CONNECTION  -selectorName sel_1 -maxBandwidth 24 -trapsInTimeSlice 8

##unset ns limitIdentifier

Use this command to remove ns limitIdentifier settings.Refer to the set ns limitIdentifier command for meanings of the arguments.


##Synopsys

unset ns limitIdentifier &lt;limitIdentifier> [-selectorName] [-threshold] [-timeSlice] [-mode] [-limitType] [-maxBandwidth] [-trapsInTimeSlice]


##show ns limitIdentifier

Displays information about a rate limit identifier.


##Synopsys

show ns limitIdentifier [&lt;limitIdentifier>]


##Arguments

<b>limitIdentifier</b>
Name of the rate limit identifier about which to display information. If a name is not provided, information about all rate limit identifiers is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>ngname</b>
Nodegroup name to which this identifier belongs to.

<b>threshold</b>
Maximum number of requests that are allowed in the given timeslice when requests (mode is set as REQUEST_RATE) are tracked per timeslice.
When connections (mode is set as CONNECTION) are tracked, it is the total number of connections that would be let through.

<b>timeSlice</b>
Defines the time interval in msecs specified in multiples of 10 msec during which the requests are tracked to see if they cross the threshold. It is used and displayed only when the mode is REQUEST_RATE while tracking request rate and for defining the trap timeslice.

<b>mode</b>
Defines the type of traffic to be tracked.
* REQUEST_RATE - Tracks requests/timeslice.
* CONNECTION - Tracks active transactions.
Examples
1. To permit 20 requests in 10 ms and 2 traps in 10 ms:
add limitidentifier limit_req -mode request_rate -limitType smooth -timeslice 1000 -Threshold 2000 -trapsInTimeSlice 200
2. To permit 50 requests in 10 ms:
set  limitidentifier limit_req -mode request_rate -timeslice 1000 -Threshold 5000 -limitType smooth
3. To permit 1 request in 40 ms:
set limitidentifier limit_req -mode request_rate -timeslice 2000 -Threshold 50 -limitType smooth
4. To permit 1 request in 200 ms and 1 trap in 130 ms:
set limitidentifier limit_req -mode request_rate -timeslice 1000 -Threshold 5 -limitType smooth -trapsInTimeSlice 8
5. To permit 5000 requests in 1000 ms and 200 traps in 1000 ms:
set limitidentifier limit_req  -mode request_rate -timeslice 1000 -Threshold 5000 -limitType BURSTY

<b>limitType</b>
Smooth or bursty request type.
* SMOOTH - When you want the permitted number of requests in a given interval of time to be spread evenly across the timeslice
* BURSTY - When you want the permitted number of requests to exhaust the quota anytime within the timeslice.
This argument is needed only when the mode is set to REQUEST_RATE.

<b>selectorName</b>
Name of the rate limit selector. If this argument is NULL, rate limiting will be applied on all traffic received by the virtual server or the NetScaler (depending on whether the limit identifier is bound to a virtual server or globally) without any filtering.

<b>stateflag</b>
This is used internally to identify ip addresses returned.

<b>hits</b>
The number of times this identifier was evaluated.

<b>drop</b>
The number of times action was taken.

<b>rule</b>
Rule.

<b>time</b>
Time interval considered for rate limiting

<b>total</b>
Maximum number of requests permitted in the computed timeslice

<b>maxBandwidth</b>
The maximum bandwidth in kbps permitted

<b>trapsInTimeSlice</b>
The maximum bandwidth permitted in kbps

<b>trapsComputedInTimeSlice</b>
The number of traps that would be sent in the timeslice configured.

<b>computedTrapTimeSlice</b>
The time interval computed for sending traps.

<b>referenceCount</b>
Total number of transactions pointing to this entry.

<b>devno</b>

<b>count</b>



##Example

show ns limitIdentifier limit_id

##stat ns limitIdentifier

Display statistics of a identifier.


##Synopsys

stat ns limitIdentifier [&lt;name>  [&lt;pattern> ...]] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )] [-sortBy Hits  [&lt;sortOrder>]]


##Arguments

<b>name</b>
The name of the identifier.

<b>pattern</b>
Pattern for the selector field, ? means field is required, * means field value does not matter, anything else is a regular pattern

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full

<b>sortBy</b>
use this argument to sort by specific key
Possible values: Hits



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Rate Limit Identifier Hits (Hits)</b>
Total hits.

<b>Rate Limit Identifier Drops (Drops)</b>
Total drops

<b>Rate Limit Session Hits (Hits)</b>
Total hits.



##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



