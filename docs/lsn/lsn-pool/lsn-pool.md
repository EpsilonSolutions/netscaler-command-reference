#lsn pool

The following operations can be performed on "lsn pool":


[add](#add-lsn-pool) | [rm](#rm-lsn-pool) | [set](#set-lsn-pool) | [unset](#unset-lsn-pool) | [bind](#bind-lsn-pool) | [unbind](#unbind-lsn-pool) | [show](#show-lsn-pool)

##add lsn pool

Add LSN Pool.


##Synopsys

add lsn pool &lt;poolname> [-nattype ( DYNAMIC | DETERMINISTIC )] [-portblockallocation ( ENABLED | DISABLED )] [-portrealloctimeout &lt;secs>] [-maxPortReallocTmq &lt;positive_integer>]


##Arguments

<b>poolname</b>
Name for the LSN pool. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN pool is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn pool1" or 'lsn pool1').

<b>nattype</b>
Type of NAT IP address and port allocation (from the LSN pools bound to an LSN group) for subscribers (of the LSN client entity bound to the LSN group):
Available options function as follows:
* Deterministic - Allocate a NAT IP address and a block of ports to each subscriber (of the LSN client bound to the LSN group). The NetScaler ADC sequentially allocates NAT resources to these subscribers. The NetScaler ADC assigns the first block of ports (block size determined by the port block size parameter of the LSN group) on the beginning NAT IP address to the beginning subscriber IP address. The next range of ports is assigned to the next subscriber, and so on, until the NAT address does not have enough ports for the next subscriber. In this case, the first port block on the next NAT address is used for the subscriber, and so on.  Because each subscriber now receives a deterministic NAT IP address and a block of ports, a subscriber can be identified without any need for logging. For a connection, a subscriber can be identified based only on the NAT IP address and port, and the destination IP address and port.
* Dynamic - Allocate a random NAT IP address and a port from the LSN NAT pool for a subscriber's connection. If port block allocation is enabled (in LSN pool) and a port block size is specified (in the LSN group), the NetScaler ADC allocates a random NAT IP address and a block of ports for a subscriber when it initiates a connection for the first time. The ADC allocates this NAT IP address and a port (from the allocated block of ports) for different connections from this subscriber. If all the ports are allocated (for different subscriber's connections) from the subscriber's allocated port block, the ADC allocates a new random port block for the subscriber.
Only LSN Pools and LSN groups with the same NAT type settings can be bound together. Multiples LSN pools can be bound to an LSN group. A maximum of 16 LSN pools can be bound to an LSN group. 
Possible values: DYNAMIC, DETERMINISTIC
Default value: DYNAMIC

<b>portblockallocation</b>
Allocate a random NAT port block, from the available NAT port pool of an NAT IP address, for each subscriber when the NAT allocation is set as Dynamic NAT. For any connection initiated from a subscriber, the NetScaler ADC allocates a NAT port from the subscriber's allocated NAT port block to create the LSN session.
You must set the port block size in the bound LSN group. For a subscriber, if all the ports are allocated from the subscriber's allocated port block, the NetScaler ADC allocates a new random port block for the subscriber.
For Deterministic NAT, this parameter is enabled by default, and you cannot disable it.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>portrealloctimeout</b>
The waiting time, in seconds, between deallocating LSN NAT ports (when an LSN mapping is removed) and reallocating them for a new LSN session. This parameter is necessary in order to prevent collisions between old and new mappings and sessions. It ensures that all established sessions are broken instead of redirected to a different subscriber. This is not applicable for ports used in:
* Deterministic NAT
* Address-Dependent filtering and Address-Port-Dependent filtering
* Dynamic NAT with port block allocation
In these cases, ports are immediately reallocated.
Default value: 0
Maximum value: 600

<b>maxPortReallocTmq</b>
Maximum number of ports for which the port reallocation timeout applies for each NAT IP address. In other words, the maximum deallocated-port queue size for which the reallocation timeout applies for each NAT IP address.
When the queue size is full, the next port deallocated is reallocated immediately for a new LSN session.
Default value: 65536
Minimum value: 0
Maximum value: 65536



##Example

add lsn pool pool1

##rm lsn pool

Remove LSN Pool.


##Synopsys

rm lsn pool &lt;poolname>


##Arguments

<b>poolname</b>
Name for the LSN pool. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN pool is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn pool1" or 'lsn pool1').



##Example

rm lsn pool pool1

##set lsn pool

Set LSN Pool.


##Synopsys

set lsn pool &lt;poolname> [-portrealloctimeout &lt;secs>] [-maxPortReallocTmq &lt;positive_integer>]


##Arguments

<b>poolname</b>
Name for the LSN pool. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN pool is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn pool1" or 'lsn pool1').

<b>portrealloctimeout</b>
The waiting time, in seconds, between deallocating LSN NAT ports (when an LSN mapping is removed) and reallocating them for a new LSN session. This parameter is necessary in order to prevent collisions between old and new mappings and sessions. It ensures that all established sessions are broken instead of redirected to a different subscriber. This is not applicable for ports used in:
* Deterministic NAT
* Address-Dependent filtering and Address-Port-Dependent filtering
* Dynamic NAT with port block allocation
In these cases, ports are immediately reallocated.
Default value: 0
Maximum value: 600

<b>maxPortReallocTmq</b>
Maximum number of ports for which the port reallocation timeout applies for each NAT IP address. In other words, the maximum deallocated-port queue size for which the reallocation timeout applies for each NAT IP address.
When the queue size is full, the next port deallocated is reallocated immediately for a new LSN session.
Default value: 65536
Minimum value: 0
Maximum value: 65536



##Example

set lsn pool pool1 -portrealloctimeout 10

##unset lsn pool

Use this command to remove lsn pool settings.Refer to the set lsn pool command for meanings of the arguments.


##Synopsys

unset lsn pool &lt;poolname> [-portrealloctimeout] [-maxPortReallocTmq]


##bind lsn pool

Bind LSN Pool with ip address range.


##Synopsys

bind lsn pool &lt;poolname> &lt;lsnip>


##Arguments

<b>poolname</b>
Name for the LSN pool. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN pool is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn pool1" or 'lsn pool1').

<b>lsnip</b>
IPv4 address or a range of IPv4 addresses to be used as NAT IP address(es) for LSN.
After the pool is created, these IPv4 addresses are added to the NetScaler ADC as NetScaler owned IP address of type LSN. A maximum of 4096 IP addresses can be bound to an LSN pool. An LSN IP address associated with an LSN pool cannot be shared with other LSN pools. IP addresses specified for this parameter must not already exist on the NetScaler ADC as any NetScaler owned IP addresses. In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189. You can later remove some or all the LSN IP addresses from the pool, and add IP addresses to the LSN pool.



##Example

bind  lsn pool pool1 1.1.1.1-1.1.1.20

##unbind lsn pool

Unbind LSN Pool with ip address range.


##Synopsys

unbind lsn pool &lt;poolname> &lt;lsnip>


##Arguments

<b>poolname</b>
Name for the LSN pool. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN pool is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn pool1" or 'lsn pool1').

<b>lsnip</b>
IPv4 address or a range of IPv4 addresses to be used as NAT IP address(es) for LSN.
After the pool is created, these IPv4 addresses are added to the NetScaler ADC as NetScaler owned IP address of type LSN. A maximum of 4096 IP addresses can be bound to an LSN pool. An LSN IP address associated with an LSN pool cannot be shared with other LSN pools. IP addresses specified for this parameter must not already exist on the NetScaler ADC as any NetScaler owned IP addresses. In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189. You can later remove some or all the LSN IP addresses from the pool, and add IP addresses to the LSN pool.



##Example

unbind  lsn pool pool1 1.1.1.1-1.1.1.20

##show lsn pool

Display LSN Pool.


##Synopsys

show lsn pool [&lt;poolname>]


##Arguments

<b>poolname</b>
Name for the LSN pool. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN pool is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn pool1" or 'lsn pool1').



##Outputs

<b>lsnip</b>
IPv4 address or a range of IPv4 addresses to be used as NAT IP address(es) for LSN.
After the pool is created, these IPv4 addresses are added to the NetScaler ADC as NetScaler owned IP address of type LSN. A maximum of 4096 IP addresses can be bound to an LSN pool. An LSN IP address associated with an LSN pool cannot be shared with other LSN pools. IP addresses specified for this parameter must not already exist on the NetScaler ADC as any NetScaler owned IP addresses. In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189. You can later remove some or all the LSN IP addresses from the pool, and add IP addresses to the LSN pool.

<b>nattype</b>
Type of NAT IP address and port allocation (from the LSN pools bound to an LSN group) for subscribers (of the LSN client entity bound to the LSN group):
Available options function as follows:
* Deterministic - Allocate a NAT IP address and a block of ports to each subscriber (of the LSN client bound to the LSN group). The NetScaler ADC sequentially allocates NAT resources to these subscribers. The NetScaler ADC assigns the first block of ports (block size determined by the port block size parameter of the LSN group) on the beginning NAT IP address to the beginning subscriber IP address. The next range of ports is assigned to the next subscriber, and so on, until the NAT address does not have enough ports for the next subscriber. In this case, the first port block on the next NAT address is used for the subscriber, and so on.  Because each subscriber now receives a deterministic NAT IP address and a block of ports, a subscriber can be identified without any need for logging. For a connection, a subscriber can be identified based only on the NAT IP address and port, and the destination IP address and port.
* Dynamic - Allocate a random NAT IP address and a port from the LSN NAT pool for a subscriber's connection. If port block allocation is enabled (in LSN pool) and a port block size is specified (in the LSN group), the NetScaler ADC allocates a random NAT IP address and a block of ports for a subscriber when it initiates a connection for the first time. The ADC allocates this NAT IP address and a port (from the allocated block of ports) for different connections from this subscriber. If all the ports are allocated (for different subscriber's connections) from the subscriber's allocated port block, the ADC allocates a new random port block for the subscriber.
Only LSN Pools and LSN groups with the same NAT type settings can be bound together. Multiples LSN pools can be bound to an LSN group. A maximum of 16 LSN pools can be bound to an LSN group.

<b>portrealloctimeout</b>
The waiting time, in seconds, between deallocating LSN NAT ports (when an LSN mapping is removed) and reallocating them for a new LSN session. This parameter is necessary in order to prevent collisions between old and new mappings and sessions. It ensures that all established sessions are broken instead of redirected to a different subscriber. This is not applicable for ports used in:
* Deterministic NAT
* Address-Dependent filtering and Address-Port-Dependent filtering
* Dynamic NAT with port block allocation
In these cases, ports are immediately reallocated.

<b>maxPortReallocTmq</b>
Maximum number of ports for which the port reallocation timeout applies for each NAT IP address. In other words, the maximum deallocated-port queue size for which the reallocation timeout applies for each NAT IP address.
When the queue size is full, the next port deallocated is reallocated immediately for a new LSN session.

<b>portblockallocation</b>
Allocate a random NAT port block, from the available NAT port pool of an NAT IP address, for each subscriber when the NAT allocation is set as Dynamic NAT. For any connection initiated from a subscriber, the NetScaler ADC allocates a NAT port from the subscriber's allocated NAT port block to create the LSN session.
You must set the port block size in the bound LSN group. For a subscriber, if all the ports are allocated from the subscriber's allocated port block, the NetScaler ADC allocates a new random port block for the subscriber.
For Deterministic NAT, this parameter is enabled by default, and you cannot disable it.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn pool pool1

