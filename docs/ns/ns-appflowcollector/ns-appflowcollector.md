#ns appflowCollector

The following operations can be performed on "ns appflowCollector":


[add](#add-ns-appflowcollector) | [rm](#rm-ns-appflowcollector) | [show](#show-ns-appflowcollector)

##add ns appflowCollector

Add a new AppFlow collector. NOTE: This command is deprecated.This command is deprecated in favor of 'add appflow collector'


##Synopsys




##Arguments

<b>name</b>
Name of the AppFlow collector.

<b>IPAddress</b>
The IPv4 address of the AppFlow collector.

<b>port</b>
The UDP port on which the AppFlow collector is listening.
Default value: 4739



##Example

add ns appflowCollector collector1 -IPAddress 192.168.1.40 -port 2055

##rm ns appflowCollector

Remove an AppFlow collector. NOTE: This command is deprecated.This command is deprecated in favor of 'rm appflow collector'


##Synopsys




##Arguments

<b>name</b>
Name of an AppFlow collector.



##Example

rm ns appflowCollector collector1

##show ns appflowCollector

Display details of all the AppFlow collectors configured on the system. Alternatively, to view the details of a particular AppFlow collector, specify its name. NOTE: This command is deprecated.This command is deprecated in favor of 'show appflow collector'


##Synopsys




##Arguments

<b>name</b>
Name of the AppFlow collector.



##Outputs

<b>IPAddress</b>
The IPv4 address of the AppFlow collector.

<b>port</b>
The UDP port on which the AppFlow collector is listening.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ns appflowCollector collector1

