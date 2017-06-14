#lldp param

The following operations can be performed on "lldp param":


[set](#set-lldp-param) | [unset](#unset-lldp-param) | [show](#show-lldp-param)

##set lldp param

Sets the global Link Layer Discovery Protocol (LLDP) parameters such as LLDP Timer, Hold Time Multiplier, and LLDP mode.


##Synopsys

set lldp param [-holdtimeTxMult &lt;positive_integer>] [-timer &lt;positive_integer>] [-Mode &lt;Mode>]


##Arguments

<b>holdtimeTxMult</b>
A multiplier for calculating the duration for which the receiving device stores the LLDP information in its database before discarding or removing it. The duration is calculated as the holdtimeTxMult (Holdtime Multiplier) parameter value multiplied by the timer (Timer) parameter value.
Default value: 4
Minimum value: 1
Maximum value: 20

<b>timer</b>
Interval, in seconds, between LLDP packet data units (LLDPDUs).  that the NetScaler ADC sends to a directly connected device.
Default value: 30
Minimum value: 1
Maximum value: 3000

<b>Mode</b>
Global mode of Link Layer Discovery Protocol (LLDP) on the NetScaler ADC. The resultant LLDP mode of an interface depends on the LLDP mode configured at the global and the interface levels.
Possible values: NONE, TRANSMITTER, RECEIVER, TRANSCEIVER



##Example

set lldpparam -mode RECEIVER

##unset lldp param

Use this command to remove lldp param settings.Refer to the set lldp param command for meanings of the arguments.


##Synopsys

unset lldp param [-holdtimeTxMult] [-timer] [-Mode]


##show lldp param

Display the global LLDP params


##Synopsys

show lldp param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>holdtimeTxMult</b>
A multiplier for calculating the duration for which the receiving device stores the LLDP information in its database before discarding or removing it. The duration is calculated as the holdtimeTxMult (Holdtime Multiplier) parameter value multiplied by the timer (Timer) parameter value.

<b>timer</b>
Interval, in seconds, between LLDP packet data units (LLDPDUs).  that the NetScaler ADC sends to a directly connected device.

<b>Mode</b>
Global mode of Link Layer Discovery Protocol (LLDP) on the NetScaler ADC. The resultant LLDP mode of an interface depends on the LLDP mode configured at the global and the interface levels.



##Example

show lldpparam

