#ns tcpbufParam

The following operations can be performed on "ns tcpbufParam":


[set](#set-ns-tcpbufparam) | [unset](#unset-ns-tcpbufparam) | [show](#show-ns-tcpbufparam)

##set ns tcpbufParam

Sets the attributes for the TCP buffering per connection.


##Synopsys

set ns tcpbufParam [-size &lt;KBytes>] [-memLimit &lt;MBytes>]


##Arguments

<b>size</b>
TCP buffering size per connection, in kilobytes.
Default value: 64
Minimum value: 4
Maximum value: 20480

<b>memLimit</b>
Maximum memory, in megabytes, that can be used for buffering.
Default value: 64



##unset ns tcpbufParam

Use this command to remove ns tcpbufParam settings.Refer to the set ns tcpbufParam command for meanings of the arguments.


##Synopsys

unset ns tcpbufParam [-size] [-memLimit]


##show ns tcpbufParam

Displays the TCP buffering configuration on the appliance.


##Synopsys

show ns tcpbufParam


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>size</b>
TCP buffering size per connection, in kilobytes.

<b>memLimit</b>
Maximum memory, in megabytes, that can be used for buffering.



##Example

An example of this command's output is as follows:TCP buffer size: 64KBytesTCP buffer percentage: 50%

