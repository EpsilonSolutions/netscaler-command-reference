#ptp

The following operations can be performed on "ptp":


[set](#set-ptp) | [show](#show-ptp)

##set ptp

Specifies whether to use Precision Time Protocol (PTP) to synchronize time across cluster nodes. This command is applicable in a cluster setup only. If you do not want to use PTP, you must disable PTP, by using this command, and instead enable NTP.


##Synopsys

set ptp -state ( DISABLE | ENABLE )


##Arguments

<b>state</b>
Enables or disables Precision Time Protocol (PTP) on the appliance. If you disable PTP, make sure you enable Network Time Protocol (NTP) on the cluster.
Possible values: DISABLE, ENABLE
Default value: NSA_PTP_ENABLE



##show ptp

Displays the status of Precision Time Protocol (PTP) on the appliance.


##Synopsys

show ptp


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>state</b>
Enables or disables Precision Time Protocol (PTP) on the appliance. If you disable PTP, make sure you enable Network Time Protocol (NTP) on the cluster.



