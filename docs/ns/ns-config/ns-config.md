#ns config

The following operations can be performed on "ns config":


[clear](#clear-ns-config) | [set](#set-ns-config) | [unset](#unset-ns-config) | [save](#save-ns-config) | [show](#show-ns-config) | [diff](#diff-ns-config) | [query](#query-ns-config)

##clear ns config

Clears the NetScaler running configurations based on different levels.


##Synopsys

clear ns config [-force] &lt;level>


##Arguments

<b>force</b>
Configurations will be cleared without prompting for confirmation.

<b>level</b>
Types of configurations to be cleared.
* basic: Clears all configurations except the following:
  - NSIP, default route (gateway), MIPs, and SNIPs
  - Network settings (DG, VLAN, RHI and DNS settings)
  - Cluster settings
  - HA node definitions
  - Feature and mode settings
  - nsroot password
* extended: Clears the same configurations as the 'basic' option. In addition, it clears the nsroot password and feature and mode settings.
* full: Clears all configurations except NSIP, default route, and interface settings.
Note: When you clear the configurations through the cluster IP address, by specifying the level as 'full', the cluster is deleted and all cluster nodes become standalone appliances. The 'basic' and 'extended' levels are propagated to the cluster nodes.
Possible values: basic, extended, full



##set ns config

Sets the NetScaler IP address and NetScaler VLAN. To set other NetScaler parameters, use the 'set ns param' command.Note: To change the NSIP address or the NSVLAN of an appliance that is part of a cluster, first remove the appliance from the cluster, change the NSIP or the NSVLAN, and then add the appliance back to the cluster.


##Synopsys

set ns config [-IPAddress &lt;ip_addr>  -netmask &lt;netmask>] [-nsvlan &lt;positive_integer>  -ifnum &lt;interface_name> ...  [-tagged ( YES | NO )]]


##Arguments

<b>IPAddress</b>
IP address of the NetScaler appliance. Commonly referred to as NSIP address. This parameter is mandatory to bring up the appliance.

<b>netmask</b>
Netmask corresponding to the IP address. This parameter is mandatory to bring up the appliance.

<b>nsvlan</b>
VLAN (NSVLAN) for the subnet on which the IP address resides.
Minimum value: 2
Maximum value: 4094

<b>ifnum</b>
Interfaces of the appliances that must be bound to the NSVLAN.
Minimum value: 1

<b>tagged</b>
Specifies that the interfaces will be added as 802.1q tagged interfaces. Packets sent on these interface on this VLAN will have an additional 4-byte 802.1q tag which identifies the VLAN.
To use 802.1q tagging, the switch connected to the appliance's interfaces must also be configured for tagging.
Possible values: YES, NO
Default value: YES



##unset ns config

Removes the attributes of the NetScaler appliance. Attributes for which a default value is available revert to their default values. Refer to the 'set ns config' command for a description of the parameters..Refer to the set ns config command for meanings of the arguments.


##Synopsys

unset ns config [-nsvlan] [-IPAddress] [-netmask] [-ifnum] [-tagged]


##save ns config

Save the configurations to the appliances FLASH memory in the /nsconfig/ns.conf file. Backup configuration files are named ns.conf.n. The most recent backup file has the smallest value for n.


##Synopsys

save ns config


##Outputs

<b>message</b>



##show ns config

Displays the following details of the NetScaler appliance:* NetScaler IP address and subnet mask* Number of mapped IP addresses* Identifies the appliance as a standalone appliance, a part of a HA pair, or is a cluster node* Current time on the system and timestamp when the appliance was last updatedNote: To view the complete configurations that have been executed on the appliance, run the 'show ns runningConfig' command.


##Synopsys

show ns config


##Outputs

<b>IPAddress</b>
IP Address of the System.

<b>netmask</b>
The netmask corresponding to the IP address.

<b>mappedIP</b>
Mapped IP Address of the System.

<b>range</b>
The range of Mapped IP addresses to be configured.

<b>nsvlan</b>
The VLAN (NSVLAN) for the subnet on which the system IP resides.

<b>ifnum</b>
Bind the given ports to the NSVLAN.

<b>tagged</b>
Specifies that the interfaces will be added as 802.1q tagged interfaces. Packets sent on these interface on this VLAN will have an additional 4-byte 802.1q tag which identifies the VLAN.
To use 802.1q tagging, the switch connected to the appliance's interfaces must also be configured for tagging.

<b>httpPort</b>
The HTTP ports on the Web server.

<b>maxConn</b>
Maximum Number of Connections.

<b>maxReq</b>
Maxmimum Number of requests that can be handled.

<b>cip</b>
Insertion of client IP address into the HTTP header.

<b>cipHeader</b>
The text that will be used as the client IP header.

<b>cookieversion</b>
The version of the cookie inserted by system.

<b>secureCookie</b>
enable/disable secure flag for persistence cookie

<b>failover</b>
Standalone node.

<b>systemType</b>
The type of the System. Possible Values: Standalone, HA, Cluster

<b>primaryIP</b>
HA Master Node IP address.

<b>pmtuMin</b>
The minimum Path MTU.

<b>pmtuTimeout</b>
The timeout value in minutes.

<b>ftpPortRange</b>
Port range configured for FTP services.

<b>crPortRange</b>
Port range for cache redirection services.

<b>flags</b>
The flags for this entry.

<b>timezone</b>
Name of the timezone

<b>LastConfigChangedTime</b>
Time when the configuration was last modified.

<b>LastConfigSaveTime</b>
Time when the configuration was last saved through savensconfig.

<b>currentSytemTime</b>
current system time in date format.

<b>systemTime</b>
current system time.

<b>grantQuotaMaxClient</b>
The percentage of shared quota to be granted at a time for maxClient

<b>exclusiveQuotaMaxClient</b>
The percentage of maxClient to be given to PEs

<b>grantQuotaSpillOver</b>
The percentage of shared quota to be granted at a time for spillover

<b>exclusiveQuotaSpillOver</b>
The percentage of max limit to be given to PEs

<b>nwfwmode</b>
Network Firewallmode

<b>ConfigChanged</b>
returns True if configuration has changed since last saved config.



##diff ns config

Difference between two configuration


##Synopsys

diff ns config [&lt;config1>] [&lt;config2>] [-outtype ( cli | xml )] [-template] [-ignoreDeviceSpecific]


##Arguments

<b>config1</b>
Location of the configurations.

<b>config2</b>
Location of the configurations.

<b>outtype</b>
Format to display the difference in configurations.
Possible values: cli, xml

<b>template</b>
File that contains the commands to be compared.

<b>ignoreDeviceSpecific</b>
Suppress device specific differences.



##Outputs

<b>response</b>



##Example

Generates the differences between two configurations.Note: If no parameters are provided, then the differences between the saved configurations and the running configurations are shown.

##query ns config

Queries NS config


##Synopsys

query ns config [-weakpassword  [-config &lt;string>]]


##Arguments

<b>weakpassword</b>
Option to list all weak passwords (not adhering to strong password requirements). Takes config file as input, if no input specified, running configuration is considered. Command =&gt; query ns config -weakpassword  / query ns config -weakpassword /nsconfig/ns.conf

<b>config</b>
configuration File to be used to find weak passwords, if not specified, running config is taken as input.



##Outputs

<b>response</b>



##Example

query ns config -weakpassword

