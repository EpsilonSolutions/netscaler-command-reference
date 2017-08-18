#snmp trap

The following operations can be performed on "snmp trap":


[add](#add-snmp-trap) | [rm](#rm-snmp-trap) | [set](#set-snmp-trap) | [unset](#unset-snmp-trap) | [show](#show-snmp-trap) | [bind](#bind-snmp-trap) | [unbind](#unbind-snmp-trap)

##add snmp trap

Adds an SNMP trap listener. You can configure the NetScaler appliance to generate asynchronous events (trap messages) to report abnormal conditions. The trap messages are sent to a remote device (trap listener) to help administrators monitor the appliance and respond promptly to any issues.


##Synopsys

add snmp trap &lt;trapClass> &lt;trapDestination> ... [-version &lt;version>] [-td &lt;positive_integer>] [-destPort &lt;port>] [-communityName &lt;string>] [-srcIP &lt;ip_addr|ipv6_addr>] [-severity &lt;severity>] [-allPartitions ( ENABLED | DISABLED )]


##Arguments

<b>trapClass</b>
Type of trap messages that the NetScaler appliance sends to the trap listener: Generic or the enterprise-specific messages defined in the MIB file.
Possible values: generic, specific

<b>trapDestination</b>
IPv4 or the IPv6 address of the trap listener to which the NetScaler appliance is to send SNMP trap messages.

<b>version</b>
SNMP version, which determines the format of trap messages sent to the trap listener. 
This setting must match the setting on the trap listener. Otherwise, the listener drops the trap messages.
Possible values: V1, V2, V3
Default value: V2

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>destPort</b>
UDP port at which the trap listener listens for trap messages. This setting must match the setting on the trap listener. Otherwise, the listener drops the trap messages.
Default value: 162
Minimum value: 1
Maximum value: 65534

<b>communityName</b>
Password (string) sent with the trap messages, so that the trap listener can authenticate them. Can include 1 to 31 uppercase or lowercase letters, numbers, and hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore (_) characters.  
You must specify the same community string on the trap listener device. Otherwise, the trap listener drops the trap messages.
The following requirement applies only to the NetScaler CLI:
If the string includes one or more spaces, enclose the name in double or single quotation marks (for example, "my string" or 'my string').

<b>srcIP</b>
IPv4 or IPv6 address that the NetScaler appliance inserts as the source IP address in all SNMP trap messages that it sends to this trap listener. By default this is the appliance's NSIP or NSIP6 address, but you can specify an IPv4 MIP or SNIP/SNIP6 address. In cluster setup, the default value is the individual node's NSIP, but it can be set to CLIP or Striped SNIP address. In non default partition, this parameter must be set to the SNIP/SNIP6 address.

<b>severity</b>
Severity level at or above which the NetScaler appliance sends trap messages to this trap listener. The severity levels, in increasing order of severity, are Informational, Warning, Minor, Major, Critical. This parameter can be set for trap listeners of type SPECIFIC only. The default is to send all levels of trap messages. 
Important: Trap messages are not assigned severity levels unless you specify severity levels when configuring SNMP alarms.
Possible values: Critical, Major, Minor, Warning, Informational
Default value: Unknown

<b>allPartitions</b>
Send traps of all partitions to this destination.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##rm snmp trap

Removes a trap listener entry from the NetScaler appliance.


##Synopsys

rm snmp trap &lt;trapClass> &lt;trapDestination> ... [-version &lt;version>] [-td &lt;positive_integer>]


##Arguments

<b>trapClass</b>
Trap type specified in the trap listener entry that you want to remove.
Possible values: generic, specific

<b>trapDestination</b>
IP address of the trap listener specified in the trap listener entry that you want to remove.

<b>version</b>
Version of the trap specified in the trap listener entry that you want to remove.
Possible values: V1, V2, V3
Default value: V2

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##set snmp trap

Modifies the specified parameters in a trap-listener entry.


##Synopsys

set snmp trap &lt;trapClass> &lt;trapDestination> [-version &lt;version>] [-td &lt;positive_integer>] [-destPort &lt;port>] [-communityName &lt;string>] [-srcIP &lt;ip_addr|ipv6_addr>] [-severity &lt;severity>] [-allPartitions ( ENABLED | DISABLED )]


##Arguments

<b>trapClass</b>
Type of trap specified in the trap-listener entry. Because this parameter is used for identifying the trap listener entry, it cannot be modified after the entry has been created.
Possible values: generic, specific

<b>trapDestination</b>
IPv4 or the IPv6 address of the trap listener to which the NetScaler appliance is to send SNMP trap messages.

<b>version</b>
SNMP version, which determines the format of trap messages sent to the trap listener. 
This setting must match the setting on the trap listener. Otherwise, the listener drops the trap messages.
Possible values: V1, V2, V3
Default value: V2

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>destPort</b>
UDP port at which the trap listener listens for trap messages. This setting must match the setting on the trap listener. Otherwise, the listener drops the trap messages.
Default value: 162
Minimum value: 1
Maximum value: 65534

<b>communityName</b>
Password (string) sent with the trap messages, so that the trap listener can authenticate them. Can include 1 to 31 uppercase or lowercase letters, numbers, and hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore (_) characters.  
You must specify the same community string on the trap listener device. Otherwise, the trap listener drops the trap messages.
The following requirement applies only to the NetScaler CLI:
If the string includes one or more spaces, enclose the name in double or single quotation marks (for example, "my string" or 'my string').

<b>srcIP</b>
IPv4 or IPv6 address that the NetScaler appliance inserts as the source IP address in all SNMP trap messages that it sends to this trap listener. By default this is the appliance's NSIP or NSIP6 address, but you can specify an IPv4 MIP or SNIP/SNIP6 address. In cluster setup, the default value is the individual node's NSIP, but it can be set to CLIP or Striped SNIP address. In non default partition, this parameter must be set to the SNIP/SNIP6 address.

<b>severity</b>
Severity level at or above which the NetScaler appliance sends trap messages to this trap listener. The severity levels, in increasing order of severity, are Informational, Warning, Minor, Major, Critical. This parameter can be set for trap listeners of type SPECIFIC only. The default is to send all levels of trap messages. 
Important: Trap messages are not assigned severity levels unless you specify severity levels when configuring SNMP alarms.
Possible values: Critical, Major, Minor, Warning, Informational
Default value: Unknown

<b>allPartitions</b>
Send traps of all partitions to this destination.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set snmp trap generic 192.168.3.4 -version V1 -severity Critical

##unset snmp trap

Resets the specified parameters to their default settings in a trap-listener entry..Refer to the set snmp trap command for meanings of the arguments.


##Synopsys

unset snmp trap &lt;trapClass> &lt;trapDestination> [-version &lt;version>] [-td &lt;positive_integer>] [-destPort] [-communityName] [-srcIP] [-severity] [-allPartitions]


##Example

unset snmp trap generic 192.168.3.4 -version V1 -severity

##show snmp trap

Displays the settings of all trap listeners or of the specified trap listener. To display the settings of all the trap listeners, run the command without any parameters. To display the settings of a particular trap listener, specify the trapClass (Trap Type) and trapDestination (IP Address) of the trap listener.


##Synopsys

show snmp trap [&lt;trapClass>  &lt;trapDestination>  [-version &lt;version>]  [-td &lt;positive_integer>]]


##Arguments

<b>trapClass</b>
Trap type specified in the trap listener entry.
Possible values: generic, specific

<b>trapDestination</b>
IP address specified in the trap listener entry.

<b>version</b>
The SNMP version of the trap specified in the trap listener entry.
Possible values: V1, V2, V3

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Outputs

<b>destPort</b>
The destination port of the SNMP trap.

<b>communityName</b>
Password (string) sent with the trap messages, so that the trap listener can authenticate them. Can include 1 to 31 uppercase or lowercase letters, numbers, and hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore (_) characters.  
You must specify the same community string on the trap listener device. Otherwise, the trap listener drops the trap messages.
The following requirement applies only to the NetScaler CLI:
If the string includes one or more spaces, enclose the name in double or single quotation marks (for example, "my string" or 'my string').

<b>srcIP</b>
The source IP of the SNMP trap to be sent.

<b>severity</b>
The minimum severity of traps to be sent to this destination.

<b>allPartitions</b>
Send traps of all partitions to this destination.

<b>userName</b>
Name of the SNMP user that will send the SNMPv3 traps.

<b>securityLevel</b>
Security level of the SNMPv3 trap.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

show snmp trap

##bind snmp trap

Binds an SNMPv3 trap to an SNMP user.


##Synopsys

bind snmp trap &lt;trapClass> &lt;trapDestination> [-td &lt;positive_integer>] [-version &lt;version>] (-userName &lt;string>  [-securityLevel &lt;securityLevel>])


##Arguments

<b>trapClass</b>
Type of trap messages that the NetScaler appliance sends to the trap listener: Generic or the enterprise-specific messages defined in the MIB file.
Possible values: generic, specific

<b>trapDestination</b>
IPv4 or the IPv6 address of the trap listener to which the NetScaler appliance is to send SNMP trap messages.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>version</b>
SNMP version, which determines the format of trap messages sent to the trap listener. 
This setting must match the setting on the trap listener. Otherwise, the listener drops the trap messages.
Possible values: V1, V2, V3
Default value: V3

<b>userName</b>
Name of the SNMP user that will send the SNMPv3 traps.

<b>securityLevel</b>
Security level of the SNMPv3 trap.
Possible values: noAuthNoPriv, authNoPriv, authPriv
Default value: authNoPriv,



##unbind snmp trap

Unbind snmp user to a V3 trap


##Synopsys

unbind snmp trap &lt;trapClass> &lt;trapDestination> [-td &lt;positive_integer>] [-version &lt;version>] -userName &lt;string>


##Arguments

<b>trapClass</b>
Type of trap messages that the NetScaler appliance sends to the trap listener: Generic or the enterprise-specific messages defined in the MIB file.
Possible values: generic, specific

<b>trapDestination</b>
IPv4 or the IPv6 address of the trap listener to which the NetScaler appliance is to send SNMP trap messages.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>version</b>
SNMP version, which determines the format of trap messages sent to the trap listener. 
This setting must match the setting on the trap listener. Otherwise, the listener drops the trap messages.
Possible values: V1, V2, V3
Default value: V3

<b>userName</b>
Name of the SNMP user that will send the SNMPv3 traps.



