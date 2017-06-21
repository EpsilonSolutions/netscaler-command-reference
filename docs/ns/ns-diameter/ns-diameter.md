#ns diameter

The following operations can be performed on "ns diameter":


[set](#set-ns-diameter) | [unset](#unset-ns-diameter) | [show](#show-ns-diameter)

##set ns diameter

Set the diameter configuration on NS.


##Synopsys

set ns diameter [-identity &lt;string>] [-realm &lt;string>] [-serverClosePropagation ( YES | NO )]


##Arguments

<b>identity</b>
DiameterIdentity to be used by NS. DiameterIdentity is used to identify a Diameter node uniquely. Before setting up diameter configuration, Netscaler (as a Diameter node) MUST be assigned a unique DiameterIdentity.
example =&gt;
set ns diameter -identity netscaler.com
Now whenever Netscaler system needs to use identity in diameter messages. It will use 'netscaler.com' as Origin-Host AVP as defined in RFC3588

<b>realm</b>
Diameter Realm to be used by NS.
example =&gt;
set ns diameter -realm com
Now whenever Netscaler system needs to use realm in diameter messages. It will use 'com' as Origin-Realm AVP as defined in RFC3588

<b>serverClosePropagation</b>
when a Server connection goes down, whether to close the corresponding client connection if there were requests pending on the server.
Possible values: YES, NO
Default value: NO



##unset ns diameter

Use this command to remove ns diameter settings.Refer to the set ns diameter command for meanings of the arguments.


##Synopsys

unset ns diameter -serverClosePropagation


##show ns diameter

Displays the diameter parameters configured on the NetScaler appliance.


##Synopsys

show ns diameter


##Outputs

<b>identity</b>
DiameterIdentity to be used by NS. DiameterIdentity is used to identify a Diameter node uniquely. Before setting up diameter configuration, Netscaler (as a Diameter node) MUST be assigned a unique DiameterIdentity.
example =>
set ns diameter -identity netscaler.com
Now whenever Netscaler system needs to use identity in diameter messages. It will use 'netscaler.com' as Origin-Host AVP as defined in RFC3588

<b>realm</b>
Diameter Realm to be used by NS.
example =>
set ns diameter -realm com
Now whenever Netscaler system needs to use realm in diameter messages. It will use 'com' as Origin-Realm AVP as defined in RFC3588

<b>serverClosePropagation</b>
when a Server connection goes down, whether to close the corresponding client connection if there were requests pending on the server.



