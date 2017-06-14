#vpath

The following operations can be performed on "vpath":


[add](#add-vpath) | [rm](#rm-vpath) | [show](#show-vpath) | [stat](#stat-vpath)

##add vpath

Adds vPath destination IP to which packets need to be vPath injected.


##Synopsys

add vpath &lt;name> (&lt;destIP>  [&lt;netmask>]  [&lt;gateway>])


##Arguments

<b>name</b>
Name for the vPath. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the profile is created. Choose a name that helps identify the net profile.

<b>destIP</b>
This is the destination ip, where vPath encapsulated packets needs to be sent



##Example

add vpath vPath1 -destip 10.102.1.10 

##rm vpath

Remove vPath destination IP.


##Synopsys

rm vpath &lt;name> ...


##Arguments

<b>name</b>
Name of the vPath to be removed.



##Example

rm netProfile prof1

##show vpath

List down all vPath destination IPs.


##Synopsys

show vpath [&lt;name>]


##Arguments

<b>name</b>
Name of the vPath whose details you want to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>destIP</b>
This is the destination ip, where vPath encapsulated packets needs to be sent

<b>netmask</b>
Subnet mask associated with the destination network.

<b>gateway</b>
Next hop gateway to reach the destination address.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show vpath

##stat vpath

Display vPath statistics.


##Synopsys

stat vpath [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>L2 data packets received (TotL2DataRx)</b>
Total number of non-fragmented vPath data packets decapsulated in L2 adjacency

<b>L3 data packets received (TotL3DataRx)</b>
Total number of non-fragmented vPath data packets decapsulated in L3 adjacency

<b>L2 control packets received (TotL2CntrlPkts)</b>
Total number of vPath control packets received in L2 adjacency

<b>L3 control packets received (TotL3CntrlPkts)</b>
Total number of vPath control packets received in L3 adjacency

<b>Fragmented packets received (TotFragPkts)</b>
Total number of vPath fragments received

<b>L2 packets transmitted (TotL2EncapPkts)</b>
Total number of L2 vPath encapsulated packets injected to VEM

<b>L3 packets transmitted (TotL3EncapPkts)</b>
Total number of L3 vPath encapsulated packets injected to VEM

<b>Fragmented packets transmitted (TotFragEncapPkts)</b>
Number of fragmented vPath packets transmitted

<b>Offload packets transmitted (TotOffload)</b>
Number of offloaded vPath packets transmitted



