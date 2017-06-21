#inatsession

The following operations can be performed on "inatsession":


##stat inatsession

Display statistics for stateful inat sessions.


##Synopsys

stat inatsession &lt;name> [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
INAT name

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

<b>INAT total sessions (inatTotHits)</b>
INAT total sessions

<b>INAT Current sessions (inatCurSessions)</b>
INAT current sessions

<b>INAT total Received Bytes (inatTotReceiveBytes)</b>
INAT total Received Bytes

<b>INAT total Sent Bytes (inatTotSentBytes)</b>
INAT total Sent Bytes

<b>INAT total Packets Received (inatTotpktreceived)</b>
INAT total Packets Received

<b>INAT total Packets Sent (inatTotpktsent)</b>
INAT total Packets Sent



##Example

stat inatsession inat_1

