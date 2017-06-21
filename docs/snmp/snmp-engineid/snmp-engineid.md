#snmp engineId

The following operations can be performed on "snmp engineId":


[set](#set-snmp-engineid) | [unset](#unset-snmp-engineid) | [show](#show-snmp-engineid)

##set snmp engineId

Modifies the SNMPv3 engine identification (ID) on the NetScaler appliance. Caution: Changing the ID of the SNMPv3 engine invalidates the current SNMP users. You have to reconfigure the SNMP users in the SNMP managers.The SNMPv3 engine has an identification (ID) that uniquely identifies it on the appliance and is used in the communication between the SNMPv3 user and the SNMPv3 engine. The engine ID is preconfigured by Citrix and is based on the MAC address of one of its interfaces. Overriding the engine ID is not necessary, but you can change it.


##Synopsys

set snmp engineId &lt;engineID> [-ownerNode &lt;positive_integer>]


##Arguments

<b>engineID</b>
A hexadecimal value of at least 10 characters, uniquely identifying the engineid

<b>ownerNode</b>
ID of the cluster node for which you are setting the engineid
Default value: -1
Minimum value: 0
Maximum value: 31



##unset snmp engineId

Resets the SNMPv3 engine identification (ID) on the NetScaler appliance to its default value. The NetScaler appliance derives the engine ID from the MAC address of one of its interfaces.Caution: Changing the ID of the SNMPv3 engine invalidates the current SNMP users. You have to reconfigure the SNMP users in the SNMP managers..Refer to the set snmp engineId command for meanings of the arguments.


##Synopsys

unset snmp engineId [-ownerNode &lt;positive_integer>]


##show snmp engineId

Displays the ID of the SNMPv3 engine of the NetScaler appliance.


##Synopsys

show snmp engineId [-ownerNode &lt;positive_integer>]


##Arguments

<b>ownerNode</b>
ID of the cluster node for which you are setting the engineid
Default value: -1
Minimum value: 0
Maximum value: 31



##Outputs

<b>engineID</b>
A hexadecimal value of at least 10 characters, uniquely identifying the engineid

<b>defaultEngineID</b>
Unique identifier to assign to the SNMPv3 engine. Should be a hexadecimal value with a minimum length of 10 hex characters.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



