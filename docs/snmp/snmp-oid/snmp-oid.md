#snmp oid

The following operations can be performed on "snmp oid":


##show snmp oid

Displays the corresponding SNMP OIDs for the virtual servers, services, and service groups configured on the NetScaler appliance. To display the SNMP OID of all entities of a particular type, such as virtual servers, run the command with only that entity type specified. To display the SNMP of a particular entity, specify the entity type and the entity name.


##Synopsys

show snmp oid &lt;entityType> [&lt;name>]


##Arguments

<b>entityType</b>
The type of entity whose SNMP OIDs you want to displayType of entity whose SNMP OIDs you want the NetScaler appliance to display.
Possible values: VSERVER, SERVICE, SERVICEGROUP

<b>name</b>
Name of the entity whose SNMP OID you want the NetScaler appliance to display.



##Outputs

<b>snmpOID</b>
The snmp oid.

<b>stateflag</b>
state flag

<b>devno</b>

<b>count</b>



##Example

show snmp oid VSERVER vs1

