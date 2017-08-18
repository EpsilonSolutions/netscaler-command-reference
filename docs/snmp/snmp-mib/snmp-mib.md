#snmp mib

The following operations can be performed on "snmp mib":


[set](#set-snmp-mib) | [unset](#unset-snmp-mib) | [show](#show-snmp-mib)

##set snmp mib

Configures the SNMP agent of the NetScaler appliance with information that identifies the appliance, such as the name of the administrator for this NetScaler appliance, a name for the appliance, and the location of the appliance. SNMP managers can query the NetScaler appliance for this information.


##Synopsys

set snmp mib [-contact &lt;string>] [-name &lt;string>] [-location &lt;string>] [-customID &lt;string>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>contact</b>
Name of the administrator for this NetScaler appliance. Along with the name, you can include information on how to contact this person, such as a phone number or an email address. Can consist of 1 to 127 characters that include uppercase and  lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the information includes one or more spaces, enclose it in double or single quotation marks (for example, "my contact" or 'my contact').
Default value: "WebMaster (default)"

<b>name</b>
Name for this NetScaler appliance. Can consist of 1 to 127 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.  You should choose a name that helps identify the NetScaler appliance.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose it in double or single quotation marks (for example, "my name" or 'my name').
Default value: "NetScaler"

<b>location</b>
Physical location of the NetScaler appliance. For example, you can specify building name, lab number, and rack number. Can consist of 1 to 127 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the location includes one or more spaces, enclose it in double or single quotation marks (for example, "my location" or 'my location').
Default value: "POP (default)"

<b>customID</b>
Custom identification number for the NetScaler appliance. Can consist of 1 to 127 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters. You should choose a custom identification that helps identify the NetScaler appliance.
The following requirement applies only to the NetScaler CLI:
If the ID includes one or more spaces, enclose it in double or single quotation marks (for example, "my ID" or 'my ID').
Default value: "Default"

<b>ownerNode</b>
ID of the cluster node for which we are setting the mib. This is a mandatory argument to set snmp mib on CLIP.
Default value: -1
Minimum value: 0
Maximum value: 31



##unset snmp mib

Use this command to remove snmp mib settings.Refer to the set snmp mib command for meanings of the arguments.


##Synopsys

unset snmp mib [-contact] [-name] [-location] [-customID] [-ownerNode &lt;positive_integer>]


##show snmp mib

Displays the information that has been configured on the SNMP agent for the purpose of identifying the NetScaler appliance, such as the name of the appliance, administrator, and location.


##Synopsys

show snmp mib [-ownerNode &lt;positive_integer>]


##Arguments

<b>ownerNode</b>
ID of the cluster node for which we are setting the mib. This is a mandatory argument to set snmp mib on CLIP.
Default value: -1
Minimum value: 0
Maximum value: 31



##Outputs

<b>contact</b>
Name of the administrator for this NetScaler appliance. Along with the name, you can include information on how to contact this person, such as a phone number or an email address. Can consist of 1 to 127 characters that include uppercase and  lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the information includes one or more spaces, enclose it in double or single quotation marks (for example, "my contact" or 'my contact').

<b>name</b>
Name for this NetScaler appliance. Can consist of 1 to 127 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.  You should choose a name that helps identify the NetScaler appliance.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose it in double or single quotation marks (for example, "my name" or 'my name').

<b>location</b>
Physical location of the NetScaler appliance. For example, you can specify building name, lab number, and rack number. Can consist of 1 to 127 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the location includes one or more spaces, enclose it in double or single quotation marks (for example, "my location" or 'my location').

<b>sysDesc</b>
The description of the system.

<b>sysUptime</b>
The UP time of the system in 100th of a second.

<b>sysServices</b>
The services offered by the system.

<b>sysOID</b>
The OID of the system's management system.

<b>customID</b>
Custom identification number for the NetScaler appliance. Can consist of 1 to 127 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters. You should choose a custom identification that helps identify the NetScaler appliance.
The following requirement applies only to the NetScaler CLI:
If the ID includes one or more spaces, enclose it in double or single quotation marks (for example, "my ID" or 'my ID').

<b>sysDescCL</b>
The description of the system from aggregator.

<b>sysUptimeCL</b>
The UP time of the system in 100th of a second from aggregator.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show snmp mib

