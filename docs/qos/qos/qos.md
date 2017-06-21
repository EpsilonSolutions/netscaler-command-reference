#qos

The following operations can be performed on "qos":


##stat qos

Display QoS statistics.


##Synopsys

stat qos [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>IPC messages sent from QoS (ipcsent)</b>
IPC messages sent from qos system.

<b>IPC messages QoS failed to send (ipcfailed)</b>
IPC messages failed to send from qos system.

<b>IPC messages QoS received (ipcrcvd)</b>
IPC messages received by qos.

<b>IPC messages sent to QoS (pe2qsent)</b>
IPC messages sent to qos system.

<b>IPC messages failed to send QoS (pe2qfail)</b>
IPC messages failed to send to qos system.

<b>IPC messages received from QoS (pe2qrecv)</b>
IPC messages received from qos system.

<b>Bytes QoS marked for drop (bytsdrop)</b>
Bytes QoS marked for drop

<b>QoS bytes sent not classified (bytsntnc)</b>
Bytes scheduled by QoS that were not classified.

<b>QoS bytes dropped no connection (bytdrpnc)</b>
Bytes dropped by QoS when no connection was found.

<b>Packets sent to QoS (qosinpkt)</b>
Packets sent to QoS for scheduling.

<b>Packets from QoS to be sent (qosotpkt)</b>
Packets from QoS to be sent

<b>Packets Dropped by QoS (qosdrpkt)</b>
Packets Dropped by QoS.

<b>Classified source MAC rewritten (qosrwmac)</b>
Number of packets with inband classification in source MAC.

<b>QoS packets unclassified (qosuclas)</b>
Number of packets without classification.

<b>QoS packets classified (qosclas)</b>
Number of packets with classification.

<b>QoS learned true MAC (qoslm)</b>
QoS learned true MAC

<b>QoS Input Bytes (qosib)</b>
Bytes sent to QoS for scheduling

<b>QoS Output Bytes (qosob)</b>
Bytes received from QoS to be sent

<b>QoS Free Held List (qosfc)</b>
No. more packets QoS can hold onto.

<b>QoS Link 00 Bytes Sent (qosl00sd)</b>
QoS bytes sent on Link 00

<b>QoS Link 00 Bytes Dropped (qosl00dr)</b>
QoS bytes dropped on Link 00

<b>QoS Link 01 Bytes Sent (qosl01sd)</b>
QoS bytes sent on Link 01

<b>QoS Link 01 Bytes Dropped (qosl01dr)</b>
QoS bytes dropped on Link 01

<b>QoS Link 02 Bytes Sent (qosl02sd)</b>
QoS bytes sent on Link 02

<b>QoS Link 02 Bytes Dropped (qosl02dr)</b>
QoS bytes dropped on Link 02

<b>QoS Link 03 Bytes Sent (qosl03sd)</b>
QoS bytes sent on Link 03

<b>QoS Link 03 Bytes Dropped (qosl03dr)</b>
QoS bytes dropped on Link 03

<b>QoS Link 04 Bytes Sent (qosl04sd)</b>
QoS bytes sent on Link 04

<b>QoS Link 04 Bytes Dropped (qosl04dr)</b>
QoS bytes dropped on Link 04

<b>QoS Link 05 Bytes Sent (qosl05sd)</b>
QoS bytes sent on Link 05

<b>QoS Link 05 Bytes Dropped (qosl05dr)</b>
QoS bytes dropped on Link 05

<b>QoS Link 06 Bytes Sent (qosl06sd)</b>
QoS bytes sent on Link 06

<b>QoS Link 06 Bytes Dropped (qosl06dr)</b>
QoS bytes dropped on Link 06

<b>QoS Link 07 Bytes Sent (qosl07sd)</b>
QoS bytes sent on Link 07

<b>QoS Link 07 Bytes Dropped (qosl07dr)</b>
QoS bytes dropped on Link 07

<b>QoS Link 08 Bytes Sent (qosl08sd)</b>
QoS bytes sent on Link 08

<b>QoS Link 08 Bytes Dropped (qosl08dr)</b>
QoS bytes dropped on Link 08

<b>QoS Link 09 Bytes Sent (qosl09sd)</b>
QoS bytes sent on Link 09

<b>QoS Link 09 Bytes Dropped (qosl09dr)</b>
QoS bytes dropped on Link 09

<b>QoS Link 10 Bytes Sent (qosl10sd)</b>
QoS bytes sent on Link 10

<b>QoS Link 10 Bytes Dropped (qosl10dr)</b>
QoS bytes dropped on Link 10



