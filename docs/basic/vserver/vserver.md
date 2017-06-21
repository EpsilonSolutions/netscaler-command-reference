#vserver

The following operations can be performed on "vserver":


[rm](#rm-vserver) | [set](#set-vserver) | [unset](#unset-vserver) | [enable](#enable-vserver) | [disable](#disable-vserver) | [show](#show-vserver)

##rm vserver

Use this command to remove a virtual server. NOTE: This command is deprecated.This command is deprecated in 10.0, instead you can use commands such as rm lb vserver


##Synopsys




##Arguments

<b>name</b>
The name of the virtual server to be removed.



##Example

rm vserver lb_vip	To remove multiple vservers, use the following command:	rm vserver lb_vip[1-3]

##set vserver

Use this command to modify the parameters for an existing virtual server. NOTE: This command is deprecated.This command is deprecated in 10.0, instead you can use commands such as set lb vserver


##Synopsys




##Arguments

<b>name</b>
The name of the virtual server for which the parameters are to be set.

<b>pushVserver</b>
The lb vserver of type PUSH/SSL_PUSH to which server pushes the updates received on the client facing non-push lb vserver.



##Example

set vserver lb_vip -backupVServerName bkvip_lbvip	To set backup vserver for multiple vservers at once, use the following command:	set vserver lb_vip[1-3] -backupVServerName bkvip_lbvip

##unset vserver

Use this command to unset the backup virtual server or the redirectURL that has been set on the virtual server..Refer to the set  vserver command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##Example

unset vserver lb_vip -backupVServer       To unset the backup vserver for multiple vservers use the following command:	unset vserver lb_vip[1-3] -backupVServer

##enable vserver

Use this command to enable a virtual server. Note:	Virtual servers, when added, are enabled by default. NOTE: This command is deprecated.This command is deprecated in 10.0, instead you can use commands such as enable lb vserver


##Synopsys




##Arguments

<b>name</b>
The name of the virtual server to be enabled.



##Example

enable vserver lb_vip	To enable multiple vservers, use the following command:        enable vserver lb_vip[1-3]

##disable vserver

Use this command to disable (take out of service) a virtual server. NOTE: This command is deprecated.This command is deprecated in 10.0, instead you can use commands such as disable lb vserver


##Synopsys




##Arguments

<b>name</b>
The name of the virtual server to be disabled.
Notes:
1.	The system will continue to respond to ARP and/or ping requests for the IP address of this virtual server.
2.	As the virtual server is still configured in the system, you can enable the virtual server using the ###enable vserver### command.



##Example

disable vserver lb_vip	To disable multiple vservers, use the following command:	disable vserver lb_vip[1-3]

##show vserver

Displays information about all virtual servers configured on the appliance.


##Synopsys

show vserver


##Example

show vserver lb_vip

