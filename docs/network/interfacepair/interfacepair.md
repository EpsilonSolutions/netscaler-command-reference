#interfacePair

The following operations can be performed on "interfacePair":


[add](#add-interfacepair) | [rm](#rm-interfacepair) | [show](#show-interfacepair)

##add interfacePair

Create an Interface Pair. Each Interface Pair or IFPAIR is identified by a IFID (integer from 1-255).


##Synopsys

add interfacePair &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
The Interface pair id
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
The constituent interfaces in the interface pair
Minimum value: 1



##rm interfacePair

Removes the IFPAIR created by the add intfPair command. Once the IFPAIR is removed, its interfaces become independent.


##Synopsys

rm interfacePair &lt;id>


##Arguments

<b>id</b>
The Interface pair id
Minimum value: 1
Maximum value: 255



##show interfacePair

Displays the configured Interface Pairs. If id is specified, then only that particular IFPAIR information is displayed. If it is not specified, all configured IFPAIRs are displayed.


##Synopsys

show interfacePair [&lt;id>]


##Arguments

<b>id</b>
The Interface pair id
Minimum value: 1
Maximum value: 255

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>ifnum</b>
The constituent interfaces in the interface pair

<b>ifaces</b>
Names of all member interfaces of this Interface Pair

<b>stateflag</b>
state flag

<b>devno</b>

<b>count</b>



##Example

An example of the output of the show interfacepair command is as follows:1)      IFPAIR ID: 3        Member Interfaces : 1/4 1/32)      IFPAIR ID: 4        Member Interfaces : 1/6 1/5 Done

