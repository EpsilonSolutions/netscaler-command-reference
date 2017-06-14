#inatsession

The following operations can be performed on "inatsession":


##stat inatsession

Display statistics for stateful inat sessions.


##Synopsys

stat inatsession &lt;name> [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
INAT name

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

