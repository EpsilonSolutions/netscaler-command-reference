#extendedmemoryparam

The following operations can be performed on "extendedmemoryparam":


[set](#set-extendedmemoryparam) | [unset](#unset-extendedmemoryparam) | [show](#show-extendedmemoryparam)

##set extendedmemoryparam

Modify the global configuration of the extended memory. This configures memory for LSN and Subscriber Session Store Modules.


##Synopsys

set extendedmemoryparam -memLimit &lt;MBytes>


##Arguments

<b>memLimit</b>
Amount of NetScaler memory to reserve for the memory used by LSN and Subscriber Session Store feature, in multiples of 2MB.
Note: If you later reduce the value of this parameter, the amount of active memory is not reduced. Changing the configured memory limit can only increase the amount of active memory.



##unset extendedmemoryparam

Use this command to remove  extendedmemoryparam settings.Refer to the set  extendedmemoryparam command for meanings of the arguments.


##Synopsys

unset extendedmemoryparam -memLimit


##show extendedmemoryparam

Display the global configuration of extendedmemory. LSN and Subscriber Session Stores use this memory configuration.


##Synopsys

show extendedmemoryparam


##Outputs

<b>memLimitActive</b>
The active memory limit for extendedmemory on the system. Active memory limit could be different from configured memory limit. This could happen when memory limit could not be increased due to unavailability, or could not be decreased as it is already in use. This active memory limit configures the current memory limit for LSN and Subscriber Session Store.

<b>maxMemLimit</b>
The maximum value of memory limit for extendedmemory on the system. Actual available memory may be less. This is maximum memory that can be utilized by LSN and Subscriber Session Store modules.

<b>memLimit</b>
Amount of NetScaler memory to reserve for the memory used by LSN and Subscriber Session Store feature, in multiples of 2MB.
Note: If you later reduce the value of this parameter, the amount of active memory is not reduced. Changing the configured memory limit can only increase the amount of active memory.

<b>minRequiredMemory</b>
The minimum memory requirement for extendedmemory. This is minimum memory required for LSN and Subscriber Session Store Modules.



