#dos

The following operations can be performed on "dos":


##stat dos

Displays DoS protection statistics. NOTE: This command is deprecated.HTTP DOS protection feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

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

<b>DOS condition triggered (CndMatch)</b>
Number of times the NetScaler appliance triggered the DOS JavaScript due to a condition match.

<b>Valid DOS clients (ValidClt)</b>
Number of clients from whom the NetScaler appliance received a valid DOS cookie.

<b>DOS priority clients (DosPriCl)</b>
Number of valid clients that were given DOS priority.



##Related Commands

<ul><li><a href="../../../-dos-p/-dos-p">stat dos policy</a></li></ul>



