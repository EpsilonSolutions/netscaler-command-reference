#system globaldata

The following operations can be performed on "system globaldata":


##show system globaldata

Display historical data for global counters.


##Synopsys

show system globaldata &lt;counters> [&lt;countergroup>] [-startTime &lt;string> | (-last &lt;integer>  [&lt;unit>])] [-endTime &lt;string>] [-dataSource &lt;string>] [-core &lt;integer>]


##Arguments

<b>counters</b>
Specify the counters to be collected.

<b>countergroup</b>
Specify the (counter) group name which contains all the counters specific to this particular group.

<b>startTime</b>
Specify start time in mmddyyyyhhmm to start collecting values from that timestamp.

<b>endTime</b>
Specify end time in mmddyyyyhhmm upto which values have to be collected.

<b>last</b>
Last is literal way of saying a certain time period from the current moment. Example: -last 1 hour, -last 1 day, et cetera.
Default value: 1

<b>unit</b>
Specify the  time period from current moment. Example 1 x where x = hours/ days/ years.
Possible values: HOURS, DAYS, MONTHS

<b>dataSource</b>
Specifies the source which contains all the stored counter values.

<b>core</b>
Specify core ID of the PE in nCore.



##Outputs

<b>response</b>

<b>startUpdate</b>

<b>lastupdate</b>



##Example

show system globaldata cpu_usage -last 1 hours

