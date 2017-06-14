#system eventhistory

The following operations can be performed on "system eventhistory":


##show system eventhistory

Display events in  historical data.


##Synopsys

show system eventhistory [-startTime &lt;string> | (-last &lt;integer>  [&lt;unit>])] [-endTime &lt;string>] -dataSource &lt;string>


##Arguments

<b>startTime</b>
Specify start time in mmddyyyyhhmm to start collecting values from that timestamp.

<b>endTime</b>
Specify end time in mmddyyyyhhmm upto which values have to be collected.

<b>last</b>
Last is literal way of saying a certain time period from the current moment. Example: -last 1 hour, -last 1 day, et cetera.
Default value: 1

<b>dataSource</b>
Specifies the source which contains all the stored counter values.



##Outputs

<b>response</b>



