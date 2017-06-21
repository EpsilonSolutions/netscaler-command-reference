#subscriber param

The following operations can be performed on "subscriber param":


[set](#set-subscriber-param) | [unset](#unset-subscriber-param) | [show](#show-subscriber-param)

##set subscriber param

Modifies the subscriber params.


##Synopsys

set subscriber param [-keytype IP] [-interfaceType &lt;interfaceType>]


##Arguments

<b>keytype</b>
Type of subscriber key type IP or IPANDVLAN
Possible values: IP
Default value: IP

<b>interfaceType</b>
Subscriber Interface refers to Netscaler interaction with control plane protocols, RADIUS and GX.
Types of subscriber interface: NONE, RadiusOnly, RadiusAndGx, GxOnly.
NONE: Only static subscribers can be configured.
RadiusOnly: GX interface is absent. Subscriber information is obtained through RADIUS Accounting messages.
RadiusAndGx: Subscriber ID obtained through RADIUS Accounting is used to query PCRF. Subscriber information is obtained from both RADIUS and PCRF.
GxOnly: RADIUS interface is absent. Subscriber information is queried using Subscriber IP.
Possible values: None, RadiusOnly, RadiusAndGx, GxOnly
Default value: None



##unset subscriber param

Use this command to remove subscriber param settings.Refer to the set subscriber param command for meanings of the arguments.


##Synopsys

unset subscriber param [-keytype] [-interfaceType]


##show subscriber param

displays global subscriber params.


##Synopsys

show subscriber param


##Outputs

<b>keytype</b>
Type of subscriber key type IP or IPANDVLAN

<b>interfaceType</b>
Subscriber Interface refers to Netscaler interaction with control plane protocols, RADIUS and GX.
Types of subscriber interface: NONE, RadiusOnly, RadiusAndGx, GxOnly.
NONE: Only static subscribers can be configured.
RadiusOnly: GX interface is absent. Subscriber information is obtained through RADIUS Accounting messages.
RadiusAndGx: Subscriber ID obtained through RADIUS Accounting is used to query PCRF. Subscriber information is obtained from both RADIUS and PCRF.
GxOnly: RADIUS interface is absent. Subscriber information is queried using Subscriber IP.



