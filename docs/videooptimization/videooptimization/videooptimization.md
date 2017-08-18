#videooptimization

The following operations can be performed on "videooptimization":


##stat videooptimization

Shows video optimization statistics


##Synopsys

stat videooptimization [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>ClearText PD Video (CTPDVideo)</b>

<b>ClearText ABR Video (CTABVideo)</b>

<b>Encrypted ABR Video (EABVideo)</b>

<b>Other (videooptOther)</b>

<b>ClearText ABR Video Sessions (CTABVideoSes)</b>

<b>Encrypted ABR Video Sessions (EABVideoSes)</b>

<b>ClearText PD Bytes (CTPDVideoBytes)</b>

<b>ClearText ABR Bytes (CTABVideoBytes)</b>

<b>Encrypted ABR Bytes (EABVideoBytes)</b>

<b>Other (videooptOtherBytes)</b>



##Related Commands

<ul><li><a href="../../../ptimization-policy.html#stat-videooptimization-p/ptimization-policy.html#stat-videooptimization-p">stat videooptimization policy</a></li><li><a href="../../../ptimization-policylabel.html#stat-videooptimization-policy/ptimization-policylabel.html#stat-videooptimization-policy">stat videooptimization policylabel</a></li></ul>



