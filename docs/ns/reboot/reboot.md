#reboot

The following operations can be performed on "reboot":


##reboot

Restarts the NetScaler appliance.Note:* When a standalone NetScaler appliance is rebooted, the unsaved configurations (configurations performed since the last 'save ns config' command was issued) are lost.* In the high availability mode, when the primary appliance is rebooted, the secondary system takes over and becomes the primary. The unsaved configurations from the old primary are available on the new primary appliance.* In a cluster setup, this command can be executed only through the cluster IP address and it reboots only the configuration coordinator.


##Synopsys

reboot [-warm]


##Arguments

<b>warm</b>
Restarts the NetScaler software without rebooting the underlying operating system. The session terminates and you must log on to the appliance after it has restarted.
Note: This argument is required only for nCore appliances. Classic appliances ignore this argument.



