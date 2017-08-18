#ns vpxparam

The following operations can be performed on "ns vpxparam":


[set](#set-ns-vpxparam) | [show](#show-ns-vpxparam)

##set ns vpxparam

Set vpx configuration settings for the existing vpx.


##Synopsys

set ns vpxparam -cpuyield &lt;cpuyield>


##Arguments

<b>cpuyield</b>
This setting applicable in virtual appliances, is to affect the cpu yield(relinquishing the cpu resources) in any hypervised environment.
* There are 3 options for the behavior:
1. YES - Allow the Virtual Appliance to yield its vCPUs periodically, if there is no data traffic.
2. NO - Virtual Appliance will not yield the vCPU.
3. DEFAULT - Restores the default behaviour, according to the license.
* Its behavior in different scenarios:
1. As this setting is node specific only, it will not be applicable in Cluster and HA scenarios.
2. This setting is a system wide implementation and not granular to vCPUs.
3. No effect on the management PE.
Possible values: DEFAULT, YES, NO



##Example

set ns vpxparam -cpuyield YES/NO

##show ns vpxparam

Display the vpx configuration setting for the vpx.


##Synopsys

show ns vpxparam


##Outputs

<b>cpuyield</b>
Display the vCPU yield setting. In a virtual appliance, CPU yield attribute will release the CPU processing for other virtual appliances on the same platform.



