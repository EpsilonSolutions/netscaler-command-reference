#dos

The following operations can be performed on "dos":


##stat dos

Displays DoS protection statistics.


##Synopsys

stat dos [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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



