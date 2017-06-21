#ns idletimeout

The following operations can be performed on "ns idletimeout":


[set](#set-ns-idletimeout) | [unset](#unset-ns-idletimeout) | [show](#show-ns-idletimeout)

##set ns idletimeout

Set the pcb/natpcb idletimeout. NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>tcpsvr</b>
Set the idletimeout for server side pcb.

<b>tcpclt</b>
Set the idletimeout for client side pcb.

<b>nontcpsvrclt</b>
Set the idletimeout for natpcb.
Default value: 120
Minimum value: 1



##Example

set ns idletimeout -tcpsvr 120 set ns idletimeout -tcpclt 120 set ns idletimeout -nontcpsvrclt 120

##unset ns idletimeout

Use this command to remove ns idletimeout settings.Refer to the set ns idletimeout command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##show ns idletimeout

Display the global setting of pcb/natpcb idletimeout. NOTE: This command is deprecated.This command is deprecated in favour of 'set ns timeout'


##Synopsys




##Outputs

<b>tcpsvr</b>
Set the idletimeout for server side pcb.

<b>tcpclt</b>
Set the idletimeout for client side pcb.

<b>nontcpsvrclt</b>
Set the idletimeout for natpcb.



