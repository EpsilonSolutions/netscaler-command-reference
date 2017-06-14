#gslb config

The following operations can be performed on "gslb config":


##sync gslb config

Synchronizes the GSLB running configuration on all NetScaler appliances participating in the GSLB setup. The appliance on which this command is run is considered the master node. All GSLB sites configured on the master node and not having a parent site are synchronized with the master node.


##Synopsys

sync gslb config [-preview | -forceSync &lt;string> | -command &lt;string> | -nowarn | -saveconfig] [-debug]


##Arguments

<b>preview</b>
Do not synchronize the GSLB sites, but display the commands that would be applied on the slave node upon synchronization. Mutually exclusive with the Save Configuration option.

<b>debug</b>
Generate verbose output when synchronizing the GSLB sites. The Debug option generates more verbose output than the sync gslb config command in which the option is not used, and is useful for analyzing synchronization issues.

<b>forceSync</b>
Force synchronization of the specified site even if a dependent configuration on the remote site is preventing synchronization or if one or more GSLB entities on the remote site have the same name but are of a different type. You can specify either the name of the remote site that you want to synchronize with the local site, or you can specify All Sites in the configuration utility (the string all-sites in the CLI). If you specify All Sites, all the sites in the GSLB setup are synchronized with the site on the master node. 
Note: If you select the Force Sync option, the synchronization starts without displaying the commands that are going to be executed.

<b>nowarn</b>
Suppress the warning and the confirmation prompt that are displayed before site synchronization begins. This option can be used in automation scripts that must not be interrupted by a prompt.

<b>saveconfig</b>
Save the configuration on all the nodes participating in the synchronization process, automatically. The master saves its configuration immediately before synchronization begins. Slave nodes save their configurations after the process of synchronization is complete. A slave node saves its configuration only if the configuration difference was successfully applied to it. Mutually exclusive with the Preview option.

<b>command</b>
Run the specified command on the master node and then on all the slave nodes. You cannot use this option with the force sync and preview options.



##Example

sync gslb config

