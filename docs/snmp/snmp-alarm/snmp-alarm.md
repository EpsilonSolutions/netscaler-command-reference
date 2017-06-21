#snmp alarm

The following operations can be performed on "snmp alarm":


[set](#set-snmp-alarm) | [unset](#unset-snmp-alarm) | [enable](#enable-snmp-alarm) | [disable](#disable-snmp-alarm) | [show](#show-snmp-alarm)

##set snmp alarm

Configures an SNMP alarm. You must enable and configure alarms to generate enterprise-specific trap messages. The NetScaler appliance sends these trap messages only to trap listeners of type (class) SPECIFIC. The SNMP alarms are either event based or threshold based.The NetScaler appliance supports the following user configurable alarms: HA-STATE-CHANGE:                Change to primary/secondary CPU-USAGE:                      Individual CPU usage AVERAGE-CPU:                    Average CPU usage MGMT-CPU:                       Management CPU usage ENTITY-STATE:                   Entity state change SYNFLOOD:                       Global unacknowledged SYN count MEMORY:                         Memory usage VSERVER-REQRATE:                Vserver specific request rate SERVICE-REQRATE:                Service specific request rate ENTITY-RXRATE:                  Entity specific Rx bytes per sec ENTITY-TXRATE:                  Entity specific Tx bytes per sec ENTITY-SYNFLOOD:                Entity specific unacknowledged SYN count CONFIG-CHANGE:                  System configuration changed SERVICE-MAXCLIENTS:             Service hit max-client limit CONFIG-SAVE:                    System configuration was saved SERVICEGROUP-MEMBER-REQRATE:    Request rate on a service group member SERVICEGROUP-MEMBER-MAXCLIENTS: Service group member hits max-client MONITOR-RTO-THRESHOLD:          Monitor probe response timeout LOGIN-FAILURE:                  GUI/CLI/API login failure SSL-CERT-EXPIRY:                Certificate expiry FAN-SPEED-LOW:                  Low fan speed VOLTAGE-LOW:                    Low voltage VOLTAGE-HIGH:                   High Voltage TEMPERATURE-HIGH:               High temperature CPU-TEMPERATURE-HIGH:           High CPU temperature POWER-SUPPLY-FAILURE:           Power supply failure DISK-USAGE-HIGH:                High disk usage INTERFACE-THROUGHPUT-LOW:       Low Interface throughput MON_PROBE_FAILED:               Monitor probe failure HA-VERSION-MISMATCH:            HA netscaler's OS version mismatch HA-SYNC-FAILURE:                HA config synchronization failure HA-NO-HEARTBEATS:               No HA hearbeats HA-BAD-SECONDARY-STATE:         Secondary state DOWN/UNKNOWN/STAY SECONDARY INTERFACE-BW-USAGE:             System aggregate BW usage RATE-LIMIT-THRESHOLD-EXCEEDED:  Client exceed rate-limit threshold ENTITY-NAME-CHANGE:             Entity name change HA-PROP-FAILURE:                HA config propagation failure IP-CONFLICT:                    IP conflict PF-RL-RATE-THRESHOLD:           Platform rate limit in Mbps PF-RL-PPS-THRESHOLD:            Platform packets per second limit PF-RL-RATE-PKTS-DROPPED:        Packet Drops due to platform rate limit PF-RL-PPS-PKTS-DROPPED:         Packet Drops due to platform packet per sec limit APPFW-START-URL:                AppFirewall Start URL violation APPFW-DENY-URL:                 AppFirewall Deny URL violation APPFW-REFERER-HEADER:           AppFirewall Referer Header violation APPFW-CSRF-TAG:                 AppFirewall CSRF Tag violation APPFW-COOKIE:                   AppFirewall Cookie violation APPFW-FIELD-CONSISTENCY:        AppFirewall Field Consistency violation APPFW-BUFFER-OVERFLOW:          AppFirewall Buffer Overflow violation APPFW-FIELD-FORMAT:             AppFirewall Field Format violation APPFW-SAFE-COMMERCE:            AppFirewall Safe Commerce violation APPFW-SAFE-OBJECT:              AppFirewall Safe Object violation APPFW-POLICY-HIT:               AppFirewall Policy Hit APPFW-VIOLATIONS-TYPE:          AppFirewall Content Type violation APPFW-XSS:                      AppFirewall Cross Site Scripting violation APPFW-XML-XSS:                  AppFirewall XML Cross Site Scripting violation APPFW-SQL:                      AppFirewall SQL violation APPFW-XML-SQL:                  AppFirewall XML SQL violation APPFW-XML-ATTACHMENT:           AppFirewall XML Attachment violation APPFW-XML-DOS:                  AppFirewall XML DoS violation APPFW-XML-VALIDATION:           AppFirewall XML Validation violation APPFW-XML-WSI:                  AppFirewall XML WSI violation APPFW-XML-SCHEMA-COMPILE:       AppFirewall XML Schema Compile violation APPFW-XML-SOAP-FAULT:           AppFirewall XML Soap Fault violation DNSKEY-EXPIRY:                  DNSKEY expiry HA-LICENSE-MISMATCH:            HA netscaler's license mismatch SSL-CARD-FAILED:                SSL Card Failed SSL-CARD-NORMAL:                SSL Card Normal WARM-RESTART-EVENT:             Warm Restart Event Occurred HARD-DISK-DRIVE-ERRORS:         Hard Disk Drive Errors COMPACT-FLASH-ERRORS:           Compact Flash Errors CALLHOME-UPLOAD-EVENT:          Attempt to upload Show Tech Support Archive 1024KEY-EXCHANGE-RATE:          1024 Key Exchange Rate 2048KEY-EXCHANGE-RATE:          2048 Key Exchange Rate 4096KEY-EXCHANGE-RATE:          4096 Key Exchange Rate SSL-CUR-SESSION-INUSE:          SSL Current Sessions In Use  CLUSTER-NODE-HEALTH:            Cluster Node Health State Change CLUSTER-NODE-QUORUM:            Cluster Node View has Quorum CLUSTER-VERSION-MISMATCH:       Cluster Node Version Mismatch CLUSTER-CCO-CHANGE:             Cluster Configuration Coordinator Change CLUSTER-OVS-CHANGE:             Cluster Operational View Set Change CLUSTER-SYNC-FAILURE:           Cluster Config Synchronization Failure CLUSTER-PROP-FAILURE:           Cluster Config Propagation Failure HA-STICKY-PRIMARY:              Fixed primary state owing to max HA flips INBAND-PROTOCOL-VERSION-MISMATCH:     Inband protocol mismatch between BR and QoSd SSL-CHIP-REINIT:                SSL Chip Reinit VRID-STATE-CHANGE:           VRID State Change PORT-ALLOC-FAILED:           Port Alloc Failed LLDP-REMOTE-CHANGE:          LLDP Remote Change DUPLICATE-IPV6:              IPv6 Address got duplicated PARTITION-CONFIG-EVENT:                Partition Added/removed PARTITION-SWITCHED:             Partition Swicthed LSN-PORTALLOC-FAILED:           LSN Port Allocation Failed LSN-PORTQUOTA-EXCEED:           LSN Port Quota Exceeded LSN-SESSIONQUOTA-EXCEED:           LSN Session Quota Exceeded VSERVER-SPILLOVER:	      Vserver spillover occurred PARTITION-RATE-LIMIT:         Partition bandwidth/connection limit exceeded/normal CLUSTER-BACKPLANE-HB-MISSING: Heartbeats are missing on backplaneFor the purposes of this command, entity includes vservers and services.


##Synopsys

set snmp alarm &lt;trapName> [-thresholdValue &lt;positive_integer>  [-normalValue &lt;positive_integer>]] [-time &lt;secs>] [-state ( ENABLED | DISABLED )] [-severity &lt;severity>] [-logging ( ENABLED | DISABLED )]


##Arguments

<b>trapName</b>
Name of the SNMP alarm. This parameter is required for identifying the SNMP alarm and cannot be modified.
Possible values: CPU-USAGE, AVERAGE-CPU, MEMORY, MGMT-CPU-USAGE, SYNFLOOD, VSERVER-REQRATE, SERVICE-REQRATE, ENTITY-RXRATE, ENTITY-TXRATE, ENTITY-SYNFLOOD, SERVICE-MAXCLIENTS, HA-STATE-CHANGE, ENTITY-STATE, CONFIG-CHANGE, CONFIG-SAVE, SERVICEGROUP-MEMBER-REQRATE, SERVICEGROUP-MEMBER-MAXCLIENTS, MONITOR-RTO-THRESHOLD, LOGIN-FAILURE, SSL-CERT-EXPIRY, FAN-SPEED-LOW, VOLTAGE-LOW, VOLTAGE-HIGH, TEMPERATURE-HIGH, CPU-TEMPERATURE-HIGH, POWER-SUPPLY-FAILURE, DISK-USAGE-HIGH, INTERFACE-THROUGHPUT-LOW, MON_PROBE_FAILED, HA-VERSION-MISMATCH, HA-SYNC-FAILURE, HA-NO-HEARTBEATS, HA-BAD-SECONDARY-STATE, INTERFACE-BW-USAGE, RATE-LIMIT-THRESHOLD-EXCEEDED, ENTITY-NAME-CHANGE, HA-PROP-FAILURE, IP-CONFLICT, PF-RL-RATE-THRESHOLD, PF-RL-PPS-THRESHOLD, PF-RL-RATE-PKTS-DROPPED, PF-RL-PPS-PKTS-DROPPED, APPFW-START-URL, APPFW-DENY-URL, APPFW-VIOLATIONS-TYPE, APPFW-REFERER-HEADER, APPFW-CSRF-TAG, APPFW-COOKIE, APPFW-FIELD-CONSISTENCY, APPFW-BUFFER-OVERFLOW, APPFW-FIELD-FORMAT, APPFW-SAFE-COMMERCE, APPFW-SAFE-OBJECT, APPFW-POLICY-HIT, APPFW-XSS, APPFW-XML-XSS, APPFW-SQL, APPFW-XML-SQL, APPFW-XML-ATTACHMENT, APPFW-XML-DOS, APPFW-XML-VALIDATION, APPFW-XML-WSI, APPFW-XML-SCHEMA-COMPILE, APPFW-XML-SOAP-FAULT, DNSKEY-EXPIRY, HA-LICENSE-MISMATCH, SSL-CARD-FAILED, SSL-CARD-NORMAL, WARM-RESTART-EVENT, HARD-DISK-DRIVE-ERRORS, COMPACT-FLASH-ERRORS, CALLHOME-UPLOAD-EVENT, 1024KEY-EXCHANGE-RATE, 2048KEY-EXCHANGE-RATE, 4096KEY-EXCHANGE-RATE, SSL-CUR-SESSION-INUSE, CLUSTER-NODE-HEALTH, CLUSTER-NODE-QUORUM, CLUSTER-VERSION-MISMATCH, CLUSTER-CCO-CHANGE, CLUSTER-OVS-CHANGE, CLUSTER-SYNC-FAILURE, CLUSTER-PROP-FAILURE, HA-STICKY-PRIMARY, INBAND-PROTOCOL-VERSION-MISMATCH, SSL-CHIP-REINIT, VRID-STATE-CHANGE, PORT-ALLOC-FAILED, LLDP-REMOTE-CHANGE, DUPLICATE-IPV6, PARTITION-CONFIG-EVENT, PARTITION-SWITCHED, LSN-PORTALLOC-FAILED, LSN-PORTQUOTA-EXCEED, LSN-SESSIONQUOTA-EXCEED, VSERVER-SPILLOVER, PARTITION-RATE-LIMIT, CLUSTER-BACKPLANE-HB-MISSING

<b>thresholdValue</b>
Value for the high threshold. The NetScaler appliance generates an SNMP trap message when the value of the attribute associated with the alarm is greater than or equal to the specified high threshold value.
Minimum value: 1

<b>normalValue</b>
Value for the normal threshold. A trap message is generated if the value of the respective attribute falls to or below this value after exceeding the high threshold.
Minimum value: 1

<b>time</b>
Interval, in seconds, at which the NetScaler appliance generates SNMP trap messages when the conditions specified in the SNMP alarm are met.Can be specified for the following alarms: SYNFLOOD, HA-VERSION-MISMATCH, HA-SYNC-FAILURE, HA-NO-HEARTBEATS,HA-BAD-SECONDARY-STATE, CLUSTER-NODE-HEALTH, CLUSTER-NODE-QUORUM, CLUSTER-VERSION-MISMATCH, CLUSTER-BKHB-FAILED, PORT-ALLOC-FAILED and APPFW traps. Default trap time intervals: SYNFLOOD and APPFW traps = 1sec, PORT-ALLOC-FAILED = 3600sec(1 hour), Other Traps = 86400sec(1 day)
Default value: 1

<b>state</b>
Current state of the SNMP alarm. The NetScaler appliance generates trap messages only for SNMP alarms that are enabled. Some alarms are enabled by default, but you can disable them.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>severity</b>
Severity level assigned to trap messages generated by this alarm. The severity levels are, in increasing order of severity, Informational, Warning, Minor, Major, and Critical.
This parameter is useful when you want the NetScaler appliance to send trap messages to a trap listener on the basis of severity level. Trap messages with a severity level lower than the specified level (in the trap listener entry) are not sent.
Possible values: Critical, Major, Minor, Warning, Informational
Default value: Unknown

<b>logging</b>
Logging status of the alarm. When logging is enabled, the NetScaler appliance logs every trap message that is generated for this alarm.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set snmp alarm VSERVER-REQRATE -thresholdValue 10000 -normalValue 100

##Related Commands

<ul><li><a href="../../../snmp/snmp">add snmp trap</a></li></ul>



##unset snmp alarm

Resets the specified parameters of an SNMP alarm to their default settings..Refer to the set snmp alarm command for meanings of the arguments.


##Synopsys

unset snmp alarm &lt;trapName> [-thresholdValue] [-normalValue] [-time] [-state] [-severity] [-logging]


##Example

unset snmp alarm VSERVER-REQRATE

##enable snmp alarm

Enables or disables an SNMP alarm. The NetScaler appliance looks for conditions specified in the enabled SNMP alarms. When the condition in any enabled SNMP alarm is met, the appliance generates an SNMP trap message. It does not look for conditions specified in disabled SNMP alarms and therefore does not generate an SNMP trap message when the condition in any disabled SNMP alarm is met. Some alarms are enabled by default, but you can disable them.


##Synopsys

enable snmp alarm &lt;trapName> ...


##Arguments

<b>trapName</b>
Name of the SNMP alarm. This parameter is required for identifying the SNMP alarm.
Possible values: CPU-USAGE, AVERAGE-CPU, MEMORY, MGMT-CPU-USAGE, SYNFLOOD, VSERVER-REQRATE, SERVICE-REQRATE, ENTITY-RXRATE, ENTITY-TXRATE, ENTITY-SYNFLOOD, SERVICE-MAXCLIENTS, HA-STATE-CHANGE, ENTITY-STATE, CONFIG-CHANGE, CONFIG-SAVE, SERVICEGROUP-MEMBER-REQRATE, SERVICEGROUP-MEMBER-MAXCLIENTS, MONITOR-RTO-THRESHOLD, LOGIN-FAILURE, SSL-CERT-EXPIRY, FAN-SPEED-LOW, VOLTAGE-LOW, VOLTAGE-HIGH, TEMPERATURE-HIGH, CPU-TEMPERATURE-HIGH, POWER-SUPPLY-FAILURE, DISK-USAGE-HIGH, INTERFACE-THROUGHPUT-LOW, MON_PROBE_FAILED, HA-VERSION-MISMATCH, HA-SYNC-FAILURE, HA-NO-HEARTBEATS, HA-BAD-SECONDARY-STATE, INTERFACE-BW-USAGE, RATE-LIMIT-THRESHOLD-EXCEEDED, ENTITY-NAME-CHANGE, HA-PROP-FAILURE, IP-CONFLICT, PF-RL-RATE-THRESHOLD, PF-RL-PPS-THRESHOLD, PF-RL-RATE-PKTS-DROPPED, PF-RL-PPS-PKTS-DROPPED, APPFW-START-URL, APPFW-DENY-URL, APPFW-VIOLATIONS-TYPE, APPFW-REFERER-HEADER, APPFW-CSRF-TAG, APPFW-COOKIE, APPFW-FIELD-CONSISTENCY, APPFW-BUFFER-OVERFLOW, APPFW-FIELD-FORMAT, APPFW-SAFE-COMMERCE, APPFW-SAFE-OBJECT, APPFW-POLICY-HIT, APPFW-XSS, APPFW-XML-XSS, APPFW-SQL, APPFW-XML-SQL, APPFW-XML-ATTACHMENT, APPFW-XML-DOS, APPFW-XML-VALIDATION, APPFW-XML-WSI, APPFW-XML-SCHEMA-COMPILE, APPFW-XML-SOAP-FAULT, DNSKEY-EXPIRY, HA-LICENSE-MISMATCH, SSL-CARD-FAILED, SSL-CARD-NORMAL, WARM-RESTART-EVENT, HARD-DISK-DRIVE-ERRORS, COMPACT-FLASH-ERRORS, CALLHOME-UPLOAD-EVENT, 1024KEY-EXCHANGE-RATE, 2048KEY-EXCHANGE-RATE, 4096KEY-EXCHANGE-RATE, SSL-CUR-SESSION-INUSE, CLUSTER-NODE-HEALTH, CLUSTER-NODE-QUORUM, CLUSTER-VERSION-MISMATCH, CLUSTER-CCO-CHANGE, CLUSTER-OVS-CHANGE, CLUSTER-SYNC-FAILURE, CLUSTER-PROP-FAILURE, HA-STICKY-PRIMARY, INBAND-PROTOCOL-VERSION-MISMATCH, SSL-CHIP-REINIT, VRID-STATE-CHANGE, PORT-ALLOC-FAILED, LLDP-REMOTE-CHANGE, DUPLICATE-IPV6, PARTITION-CONFIG-EVENT, PARTITION-SWITCHED, LSN-PORTALLOC-FAILED, LSN-PORTQUOTA-EXCEED, LSN-SESSIONQUOTA-EXCEED, VSERVER-SPILLOVER, PARTITION-RATE-LIMIT, CLUSTER-BACKPLANE-HB-MISSING



##Example

enable snmp alarm VSERVER-REQRATEenable snmp alarm CPU SYNFLOOD

##disable snmp alarm

Disables an SNMP alarm. The NetScaler appliance does not generate trap messages for SNMP alarms that are disabled. Some alarms are enabled by default, but you can disable them.


##Synopsys

disable snmp alarm &lt;trapName> ...


##Arguments

<b>trapName</b>
Name of the SNMP alarm. This parameter is required for identifying the SNMP alarm.
Possible values: CPU-USAGE, AVERAGE-CPU, MEMORY, MGMT-CPU-USAGE, SYNFLOOD, VSERVER-REQRATE, SERVICE-REQRATE, ENTITY-RXRATE, ENTITY-TXRATE, ENTITY-SYNFLOOD, SERVICE-MAXCLIENTS, HA-STATE-CHANGE, ENTITY-STATE, CONFIG-CHANGE, CONFIG-SAVE, SERVICEGROUP-MEMBER-REQRATE, SERVICEGROUP-MEMBER-MAXCLIENTS, MONITOR-RTO-THRESHOLD, LOGIN-FAILURE, SSL-CERT-EXPIRY, FAN-SPEED-LOW, VOLTAGE-LOW, VOLTAGE-HIGH, TEMPERATURE-HIGH, CPU-TEMPERATURE-HIGH, POWER-SUPPLY-FAILURE, DISK-USAGE-HIGH, INTERFACE-THROUGHPUT-LOW, MON_PROBE_FAILED, HA-VERSION-MISMATCH, HA-SYNC-FAILURE, HA-NO-HEARTBEATS, HA-BAD-SECONDARY-STATE, INTERFACE-BW-USAGE, RATE-LIMIT-THRESHOLD-EXCEEDED, ENTITY-NAME-CHANGE, HA-PROP-FAILURE, IP-CONFLICT, PF-RL-RATE-THRESHOLD, PF-RL-PPS-THRESHOLD, PF-RL-RATE-PKTS-DROPPED, PF-RL-PPS-PKTS-DROPPED, APPFW-START-URL, APPFW-DENY-URL, APPFW-VIOLATIONS-TYPE, APPFW-REFERER-HEADER, APPFW-CSRF-TAG, APPFW-COOKIE, APPFW-FIELD-CONSISTENCY, APPFW-BUFFER-OVERFLOW, APPFW-FIELD-FORMAT, APPFW-SAFE-COMMERCE, APPFW-SAFE-OBJECT, APPFW-POLICY-HIT, APPFW-XSS, APPFW-XML-XSS, APPFW-SQL, APPFW-XML-SQL, APPFW-XML-ATTACHMENT, APPFW-XML-DOS, APPFW-XML-VALIDATION, APPFW-XML-WSI, APPFW-XML-SCHEMA-COMPILE, APPFW-XML-SOAP-FAULT, DNSKEY-EXPIRY, HA-LICENSE-MISMATCH, SSL-CARD-FAILED, SSL-CARD-NORMAL, WARM-RESTART-EVENT, HARD-DISK-DRIVE-ERRORS, COMPACT-FLASH-ERRORS, CALLHOME-UPLOAD-EVENT, 1024KEY-EXCHANGE-RATE, 2048KEY-EXCHANGE-RATE, 4096KEY-EXCHANGE-RATE, SSL-CUR-SESSION-INUSE, CLUSTER-NODE-HEALTH, CLUSTER-NODE-QUORUM, CLUSTER-VERSION-MISMATCH, CLUSTER-CCO-CHANGE, CLUSTER-OVS-CHANGE, CLUSTER-SYNC-FAILURE, CLUSTER-PROP-FAILURE, HA-STICKY-PRIMARY, INBAND-PROTOCOL-VERSION-MISMATCH, SSL-CHIP-REINIT, VRID-STATE-CHANGE, PORT-ALLOC-FAILED, LLDP-REMOTE-CHANGE, DUPLICATE-IPV6, PARTITION-CONFIG-EVENT, PARTITION-SWITCHED, LSN-PORTALLOC-FAILED, LSN-PORTQUOTA-EXCEED, LSN-SESSIONQUOTA-EXCEED, VSERVER-SPILLOVER, PARTITION-RATE-LIMIT, CLUSTER-BACKPLANE-HB-MISSING



##Example

disable snmp alarm VSERVER-REQRATEdisable snmp alarm CPU SYNFLOOD

##show snmp alarm

Displays the settings of all SNMP alarms or of the specified SNMP alarm. To display the settings of all the SNMP alarms, run the command without any parameters. To display the settings of a particular SNMP alarm, specify the trapName (Alarm name) of the SNMP alarm.


##Synopsys

show snmp alarm [&lt;trapName>]


##Arguments

<b>trapName</b>
Name of the SNMP alarm whose details you want the NetScaler appliance to display.
Possible values: CPU-USAGE, AVERAGE-CPU, MEMORY, MGMT-CPU-USAGE, SYNFLOOD, VSERVER-REQRATE, SERVICE-REQRATE, ENTITY-RXRATE, ENTITY-TXRATE, ENTITY-SYNFLOOD, SERVICE-MAXCLIENTS, HA-STATE-CHANGE, ENTITY-STATE, CONFIG-CHANGE, CONFIG-SAVE, SERVICEGROUP-MEMBER-REQRATE, SERVICEGROUP-MEMBER-MAXCLIENTS, MONITOR-RTO-THRESHOLD, LOGIN-FAILURE, SSL-CERT-EXPIRY, FAN-SPEED-LOW, VOLTAGE-LOW, VOLTAGE-HIGH, TEMPERATURE-HIGH, CPU-TEMPERATURE-HIGH, POWER-SUPPLY-FAILURE, DISK-USAGE-HIGH, INTERFACE-THROUGHPUT-LOW, MON_PROBE_FAILED, HA-VERSION-MISMATCH, HA-SYNC-FAILURE, HA-NO-HEARTBEATS, HA-BAD-SECONDARY-STATE, INTERFACE-BW-USAGE, RATE-LIMIT-THRESHOLD-EXCEEDED, ENTITY-NAME-CHANGE, HA-PROP-FAILURE, IP-CONFLICT, PF-RL-RATE-THRESHOLD, PF-RL-PPS-THRESHOLD, PF-RL-RATE-PKTS-DROPPED, PF-RL-PPS-PKTS-DROPPED, APPFW-START-URL, APPFW-DENY-URL, APPFW-VIOLATIONS-TYPE, APPFW-REFERER-HEADER, APPFW-CSRF-TAG, APPFW-COOKIE, APPFW-FIELD-CONSISTENCY, APPFW-BUFFER-OVERFLOW, APPFW-FIELD-FORMAT, APPFW-SAFE-COMMERCE, APPFW-SAFE-OBJECT, APPFW-POLICY-HIT, APPFW-XSS, APPFW-XML-XSS, APPFW-SQL, APPFW-XML-SQL, APPFW-XML-ATTACHMENT, APPFW-XML-DOS, APPFW-XML-VALIDATION, APPFW-XML-WSI, APPFW-XML-SCHEMA-COMPILE, APPFW-XML-SOAP-FAULT, DNSKEY-EXPIRY, HA-LICENSE-MISMATCH, SSL-CARD-FAILED, SSL-CARD-NORMAL, WARM-RESTART-EVENT, HARD-DISK-DRIVE-ERRORS, COMPACT-FLASH-ERRORS, CALLHOME-UPLOAD-EVENT, 1024KEY-EXCHANGE-RATE, 2048KEY-EXCHANGE-RATE, 4096KEY-EXCHANGE-RATE, SSL-CUR-SESSION-INUSE, CLUSTER-NODE-HEALTH, CLUSTER-NODE-QUORUM, CLUSTER-VERSION-MISMATCH, CLUSTER-CCO-CHANGE, CLUSTER-OVS-CHANGE, CLUSTER-SYNC-FAILURE, CLUSTER-PROP-FAILURE, HA-STICKY-PRIMARY, INBAND-PROTOCOL-VERSION-MISMATCH, SSL-CHIP-REINIT, VRID-STATE-CHANGE, PORT-ALLOC-FAILED, LLDP-REMOTE-CHANGE, DUPLICATE-IPV6, PARTITION-CONFIG-EVENT, PARTITION-SWITCHED, LSN-PORTALLOC-FAILED, LSN-PORTQUOTA-EXCEED, LSN-SESSIONQUOTA-EXCEED, VSERVER-SPILLOVER, PARTITION-RATE-LIMIT, CLUSTER-BACKPLANE-HB-MISSING



##Outputs

<b>thresholdValue</b>
The high threshold value.

<b>normalValue</b>
The normal threshold value.

<b>time</b>
The time interval for the SYNFLOOD alarm.

<b>state</b>
Current state of the SNMP alarm. The NetScaler appliance generates trap messages only for SNMP alarms that are enabled. Some alarms are enabled by default, but you can disable them.

<b>severity</b>
The severity of this alarm.

<b>logging</b>
The log status of the alarm.

<b>flags</b>

<b>timeout</b>
If DB is enabled and clear config is fired, then to reset timeinterval of alarm, corresponding default time value is needed. This hidden argument holds the default time value for the corresponding alarm.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



