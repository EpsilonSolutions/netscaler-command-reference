#smpp param

The following operations can be performed on "smpp param":


[set](#set-smpp-param) | [unset](#unset-smpp-param) | [show](#show-smpp-param)

##set smpp param

Modifies the SMPP parameters on the NetScaler ADC.


##Synopsys

set smpp param [-clientmode &lt;clientmode>] [-msgQueue ( ON | OFF )] [-msgQueueSize &lt;positive_integer>] [-addrton &lt;positive_integer>] [-addrnpi &lt;positive_integer>] [-addrrange &lt;string>]


##Arguments

<b>clientmode</b>
Mode in which the client binds to the ADC. Applicable settings function as follows:
* TRANSCEIVER - Client can send and receive messages to and from the message center.
* TRANSMITTERONLY - Client can only send messages.
* RECEIVERONLY - Client can only receive messages.
Possible values: TRANSCEIVER, TRANSMITTERONLY, RECEIVERONLY
Default value: TRANSCEIVER

<b>msgQueue</b>
Queue SMPP messages if a client that is capable of receiving the destination address messages is not available.
Possible values: ON, OFF
Default value: OFF

<b>msgQueueSize</b>
Maximum number of SMPP messages that can be queued. After the limit is reached, the NetScaler ADC sends a deliver_sm_resp PDU, with an appropriate error message, to the message center.
Default value: 10000
Minimum value: 0

<b>addrton</b>
Type of Number, such as an international number or a national number, used in the ESME address sent in the bind request.
Default value: 0
Minimum value: 0
Maximum value: 256

<b>addrnpi</b>
Numbering Plan Indicator, such as landline, data, or WAP client, used in the ESME address sent in the bind request.
Default value: 0
Minimum value: 0
Maximum value: 256

<b>addrrange</b>
Set of SME addresses, sent in the bind request, serviced by the ESME.
Default value: "\\\\d*"



##unset smpp param

Use this command to remove smpp param settings.Refer to the set smpp param command for meanings of the arguments.


##Synopsys

unset smpp param [-clientmode] [-msgQueue] [-msgQueueSize] [-addrton] [-addrnpi] [-addrrange]


##show smpp param

Displays the SMPP parameters configured on the NetScaler appliance.


##Synopsys

show smpp param


##Outputs

<b>clientmode</b>
Mode in which the client binds to the ADC. Applicable settings function as follows:
* TRANSCEIVER - Client can send and receive messages to and from the message center.
* TRANSMITTERONLY - Client can only send messages.
* RECEIVERONLY - Client can only receive messages.

<b>msgQueue</b>
Queue SMPP messages if a client that is capable of receiving the destination address messages is not available.

<b>msgQueueSize</b>
Maximum number of SMPP messages that can be queued. After the limit is reached, the NetScaler ADC sends a deliver_sm_resp PDU, with an appropriate error message, to the message center.

<b>addrton</b>
Type of Number, such as an international number or a national number, used in the ESME address sent in the bind request.

<b>addrnpi</b>
Numbering Plan Indicator, such as landline, data, or WAP client, used in the ESME address sent in the bind request.

<b>addrrange</b>
Set of SME addresses, sent in the bind request, serviced by the ESME.



