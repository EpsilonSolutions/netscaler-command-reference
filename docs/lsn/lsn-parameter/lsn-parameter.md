#lsn parameter

The following operations can be performed on "lsn parameter":


[set](#set-lsn-parameter) | [unset](#unset-lsn-parameter) | [show](#show-lsn-parameter)

##set lsn parameter

Modify the global configuration of the LSN.


##Synopsys

set lsn parameter -sessionSync ( ENABLED | DISABLED )


##Arguments

<b>sessionSync</b>
Synchronize all LSN sessions with the secondary node in a high availability (HA) deployment (global synchronization). After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary node (new primary).
The global session synchronization parameter and session synchronization parameters (group level) of all LSN groups are enabled by default.
For a group, when both the global level and the group level LSN session synchronization parameters are enabled, the primary node synchronizes information of all LSN sessions related to this LSN group with the secondary node.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##unset lsn parameter

Use this command to remove lsn parameter settings.Refer to the set lsn parameter command for meanings of the arguments.


##Synopsys

unset lsn parameter -sessionSync


##show lsn parameter

Display the global configuration of the LSN.


##Synopsys

show lsn parameter


##Outputs

<b>memLimitActive</b>
Amount of actual memory reserved for the LSN feature. 
The amount of active memory for the LSN feature might be less than the configured memory, because the available memory is shared across features.

<b>maxMemLimit</b>
Maximum amount of NetScaler memory that can be reserved for the LSN feature.

<b>memLimit</b>
Amount of NetScaler memory to reserve for the LSN feature, in multiples of 2MB.
Note: If you later reduce the value of this parameter, the amount of active memory is not reduced. Changing the configured memory limit can only increase the amount of active memory.
This command is deprecated, use 'set extendedmemoryparam -memlimit' instead.

<b>sessionSync</b>
Synchronize all LSN sessions with the secondary node in a high availability (HA) deployment (global synchronization). After a failover, established TCP connections and UDP packet flows are kept active and resumed on the secondary node (new primary).
The global session synchronization parameter and session synchronization parameters (group level) of all LSN groups are enabled by default.
For a group, when both the global level and the group level LSN session synchronization parameters are enabled, the primary node synchronizes information of all LSN sessions related to this LSN group with the secondary node.



