#stream identifier

The following operations can be performed on "stream identifier":


[add](#add-stream-identifier) | [set](#set-stream-identifier) | [unset](#unset-stream-identifier) | [rm](#rm-stream-identifier) | [show](#show-stream-identifier) | [stat](#stat-stream-identifier)

##add stream identifier

Creates a stream identifier. A stream identifier specifies how data is collected and stored for an Action Analytics configuration.


##Synopsys

add stream identifier &lt;name> &lt;selectorName> [-interval &lt;positive_integer>] [-SampleCount &lt;positive_integer>] [-sort &lt;sort>] [-snmptrap ( ENABLED | DISABLED )] [-appflowLog ( ENABLED | DISABLED )] [-trackTransactions ( RESPTIME | NONE )  [-maxTransactionThreshold &lt;positive_integer>]  [-minTransactionThreshold &lt;positive_integer>]  [-acceptanceThreshold &lt;string>]  [-breachThreshold &lt;positive_integer>]]


##Arguments

<b>name</b>
The name of stream identifier.

<b>selectorName</b>
Name of the selector to use with the stream identifier.

<b>interval</b>
Number of minutes of data to use when calculating session statistics (number of requests, bandwidth, and response times). The interval is a moving window that keeps the most recently collected data. Older data is discarded at regular intervals.
Default value: 1
Minimum value: 1

<b>SampleCount</b>
Size of the sample from which to select a request for evaluation. The smaller the sample count, the more accurate is the statistical data. To evaluate all requests, set the sample count to 1. However, such a low setting can result in excessive consumption of memory and processing resources.
Default value: 1
Minimum value: 1
Maximum value: 65535

<b>sort</b>
Sort stored records by the specified statistics column, in descending order. Performed during data collection, the sorting enables real-time data evaluation through NetScaler policies (for example, compression and caching policies) that use functions such as IS_TOP(n).
Possible values: REQUESTS, CONNECTIONS, RESPTIME, BANDWIDTH, RESPTIME_BREACHES, NONE
Default value: REQUESTS

<b>snmptrap</b>
Enable/disable SNMP trap for stream identifier
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>appflowLog</b>
Enable/disable Appflow logging for stream identifier
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>trackTransactions</b>
Track transactions exceeding configured threshold. Transaction tracking can be enabled for following metric: ResponseTime.
By default transaction tracking is disabled
Possible values: RESPTIME, NONE
Default value: NONE

<b>maxTransactionThreshold</b>
Maximum per transcation value of metric. Metric to be tracked is specified by tracktransactions attribute.
Default value: 0
Minimum value: 0

<b>minTransactionThreshold</b>
Minimum per transcation value of metric. Metric to be tracked is specified by tracktransactions attribute.
Default value: 0
Minimum value: 0

<b>acceptanceThreshold</b>
Non-Breaching transactions to Total transactions threshold expressed in percent.
Maximum of 6 decimal places is supported.
Default value: 0.000000

<b>breachThreshold</b>
Breaching transactions threshold calculated over interval.
Default value: 0
Minimum value: 0



##Example

add stream identifier stream_id top_url -interval 10 -sampleCount 1 -sort REQUESTS

##set stream identifier

Modifies the specified parameters of a stream identifier. Parameters for which a default value is available revert to their default values.


##Synopsys

set stream identifier &lt;name> [-selectorName &lt;string>] [-interval &lt;positive_integer>] [-SampleCount &lt;positive_integer>] [-sort &lt;sort>] [-snmptrap ( ENABLED | DISABLED )] [-appflowLog ( ENABLED | DISABLED )] [-trackTransactions ( RESPTIME | NONE )] [-maxTransactionThreshold &lt;positive_integer>] [-minTransactionThreshold &lt;positive_integer>] [-acceptanceThreshold &lt;string>] [-breachThreshold &lt;positive_integer>]


##Arguments

<b>name</b>
The name of stream identifier.

<b>selectorName</b>
Name of the selector to use with the stream identifier.

<b>interval</b>
Number of minutes of data to use when calculating session statistics (number of requests, bandwidth, and response times). The interval is a moving window that keeps the most recently collected data. Older data is discarded at regular intervals.
Default value: 1
Minimum value: 1

<b>SampleCount</b>
Size of the sample from which to select a request for evaluation. The smaller the sample count, the more accurate is the statistical data. To evaluate all requests, set the sample count to 1. However, such a low setting can result in excessive consumption of memory and processing resources.
Default value: 1
Minimum value: 1
Maximum value: 65535

<b>sort</b>
Sort stored records by the specified statistics column, in descending order. Performed during data collection, the sorting enables real-time data evaluation through NetScaler policies (for example, compression and caching policies) that use functions such as IS_TOP(n).
Possible values: REQUESTS, CONNECTIONS, RESPTIME, BANDWIDTH, RESPTIME_BREACHES, NONE
Default value: REQUESTS

<b>snmptrap</b>
Enable/disable SNMP trap for stream identifier
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>appflowLog</b>
Enable/disable Appflow logging for stream identifier
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>trackTransactions</b>
Track transactions exceeding configured threshold. Transaction tracking can be enabled for following metric: ResponseTime.
By default transaction tracking is disabled
Possible values: RESPTIME, NONE
Default value: NONE

<b>maxTransactionThreshold</b>
Maximum per transcation value of metric. Metric to be tracked is specified by tracktransactions attribute.
Default value: 0
Minimum value: 0

<b>minTransactionThreshold</b>
Minimum per transcation value of metric. Metric to be tracked is specified by tracktransactions attribute.
Default value: 0
Minimum value: 0

<b>acceptanceThreshold</b>
Non-Breaching transactions to Total transactions threshold expressed in percent.
Maximum of 6 decimal places is supported.
Default value: 0.000000

<b>breachThreshold</b>
Breaching transactions threshold calculated over interval.
Default value: 0
Minimum value: 0



##Example

set stream identifier stream_id -selectorName top_clients -interval 1 -sampleCount 1 -sort NONE

##unset stream identifier

Use this command to remove stream identifier settings.Refer to the set stream identifier command for meanings of the arguments.


##Synopsys

unset stream identifier &lt;name> [-selectorName] [-interval] [-SampleCount] [-sort] [-snmptrap] [-appflowLog] [-trackTransactions] [-maxTransactionThreshold] [-minTransactionThreshold] [-acceptanceThreshold] [-breachThreshold]


##rm stream identifier

Removes a stream identifier. Note: You cannot remove a stream identifier if it is being used in a policy.


##Synopsys

rm stream identifier &lt;name>


##Arguments

<b>name</b>
The name of stream identifier.



##Example

rm stream identifier stream_id

##show stream identifier

Displays the parameters of the specified stream identifier or, if no stream identifier name is specified, the parameters of all configured stream identifiers.


##Synopsys

show stream identifier [&lt;name>]


##Arguments

<b>name</b>
The name of stream identifier.



##Outputs

<b>selectorName</b>
Name of the selector to use with the stream identifier.

<b>rule</b>
Rule.

<b>ngname</b>
Nodegroup name to which this identifier belongs to.

<b>recordlimit</b>
Maximum number of objects allowed per identifier.

<b>interval</b>
Number of minutes of data to use when calculating session statistics (number of requests, bandwidth, and response times). The interval is a moving window that keeps the most recently collected data. Older data is discarded at regular intervals.

<b>SampleCount</b>
Size of the sample from which to select a request for evaluation. The smaller the sample count, the more accurate is the statistical data. To evaluate all requests, set the sample count to 1. However, such a low setting can result in excessive consumption of memory and processing resources.

<b>sort</b>
Sort stored records by the specified statistics column, in descending order. Performed during data collection, the sorting enables real-time data evaluation through NetScaler policies (for example, compression and caching policies) that use functions such as IS_TOP(n).

<b>snmptrap</b>
Enable/disable SNMP trap for stream identifier

<b>appflowLog</b>
Enable/disable Appflow logging for stream identifier

<b>trackTransactions</b>
Track transactions exceeding configured threshold. Transaction tracking can be enabled for following metric: ResponseTime.
By default transaction tracking is disabled

<b>maxTransactionThreshold</b>
Maximum per transcation value of metric. Metric to be tracked is specified by tracktransactions attribute.

<b>minTransactionThreshold</b>
Minimum per transcation value of metric. Metric to be tracked is specified by tracktransactions attribute.

<b>acceptanceThreshold</b>
Non-Breaching transactions to Total transactions threshold expressed in percent.
Maximum of 6 decimal places is supported.

<b>breachThreshold</b>
Breaching transactions threshold calculated over interval.

<b>log</b>
Location where objects collected on the identifier will be logged.

<b>logInterval</b>
Time interval in minutes for logging the collected objects. Log interval should be greater
than or equal to the inteval of the stream identifier.

<b>logLimit</b>
Maximum number of objects to be logged in the log interval.

<b>builtin</b>
Flag to determine if stream identifier is built-in or not

<b>stateflag</b>
used internally to identify ip addresses returned.

<b>devno</b>

<b>count</b>



##Example

show stream identifier stream_id

##stat stream identifier

Displays the statistics that the NetScaler appliance has collected for the specified stream identifier.


##Synopsys

stat stream identifier &lt;name> [&lt;pattern> ...] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )] [-sortBy &lt;sortBy>  [&lt;sortOrder>]]


##Arguments

<b>name</b>
Name of the stream identifier.

<b>pattern</b>
Values on which grouping is performed are displayed in the output as row titles. If grouping is performed on two or more fields, their values are separated by a question mark in the row title.
For example, consider a selector that contains the expressions HTTP.REQ.URL and CLIENT.IP.SRC (in that order), on an appliance that has accumulated records of a number of requests for two URLs, example.com/page1.html and example.com/page2.html, from two client IP addresses, 192.0.2.10 and 192.0.2.11. 
With a pattern of ? ?, the appliance performs grouping on both fields and displays statistics for the following:
* Requests for example.com/abc.html from 192.0.2.10, with a row title of example.com/abc.html?192.0.2.10.
* Requests for example.com/abc.html from 192.0.2.11, with a row title of example.com/abc.html?192.0.2.11.
* Requests for example.com/def.html from 192.0.2.10, with a row title of example.com/def.html?192.0.2.10.
* Requests for example.com/def.html from 192.0.2.11, with a row title of example.com/def.html?192.0.2.11.
With a pattern of * ?, the appliance performs grouping on only the client IP address values and displays statistics for the following requests:
* All requests from 192.0.2.10, with the IP address as the row title.
* All requests from 192.0.2.11, with the IP address as the row title.
With a pattern of ? *, the appliance performs grouping on only the URL values and displays statistics for the following requests:
* All requests for example.com/abc.html, with the URL as the row title.
* All requests for example.com/def.html, with the URL as the row title.
With a pattern of * *, the appliance displays one set of collective statistics for all the requests received, with no row title.
With a pattern of example.com/abc.html ?, the appliance displays statistics for requests for example.com/abc.html from each unique client IP address.
With a pattern of * 192.0.2.11, the appliance displays statistics for all requests from 192.0.2.11.

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

<b>sortBy</b>
use this argument to sort by specific key
Possible values: Req, BandW, RspTime, Conn, breachcnt, pktCredits

<b>sortOrder</b>
use this argument to specify sort order
Possible values: ascending, descending
Default value: SORT_DESCENDING



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Stream Session Requests (Req)</b>
Total number of Stream Requests recieved.

<b>Stream Session Bandwidth (BandW)</b>
Total Bandwidth consumed.

<b>Stream Session Response Time (RspTime)</b>
Average response time of the stream session.

<b>Stream Session Connections (Conn)</b>
Current connections on the stream session.

<b>Stream Session Breaching Transactions (breachcnt)</b>
Total Breaching Transactions in configured interval.

<b>Stream session packet credits (pktCredits)</b>
Calculated Packet credits on current connection.



