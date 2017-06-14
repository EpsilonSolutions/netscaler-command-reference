#audit messages

The following operations can be performed on "audit messages":


##show audit messages

Displays the most recent audit log messages.


##Synopsys

show audit messages [-logLevel &lt;logLevel> ...] [-numOfMesgs &lt;positive_integer>]


##Arguments

<b>logLevel</b>
Audit log level filter, which specifies the types of events to display. 
The following loglevels are valid:
* ALL - All events.
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.

<b>numOfMesgs</b>
Number of log messages to be displayed.
Default value: 20
Minimum value: 1
Maximum value: 256

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>value</b>
The Audit message

<b>devno</b>

<b>count</b>

<b>stateflag</b>



