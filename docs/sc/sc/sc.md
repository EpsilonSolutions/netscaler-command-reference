#sc

The following operations can be performed on "sc":


##stat sc

Displays SureConnect statistics.


##Synopsys

stat sc [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>SC condition triggered (ScTrigd)</b>
Number of times that SureConnect conditions were triggered.

<b>SC trigger condition failed</b>
Total number of times SureConnect was not triggered because the thresholds conditions failed.

<b>Policy matches</b>
Total number of incoming requests that matched configured sureconnect policies.

<b>SC responses sent</b>
Total number of in-memory java script  served which throws the pop-up window.

<b>Reissued requests (ReissReq)</b>
Total number of reissued SureConnect requests.

<b>Valid reissued requests</b>
Total number of requests that were  handled in a single SureConnect session.

<b>Alternate content requests</b>
Total number of alternate content served which throws the pop-up window.

<b>SC POST requests</b>
Total number of   HTTP POST requests that triggered SureConnect feature.

<b>SC statistics timeout</b>
Toal number of times that SureConnect statistics were reset.

<b>Unsupported browsers</b>
Total number of requests that came from all unsupported browsers.

<b>Tampered SC cookies</b>
Total number of corrupted SureConnect cookies.



##Related Commands

<ul><li><a href="../../../c-p/c-p">stat sc policy</a></li></ul>



