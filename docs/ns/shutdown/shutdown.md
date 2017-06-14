#shutdown

The following operations can be performed on "shutdown":


##shutdown

Stops all operations and powers off the NetScaler appliance.Note:* When a standalone NetScaler appliance is shut down, the unsaved configurations (configurations performed since the last 'save ns config' command was issued) are lost.* In a high availability setup, when the primary appliance is shut down, the secondary appliance takes over and becomes the primary. The unsaved configurations from the old primary are available on the new primary appliance.* In a cluster setup, this command can be executed only through the cluster IP address and it shuts down only the configuration coordinator.


##Synopsys

shutdown


