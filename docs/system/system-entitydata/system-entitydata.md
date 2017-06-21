#system entitydata

The following operations can be performed on "system entitydata":


[rm](#rm-system-entitydata) | [show](#show-system-entitydata)

##rm system entitydata

Removes the specified entity from historical charting along with all the associated counters till the current time stamp.


##Synopsys

rm system entitydata [&lt;type>] [&lt;name>] [-allDeleted] [-allInactive] [-dataSource &lt;string>] [-core &lt;integer>]


##Arguments

<b>type</b>
Specify the entity type.

<b>name</b>
Specify the entity name.

<b>allDeleted</b>
Specify this if you would like to delete information about all deleted entities from the database.

<b>allInactive</b>
Specify this if you would like to delete information about all inactive entities from the database.

<b>dataSource</b>
Specifies the source which contains all the stored counter values.

<b>core</b>
Specify core ID of the PE in nCore.



##show system entitydata

Display the historical data for entity specific counters.


##Synopsys

show system entitydata &lt;type> &lt;name> &lt;counters> [-startTime &lt;string> | (-last &lt;integer>  [&lt;unit>])] [-endTime &lt;string>] [-dataSource &lt;string>] [-core &lt;integer>]


##Arguments

<b>type</b>
Specify the entity type.

<b>name</b>
Specify the entity name.

<b>counters</b>
Specify the counters to be collected.

<b>startTime</b>
Specify start time in mmddyyyyhhmm to start collecting values from that timestamp.

<b>endTime</b>
Specify end time in mmddyyyyhhmm upto which values have to be collected.

<b>last</b>
Last is literal way of saying a certain time period from the current moment. Example: -last 1 hour, -last 1 day, et cetera.
Default value: 1

<b>unit</b>
Specify the time period from current moment. Example 1 x where x = hours/ days/ years.
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

show system entitydata lbvserver v1 totalrequests -last 1 days

