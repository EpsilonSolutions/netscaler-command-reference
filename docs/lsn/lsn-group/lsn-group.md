#lsn group

The following operations can be performed on "lsn group":


[add](#add-lsn-group) | [rm](#rm-lsn-group) | [set](#set-lsn-group) | [unset](#unset-lsn-group) | [bind](#bind-lsn-group) | [unbind](#unbind-lsn-group) | [show](#show-lsn-group) | [stat](#stat-lsn-group)

##add lsn group

Add LSN Group.


##Synopsys

add lsn group &lt;groupname> -clientname &lt;string> [-nattype ( DYNAMIC | DETERMINISTIC )] [-portblocksize &lt;positive_integer>] [-logging ( ENABLED | DISABLED )] [-sessionLogging ( ENABLED | DISABLED )] [-sessionSync ( ENABLED | DISABLED )] [-snmptraplimit &lt;positive_integer>] [-ftp ( ENABLED | DISABLED )] [-pptp ( ENABLED | DISABLED )] [-sipalg ( ENABLED | DISABLED )] [-rtspalg ( ENABLED | DISABLED )] [-ip6profile &lt;string>]


##Arguments

<b>groupname</b>
Name for the LSN group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn group1" or 'lsn group1').

<b>clientname</b>
Name of the LSN client entity to be associated with the LSN group. You can associate only one LSN client entity with an LSN group.You cannot remove this association or replace with another LSN client entity once the LSN group is created.

<b>nattype</b>
Type of NAT IP address and port allocation (from the bound LSN pools) for subscribers:
Available options function as follows:
* Deterministic - Allocate a NAT IP address and a block of ports to each subscriber (of the LSN client bound to the LSN group). The NetScaler ADC sequentially allocates NAT resources to these subscribers. The NetScaler ADC assigns the first block of ports (block size determined by the port block size parameter of the LSN group) on the beginning NAT IP address to the beginning subscriber IP address. The next range of ports is assigned to the next subscriber, and so on, until the NAT address does not have enough ports for the next subscriber. In this case, the first port block on the next NAT address is used for the subscriber, and so on.  Because each subscriber now receives a deterministic NAT IP address and a block of ports, a subscriber can be identified without any need for logging. For a connection, a subscriber can be identified based only on the NAT IP address and port, and the destination IP address and port. The maximum number of LSN subscribers allowed, globally, is 1 million.  
* Dynamic - Allocate a random NAT IP address and a port from the LSN NAT pool for a subscriber\\?s connection. If port block allocation is enabled (in LSN pool) and a port block size is specified (in the LSN group), the NetScaler ADC allocates a random NAT IP address and a block of ports for a subscriber when it initiates a connection for the first time. The ADC allocates this NAT IP address and a port (from the allocated block of ports) for different connections from this subscriber. If all the ports are allocated (for different subscriber\\?s connections) from the subscriber\\?s allocated port block, the ADC allocates a new random port block for the subscriber.
Possible values: DYNAMIC, DETERMINISTIC
Default value: DYNAMIC

<b>portblocksize</b>
Size of the NAT port block to be allocated for each subscriber.
To set this parameter for Dynamic NAT, you must enable the port block allocation parameter in the bound LSN pool. For Deterministic NAT, the port block allocation parameter is always  enabled, and you cannot disable it.
In Dynamic NAT, the NetScaler ADC allocates a random NAT port block, from the available NAT port pool of an NAT IP address, for each subscriber. For a subscriber, if all the ports are allocated from the subscriber\\?s allocated port block, the ADC allocates a new random port block for the subscriber.
The default port block size is 512 for Deterministic NAT, and 0 for Dynamic NAT.
Default value: 0
Minimum value: 512
Maximum value: 65536

<b>logging</b>
Log mapping entries and sessions created or deleted for this LSN group. The NetScaler ADC logs LSN sessions for this LSN group only when both logging and session logging parameters are enabled.
The ADC uses its existing syslog and audit log framework to log LSN information. You must enable global level LSN logging by enabling the LSN parameter in the related NSLOG action and SYLOG action entities. When the Logging parameter is enabled, the NetScaler ADC generates log messages related to LSN mappings and LSN sessions of this LSN group. The ADC then sends these log messages to servers associated with the NSLOG action and SYSLOG actions entities. 
A log message for an LSN mapping entry consists of the following information:
* NSIP address of the NetScaler ADC
* Time stamp
* Entry type (MAPPING or SESSION)
* Whether the LSN mapping entry is created or deleted
* Subscriber's IP address, port, and traffic domain ID
* NAT IP address and port
* Protocol name
* Destination IP address, port, and traffic domain ID might be  present, depending on the following conditions:
** Destination IP address and port are not logged for Endpoint-Independent mapping
** Only Destination IP address (and not port) is logged for Address-Dependent mapping
** Destination IP address and port are logged for Address-Port-Dependent mapping
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessionLogging</b>
Log sessions created or deleted for the LSN group. The NetScaler ADC logs LSN sessions for this LSN group only when both logging and session logging parameters are enabled.
A log message for an LSN session consists of the following information:
* NSIP address of the NetScaler ADC
* Time stamp
* Entry type (MAPPING or SESSION)
* Whether the LSN session is created or removed
* Subscriber's IP address, port, and traffic domain ID
* NAT IP address and port
* Protocol name
* Destination IP address, port, and traffic domain ID
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessionSync</b>
In a high availability (HA) deployment, synchronize information of all LSN sessions related to this LSN group with the secondary node. After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary node (new primary).
For this setting to work, you must enable the global session synchronization parameter.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>snmptraplimit</b>
Maximum number of SNMP Trap messages that can be generated for the LSN group in one minute.
Default value: 100
Minimum value: 0
Maximum value: 10000

<b>ftp</b>
Enable Application Layer Gateway (ALG) for the FTP protocol. For some application-layer protocols, the IP addresses and protocol port numbers are usually communicated in the packet?s payload. When acting as an ALG, the NetScaler changes the packet?s payload to ensure that the protocol continues to work over LSN. 
Note:  The NetScaler ADC also includes ALG for ICMP and TFTP protocols. ALG for the ICMP protocol is enabled by default, and there is no provision to disable it. ALG for the TFTP protocol is disabled by default. ALG is enabled automatically for an LSN group when you bind a UDP LSN application profile, with endpoint-independent-mapping, endpoint-independent filtering, and destination port as 69 (well-known port for TFTP), to the LSN group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>pptp</b>
Enable the PPTP Application Layer Gateway.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sipalg</b>
Enable the SIP ALG.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rtspalg</b>
Enable the RTSP ALG.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ip6profile</b>
Name of the LSN ip6 profile to associate with the specified LSN group. An ip6 profile can be associated with a group only during group creation.
By default, no LSN ip6 profile is associated with an LSN group during its creation. Only one ip6profile can be associated with a group.



##Example

add lsn group group1

##rm lsn group

Remove LSN Group.


##Synopsys

rm lsn group &lt;groupname>


##Arguments

<b>groupname</b>
Name for the LSN group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn group1" or 'lsn group1').



##Example

rm lsn group group1

##set lsn group

Set LSN Group.


##Synopsys

set lsn group &lt;groupname> [-portblocksize &lt;positive_integer>] [-logging ( ENABLED | DISABLED )] [-sessionLogging ( ENABLED | DISABLED )] [-sessionSync ( ENABLED | DISABLED )] [-snmptraplimit &lt;positive_integer>] [-ftp ( ENABLED | DISABLED )] [-pptp ( ENABLED | DISABLED )] [-sipalg ( ENABLED | DISABLED )] [-rtspalg ( ENABLED | DISABLED )]


##Arguments

<b>groupname</b>
Name for the LSN group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn group1" or 'lsn group1').

<b>portblocksize</b>
Size of the NAT port block to be allocated for each subscriber.
To set this parameter for Dynamic NAT, you must enable the port block allocation parameter in the bound LSN pool. For Deterministic NAT, the port block allocation parameter is always  enabled, and you cannot disable it.
In Dynamic NAT, the NetScaler ADC allocates a random NAT port block, from the available NAT port pool of an NAT IP address, for each subscriber. For a subscriber, if all the ports are allocated from the subscriber\\?s allocated port block, the ADC allocates a new random port block for the subscriber.
The default port block size is 512 for Deterministic NAT, and 0 for Dynamic NAT.
Default value: 0
Minimum value: 512
Maximum value: 65536

<b>logging</b>
Log mapping entries and sessions created or deleted for this LSN group. The NetScaler ADC logs LSN sessions for this LSN group only when both logging and session logging parameters are enabled.
The ADC uses its existing syslog and audit log framework to log LSN information. You must enable global level LSN logging by enabling the LSN parameter in the related NSLOG action and SYLOG action entities. When the Logging parameter is enabled, the NetScaler ADC generates log messages related to LSN mappings and LSN sessions of this LSN group. The ADC then sends these log messages to servers associated with the NSLOG action and SYSLOG actions entities. 
A log message for an LSN mapping entry consists of the following information:
* NSIP address of the NetScaler ADC
* Time stamp
* Entry type (MAPPING or SESSION)
* Whether the LSN mapping entry is created or deleted
* Subscriber's IP address, port, and traffic domain ID
* NAT IP address and port
* Protocol name
* Destination IP address, port, and traffic domain ID might be  present, depending on the following conditions:
** Destination IP address and port are not logged for Endpoint-Independent mapping
** Only Destination IP address (and not port) is logged for Address-Dependent mapping
** Destination IP address and port are logged for Address-Port-Dependent mapping
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessionLogging</b>
Log sessions created or deleted for the LSN group. The NetScaler ADC logs LSN sessions for this LSN group only when both logging and session logging parameters are enabled.
A log message for an LSN session consists of the following information:
* NSIP address of the NetScaler ADC
* Time stamp
* Entry type (MAPPING or SESSION)
* Whether the LSN session is created or removed
* Subscriber's IP address, port, and traffic domain ID
* NAT IP address and port
* Protocol name
* Destination IP address, port, and traffic domain ID
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessionSync</b>
In a high availability (HA) deployment, synchronize information of all LSN sessions related to this LSN group with the secondary node. After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary node (new primary).
For this setting to work, you must enable the global session synchronization parameter.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>snmptraplimit</b>
Maximum number of SNMP Trap messages that can be generated for the LSN group in one minute.
Default value: 100
Minimum value: 0
Maximum value: 10000

<b>ftp</b>
Enable Application Layer Gateway (ALG) for the FTP protocol. For some application-layer protocols, the IP addresses and protocol port numbers are usually communicated in the packet?s payload. When acting as an ALG, the NetScaler changes the packet?s payload to ensure that the protocol continues to work over LSN. 
Note:  The NetScaler ADC also includes ALG for ICMP and TFTP protocols. ALG for the ICMP protocol is enabled by default, and there is no provision to disable it. ALG for the TFTP protocol is disabled by default. ALG is enabled automatically for an LSN group when you bind a UDP LSN application profile, with endpoint-independent-mapping, endpoint-independent filtering, and destination port as 69 (well-known port for TFTP), to the LSN group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>pptp</b>
Enable the PPTP Application Layer Gateway.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sipalg</b>
Enable the SIP ALG.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rtspalg</b>
Enable the RTSP ALG.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set lsn group group1

##unset lsn group

Use this command to remove lsn group settings.Refer to the set lsn group command for meanings of the arguments.


##Synopsys

unset lsn group &lt;groupname> [-portblocksize] [-logging] [-sessionLogging] [-sessionSync] [-snmptraplimit] [-ftp] [-pptp] [-sipalg] [-rtspalg]


##bind lsn group

Bind LSN Group with protocol profiles and pools.


##Synopsys

bind lsn group &lt;groupname> (-poolname &lt;string> | -transportprofilename &lt;string> | -httphdrlogprofilename &lt;string> | -appsprofilename &lt;string> | -sipalgprofilename &lt;string> | -rtspalgprofilename &lt;string>)


##Arguments

<b>groupname</b>
Name for the LSN group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn group1" or 'lsn group1').

<b>poolname</b>
Name of the LSN pool to bind to the specified LSN group. Only LSN Pools and LSN groups with the same NAT type settings can be bound together. Multiples LSN pools can be bound to an LSN group.
For Deterministic NAT, pools bound to an LSN group cannot be bound to other LSN groups. For Dynamic NAT, pools bound to an LSN group can be bound to multiple LSN groups.

<b>transportprofilename</b>
Name of the LSN transport profile to bind to the specified LSN group. Bind a profile for each protocol for which you want to specify settings.
By default, one LSN transport profile with default settings for TCP, UDP, and ICMP protocols is bound to an LSN group during its creation. This profile is called a default transport.
An LSN transport profile that you bind to an LSN group overrides the default LSN transport profile for that protocol.

<b>httphdrlogprofilename</b>
The name of the LSN HTTP header logging Profile.

<b>appsprofilename</b>
Name of the LSN application profile to bind to the specified LSN group. For each set of destination ports, bind a profile for each protocol for which you want to specify settings.
By default, one LSN application profile with default settings for TCP, UDP, and ICMP protocols for all destination ports is bound to an LSN group during its creation.  This profile is called a default application profile.
When you bind an LSN application profile, with a specified set of destination ports, to an LSN group, the bound profile overrides the default LSN application profile for that protocol at that set of destination ports.

<b>sipalgprofilename</b>
The name of the LSN SIP ALG Profile.

<b>rtspalgprofilename</b>
The name of the LSN RTSP ALG Profile.



##Example

bind  lsn group group1 -transportprofile profile1 -appsprofile profile2

##unbind lsn group

Unbind LSN Group with protocol profiles and pools.


##Synopsys

unbind lsn group &lt;groupname> (-poolname &lt;string> | -transportprofilename &lt;string> | -httphdrlogprofilename &lt;string> | -appsprofilename &lt;string> | -sipalgprofilename &lt;string> | -rtspalgprofilename &lt;string>)


##Arguments

<b>groupname</b>
Name for the LSN group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn group1" or 'lsn group1').

<b>poolname</b>
Name of the LSN pool to bind to the specified LSN group. Only LSN Pools and LSN groups with the same NAT type settings can be bound together. Multiples LSN pools can be bound to an LSN group.
For Deterministic NAT, pools bound to an LSN group cannot be bound to other LSN groups. For Dynamic NAT, pools bound to an LSN group can be bound to multiple LSN groups.

<b>transportprofilename</b>
Name of the LSN transport profile to bind to the specified LSN group. Bind a profile for each protocol for which you want to specify settings.
By default, one LSN transport profile with default settings for TCP, UDP, and ICMP protocols is bound to an LSN group during its creation. This profile is called a default transport.
An LSN transport profile that you bind to an LSN group overrides the default LSN transport profile for that protocol.

<b>httphdrlogprofilename</b>
The name of the LSN HTTP header logging Profile.

<b>appsprofilename</b>
Name of the LSN application profile to bind to the specified LSN group. For each set of destination ports, bind a profile for each protocol for which you want to specify settings.
By default, one LSN application profile with default settings for TCP, UDP, and ICMP protocols for all destination ports is bound to an LSN group during its creation.  This profile is called a default application profile.
When you bind an LSN application profile, with a specified set of destination ports, to an LSN group, the bound profile overrides the default LSN application profile for that protocol at that set of destination ports.

<b>sipalgprofilename</b>
The name of the LSN SIP ALG Profile.

<b>rtspalgprofilename</b>
The name of the LSN RTSP ALG Profile.



##Example

unbind  lsn group group1 -transportprofile profile1 -appsprofile profile2

##show lsn group

Display LSN Group.


##Synopsys

show lsn group [&lt;groupname>]


##Arguments

<b>groupname</b>
Name for the LSN group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn group1" or 'lsn group1').



##Outputs

<b>poolname</b>
Name of the LSN pool to bind to the specified LSN group. Only LSN Pools and LSN groups with the same NAT type settings can be bound together. Multiples LSN pools can be bound to an LSN group.
For Deterministic NAT, pools bound to an LSN group cannot be bound to other LSN groups. For Dynamic NAT, pools bound to an LSN group can be bound to multiple LSN groups.

<b>transportprofilename</b>
Name of the LSN transport profile to bind to the specified LSN group. Bind a profile for each protocol for which you want to specify settings.
By default, one LSN transport profile with default settings for TCP, UDP, and ICMP protocols is bound to an LSN group during its creation. This profile is called a default transport.
An LSN transport profile that you bind to an LSN group overrides the default LSN transport profile for that protocol.

<b>appsprofilename</b>
Name of the LSN application profile to bind to the specified LSN group. For each set of destination ports, bind a profile for each protocol for which you want to specify settings.
By default, one LSN application profile with default settings for TCP, UDP, and ICMP protocols for all destination ports is bound to an LSN group during its creation.  This profile is called a default application profile.
When you bind an LSN application profile, with a specified set of destination ports, to an LSN group, the bound profile overrides the default LSN application profile for that protocol at that set of destination ports.

<b>clientname</b>
Name of the LSN client entity to be associated with the LSN group. You can associate only one LSN client entity with an LSN group.You cannot remove this association or replace with another LSN client entity once the LSN group is created.

<b>nattype</b>
Type of NAT IP address and port allocation (from the bound LSN pools) for subscribers:
Available options function as follows:
* Deterministic - Allocate a NAT IP address and a block of ports to each subscriber (of the LSN client bound to the LSN group). The NetScaler ADC sequentially allocates NAT resources to these subscribers. The NetScaler ADC assigns the first block of ports (block size determined by the port block size parameter of the LSN group) on the beginning NAT IP address to the beginning subscriber IP address. The next range of ports is assigned to the next subscriber, and so on, until the NAT address does not have enough ports for the next subscriber. In this case, the first port block on the next NAT address is used for the subscriber, and so on.  Because each subscriber now receives a deterministic NAT IP address and a block of ports, a subscriber can be identified without any need for logging. For a connection, a subscriber can be identified based only on the NAT IP address and port, and the destination IP address and port. The maximum number of LSN subscribers allowed, globally, is 1 million.  
* Dynamic - Allocate a random NAT IP address and a port from the LSN NAT pool for a subscriber\\?s connection. If port block allocation is enabled (in LSN pool) and a port block size is specified (in the LSN group), the NetScaler ADC allocates a random NAT IP address and a block of ports for a subscriber when it initiates a connection for the first time. The ADC allocates this NAT IP address and a port (from the allocated block of ports) for different connections from this subscriber. If all the ports are allocated (for different subscriber\\?s connections) from the subscriber\\?s allocated port block, the ADC allocates a new random port block for the subscriber.

<b>portblocksize</b>
Size of the NAT port block to be allocated for each subscriber.
To set this parameter for Dynamic NAT, you must enable the port block allocation parameter in the bound LSN pool. For Deterministic NAT, the port block allocation parameter is always  enabled, and you cannot disable it.
In Dynamic NAT, the NetScaler ADC allocates a random NAT port block, from the available NAT port pool of an NAT IP address, for each subscriber. For a subscriber, if all the ports are allocated from the subscriber\\?s allocated port block, the ADC allocates a new random port block for the subscriber.
The default port block size is 512 for Deterministic NAT, and 0 for Dynamic NAT.

<b>logging</b>
Log mapping entries and sessions created or deleted for this LSN group. The NetScaler ADC logs LSN sessions for this LSN group only when both logging and session logging parameters are enabled.
The ADC uses its existing syslog and audit log framework to log LSN information. You must enable global level LSN logging by enabling the LSN parameter in the related NSLOG action and SYLOG action entities. When the Logging parameter is enabled, the NetScaler ADC generates log messages related to LSN mappings and LSN sessions of this LSN group. The ADC then sends these log messages to servers associated with the NSLOG action and SYSLOG actions entities. 
A log message for an LSN mapping entry consists of the following information:
* NSIP address of the NetScaler ADC
* Time stamp
* Entry type (MAPPING or SESSION)
* Whether the LSN mapping entry is created or deleted
* Subscriber's IP address, port, and traffic domain ID
* NAT IP address and port
* Protocol name
* Destination IP address, port, and traffic domain ID might be  present, depending on the following conditions:
** Destination IP address and port are not logged for Endpoint-Independent mapping
** Only Destination IP address (and not port) is logged for Address-Dependent mapping
** Destination IP address and port are logged for Address-Port-Dependent mapping

<b>sessionLogging</b>
Log sessions created or deleted for the LSN group. The NetScaler ADC logs LSN sessions for this LSN group only when both logging and session logging parameters are enabled.
A log message for an LSN session consists of the following information:
* NSIP address of the NetScaler ADC
* Time stamp
* Entry type (MAPPING or SESSION)
* Whether the LSN session is created or removed
* Subscriber's IP address, port, and traffic domain ID
* NAT IP address and port
* Protocol name
* Destination IP address, port, and traffic domain ID

<b>sessionSync</b>
In a high availability (HA) deployment, synchronize information of all LSN sessions related to this LSN group with the secondary node. After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary node (new primary).
For this setting to work, you must enable the global session synchronization parameter.

<b>snmptraplimit</b>
Maximum number of SNMP Trap messages that can be generated for the LSN group in one minute.

<b>ftp</b>
Enable Application Layer Gateway (ALG) for the FTP protocol. For some application-layer protocols, the IP addresses and protocol port numbers are usually communicated in the packet?s payload. When acting as an ALG, the NetScaler changes the packet?s payload to ensure that the protocol continues to work over LSN. 
Note:  The NetScaler ADC also includes ALG for ICMP and TFTP protocols. ALG for the ICMP protocol is enabled by default, and there is no provision to disable it. ALG for the TFTP protocol is disabled by default. ALG is enabled automatically for an LSN group when you bind a UDP LSN application profile, with endpoint-independent-mapping, endpoint-independent filtering, and destination port as 69 (well-known port for TFTP), to the LSN group.

<b>pptp</b>
Enable the PPTP Application Layer Gateway.

<b>groupId</b>

<b>sipalg</b>
Enable the SIP ALG.

<b>sipalgprofilename</b>
The name of the LSN SIP ALG Profile.

<b>rtspalg</b>
Enable the RTSP ALG.

<b>rtspalgprofilename</b>
The name of the LSN RTSP ALG Profile.

<b>ip6profile</b>
Name of the LSN ip6 profile to associate with the specified LSN group. An ip6 profile can be associated with a group only during group creation.
By default, no LSN ip6 profile is associated with an LSN group during its creation. Only one ip6profile can be associated with a group.

<b>httphdrlogprofilename</b>
The name of the LSN HTTP header logging Profile.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn group group1

##stat lsn group

Display statistics for all LSN groups or display detailed statistics for the specified LSN group.


##Synopsys

stat lsn group [&lt;groupname>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>groupname</b>
Name of the LSN Group.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Current Sessions (Session)</b>
Number of Current Sessions for LSN group

<b>Translated Bytes (Bytes)</b>
Number of Translated Bytes for LSN group

<b>Translated Pkts (Pkts)</b>
Number of Translated Pkts for LSN group

<b>TCP Translated Pkts (TcpTranslPkts)</b>
Number of TCP Translated Pkts for LSN group

<b>TCP Translated Bytes (TcpTranslBytes)</b>
Number of TCP Translated Bytes for LSN group

<b>TCP Dropped Pkts (TcpDrpPkts)</b>
Number of TCP Dropped Pkts for LSN group

<b>TCP Current Sessions (TcpSess)</b>
Number of TCP Current Sessions for LSN group

<b>UDP Translated Pkts (UdpTranslPkts)</b>
Number of UDP Translated Pkts for LSN group

<b>UDP Translated Bytes (UdpTranslBytes)</b>
Number of UDP Translated Bytes for LSN group

<b>UDP Dropped Pkts (UdpDrpPkts)</b>
Number of UDP Dropped Pkts for LSN group

<b>UDP Current Sessions (UdpSess)</b>
Number of UDP Current Sessions for LSN group

<b>ICMP Translated Pkts (IcmpTranslPkts)</b>
Number of ICMP Translated Pkts for LSN group

<b>ICMP Translated Bytes (IcmpTranslBytes)</b>
Number of ICMP Translated Bytes for LSN group

<b>ICMP Dropped Pkts (IcmpDrpPkts)</b>
Number of ICMP Dropped Pkts for LSN group

<b>ICMP Current Sessions (IcmpSess)</b>
Number of ICMP Current Sessions for LSN group

<b>Current Subscribers (Subscr)</b>
Number of ICMP Current Sessions for LSN group



##Related Commands

<ul><li><a href="../../..//">stat lsn</a></li><li><a href="../../../-lsn-d/-lsn-d">stat lsn dslite</a></li></ul>



