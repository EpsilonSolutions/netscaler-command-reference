#ns capacity

The following operations can be performed on "ns capacity":


[set](#set-ns-capacity) | [unset](#unset-ns-capacity) | [show](#show-ns-capacity)

##set ns capacity

Modifies the system capacity. Capacity will be check-out from the license pool of License Server


##Synopsys

set ns capacity ((-bandwidth &lt;positive_integer>  -unit ( Gbps | Mbps )) | -platform &lt;platform>) [-Edition &lt;Edition>]


##Arguments

<b>bandwidth</b>
System bandwidth limit.
Minimum value: 0

<b>Edition</b>
Product edition.
Possible values: Standard, Enterprise, Platinum

<b>unit</b>
Bandwidth unit.
Possible values: Gbps, Mbps

<b>platform</b>
appliance platform type.
Possible values: VS1, VP1, VS5, VP5, VS10, VE10, VP10, VS25, VE25, VP25, VS50, VE50, VP50, VS100, VE100, VP100, VS200, VE200, VP200, VS500, VE500, VP500, VS1000, VE1000, VP1000, VP2000, VS3000, VE3000, VP3000, VP4000, VS5000, VE5000, VP5000, VS8000, VE8000, VP8000, CP1000



##unset ns capacity

Use this command to undo configuration changes made to ns capacity parameters..Refer to the set ns capacity command for meanings of the arguments.


##Synopsys

unset ns capacity (-bandwidth | -platform)


##show ns capacity

Displays the running capacity of the system.


##Synopsys

show ns capacity


##Outputs

<b>actualbandwidth</b>
Bandwith in MBPS.

<b>platform</b>
appliance platform type.

<b>Edition</b>
Product edition Standard/Enterprise/Platinum.

<b>unit</b>
Bandwidth unit GBPS/MBPS.

<b>bandwidth</b>
Configured Bandwidth.

<b>maxbandwidth</b>
Maximum Bandwidth.

<b>minbandwidth</b>
Minimum Bandwidth.

<b>instancecount</b>
VPX will consume one instance and MPX will consume zero instance



