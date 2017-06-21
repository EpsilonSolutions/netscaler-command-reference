#sc parameter

The following operations can be performed on "sc parameter":


[set](#set-sc-parameter) | [unset](#unset-sc-parameter) | [show](#show-sc-parameter)

##set sc parameter

Sets the parameters for displaying SureConnect information.


##Synopsys

set sc parameter [-sessionLife &lt;secs>] [-vsr &lt;input_filename>]


##Arguments

<b>sessionLife</b>
Time, in seconds, between the first time and the next time the SureConnect alternative content window is displayed. The alternative content window is displayed only once during a session for the same browser accessing a configured URL, so this parameter determines the length of a session.
Default value: 300
Minimum value: 1
Maximum value: 4294967294

<b>vsr</b>
File containing the customized response to be displayed when the ACTION in the SureConnect policy is set to NS.
Default value: "DEFAULT"



##Example

set sc parameter -sessionlife 200 -vsr /etc/vsr.htm

##unset sc parameter

Use this command to remove sc parameter settings.Refer to the set sc parameter command for meanings of the arguments.


##Synopsys

unset sc parameter [-sessionLife] [-vsr]


##show sc parameter

Displays the values of the session life and vsr filename parameters.


##Synopsys

show sc parameter


##Outputs

<b>sessionLife</b>
The time between first time the Sureconnect aternate content window displays and the next time it displays.The SureConnect alternate content window is displayed only once during a session. For the same browser accessing a configured URL.The value is in seconds.

<b>vsr</b>
The customized response will be displayed to the user if the alternate content server has been determined by the system to have failed.
If you have created a customized response that you want the system to use, enter its filename (if you renamed the vsr.htm file supplied by  system). If you have not renamed the file, enter /etc/vsr.htm as the filename.



##Example

&gt; show sc parameter      Sure Connect Parameters:      Sessionlife: 300      Vsr: DEFAULT Done

