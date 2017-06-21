#dns records

The following operations can be performed on "dns records":


##stat dns records

Displays statistics for the specified DNS record or query type. If a DNS record or query type is not specified, statistics for all record and query types are shown.


##Synopsys

stat dns records [&lt;dnsRecordType>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>dnsRecordType</b>
Display statistics for the specified DNS record or query type or, if a record or query type is not specified, statistics for all record types supported on the NetScaler appliance.

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

<b>Total entries (totEntries)</b>
Total number of DNS record entries

<b>Total updates (totUpdates)</b>
Total number of DNS proactive updates

<b>Total responses (totResp)</b>
Total number of DNS server responses

<b>Total requests (totReq)</b>
Total number of DNS queries recieved

<b>Current entries (curEnt)</b>
Current number of DNS entries

<b>Total limit errors (errLim)</b>
Total number of times we have recieved dns record with more entries than we support

<b>Total response format errors (errRespFor)</b>
Total number of times we have recieved malformed responses from the backend

<b>Total alias exist errors (errAlias)</b>
Total number of times we have recieved non-cname record for a domain for which an alias exists

<b>Total cache misses (errNoDom)</b>
Total number of cache misses

<b>Current records (curRec)</b>
Current number of DNS Records



##Related Commands

<ul><li><a href="../../..//">stat dns</a></li><li><a href="../../../#stat-dns-policy/#stat-dns-policy">stat dns policylabel</a></li></ul>



