#gslb domain

The following operations can be performed on "gslb domain":


##stat gslb domain

Displays the statistics associated with a global server load balancing (GSLB) domain.


##Synopsys

stat gslb domain [&lt;name>  [-dnsRecordType &lt;dnsRecordType>]] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the GSLB domain for which to display statistics. If you do not specify a name, statistics are shown for all configured GSLB domains.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>domainHits (Hits)</b>
Total number of DNS queries received.

<b>Dns Record Type (Rec_Type)</b>
Type of DNS record returned



##Related Commands

<ul><li><a href="../../../-gslb/-gslb">stat gslb site</a></li><li><a href="../../../tat-gslb-se/tat-gslb-se">stat gslb service</a></li><li><a href="../../../tat-gslb-vs/tat-gslb-vs">stat gslb vserver</a></li></ul>



