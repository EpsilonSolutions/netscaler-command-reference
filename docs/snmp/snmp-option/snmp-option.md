#snmp option

The following operations can be performed on "snmp option":


[set](#set-snmp-option) | [unset](#unset-snmp-option) | [show](#show-snmp-option)

##set snmp option

Enables or disables SNMP options for SNMP SET and SNMP trap logging.


##Synopsys

set snmp option [-snmpset ( ENABLED | DISABLED )] [-snmpTrapLogging ( ENABLED | DISABLED )]


##Arguments

<b>snmpset</b>
Accept SNMP SET requests sent to the NetScaler appliance, and allow SNMP managers to write values to MIB objects that are configured for write access.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>snmpTrapLogging</b>
Log any SNMP trap events (for SNMP alarms in which logging is enabled) even if no trap listeners are configured. With the default setting, SNMP trap events are logged if at least one trap listener is configured on the appliance.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset snmp option

Use this command to remove snmp option settings.Refer to the set snmp option command for meanings of the arguments.


##Synopsys

unset snmp option [-snmpset] [-snmpTrapLogging]


##show snmp option

Displays the settings for the following SNMP options: SNMP SET and SNMP trap Logging.


##Synopsys

show snmp option


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>snmpset</b>
Accept SNMP SET requests sent to the NetScaler appliance, and allow SNMP managers to write values to MIB objects that are configured for write access.

<b>snmpTrapLogging</b>
Log any SNMP trap events (for SNMP alarms in which logging is enabled) even if no trap listeners are configured. With the default setting, SNMP trap events are logged if at least one trap listener is configured on the appliance.



