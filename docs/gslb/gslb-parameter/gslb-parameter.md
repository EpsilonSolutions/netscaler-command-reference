#gslb parameter

The following operations can be performed on "gslb parameter":


[set](#set-gslb-parameter) | [unset](#unset-gslb-parameter) | [show](#show-gslb-parameter)

##set gslb parameter

Sets various global GSLB parameters.


##Synopsys

set gslb parameter [-ldnsEntryTimeout &lt;secs>] [-RTTTolerance &lt;msecs>] [-ldnsMask &lt;netmask>] [-v6ldnsmasklen &lt;positive_integer>] [-ldnsProbeOrder &lt;ldnsProbeOrder> ...] [-dropLdnsReq ( ENABLED | DISABLED )] [-GSLBSvcStateDelayTime &lt;secs>] [-AutomaticConfigSync ( ENABLED | DISABLED )]


##Arguments

<b>ldnsEntryTimeout</b>
Time, in seconds, after which an inactive LDNS entry is removed.
Default value: 180
Minimum value: 30
Maximum value: 65534

<b>RTTTolerance</b>
Tolerance, in milliseconds, for newly learned round-trip time (RTT) values. If the difference between the old RTT value and the newly computed RTT value is less than or equal to the specified tolerance value, the LDNS entry in the network metric table is not updated with the new RTT value. Prevents the exchange of metrics when variations in RTT values are negligible.
Default value: 5
Minimum value: 1
Maximum value: 100

<b>ldnsMask</b>
The IPv4 network mask with which to create LDNS entries.
Default value: 0xFFFFFFFF

<b>v6ldnsmasklen</b>
Mask for creating LDNS entries for IPv6 source addresses. The mask is defined as the number of leading bits to consider, in the source IP address, when creating an LDNS entry.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>ldnsProbeOrder</b>
Order in which monitors should be initiated to calculate RTT.
Possible values: PING, DNS, TCP
Default value: ARRAY(0x2bb8bcf8)

<b>dropLdnsReq</b>
Drop LDNS requests if round-trip time (RTT) information is not available.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>GSLBSvcStateDelayTime</b>
Amount of delay in updating the state of GSLB service to DOWN when MEP goes down.
			This parameter is applicable only if monitors are not bound to GSLB services
Default value: 0
Maximum value: 3600

<b>AutomaticConfigSync</b>
GSLB configuration will be synced automatically to remote gslb sites if enabled.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set gslb parameter -ldnsMask 255.255.0.0

##unset gslb parameter

Use this command to remove gslb parameter settings.Refer to the set gslb parameter command for meanings of the arguments.


##Synopsys

unset gslb parameter [-ldnsEntryTimeout] [-RTTTolerance] [-ldnsMask] [-v6ldnsmasklen] [-ldnsProbeOrder] [-dropLdnsReq] [-GSLBSvcStateDelayTime] [-AutomaticConfigSync]


##show gslb parameter

Displays the global GSLB parameters.


##Synopsys

show gslb parameter


##Outputs

<b>flags</b>
State of the GSLB parameter.

<b>ldnsEntryTimeout</b>
Time, in seconds, after which an inactive LDNS entry is removed.

<b>RTTTolerance</b>
Tolerance, in milliseconds, for newly learned round-trip time (RTT) values. If the difference between the old RTT value and the newly computed RTT value is less than or equal to the specified tolerance value, the LDNS entry in the network metric table is not updated with the new RTT value. Prevents the exchange of metrics when variations in RTT values are negligible.

<b>ldnsMask</b>
The IPv4 network mask with which to create LDNS entries.

<b>v6ldnsmasklen</b>
Mask for creating LDNS entries for IPv6 source addresses. The mask is defined as the number of leading bits to consider, in the source IP address, when creating an LDNS entry.

<b>ldnsProbeOrder</b>
The order in which monitors should be initiated to calculate RTT

<b>dropLdnsReq</b>
Drop LDNS requests if round-trip time (RTT) information is not available.

<b>GSLBSvcStateDelayTime</b>
Amount of delay in updating the state of GSLB service to DOWN when MEP goes down.
			This parameter is applicable only if monitors are not bound to GSLB services

<b>AutomaticConfigSync</b>
GSLB configuration will be synced automatically to remote gslb sites if enabled.



##Example

show gslb parameter

