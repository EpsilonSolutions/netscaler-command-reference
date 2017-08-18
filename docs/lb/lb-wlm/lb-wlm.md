#lb wlm

The following operations can be performed on "lb wlm":


[add](#add-lb-wlm) | [rm](#rm-lb-wlm) | [set](#set-lb-wlm) | [unset](#unset-lb-wlm) | [show](#show-lb-wlm) | [bind](#bind-lb-wlm) | [unbind](#unbind-lb-wlm)

##add lb wlm

Add a Work Load Manager. NOTE: This command is deprecated.WLM feature has been deprecated from Kos onwards as classic build is not supported.


##Synopsys




##Arguments

<b>wlmName</b>
The name of the Work Load Manager.

<b>IPAddress</b>
The IP address of the WLM.

<b>port</b>
The port of the WLM.

<b>LBUID</b>
The LBUID for the Load Balancer to communicate to the Work Load Manager.

<b>KATimeout</b>
The idle time period after which NS would probe the WLM. The value ranges from 1 to 1440 minutes.
Default value: 2
Maximum value: 1440



##Example

add lb wlm ibm_wlm 10.102.1.10 3060

##rm lb wlm

Removes a Work Load Manager. NOTE: This command is deprecated.WLM feature has been deprecated from Kos onwards as classic build is not supported.


##Synopsys




##Arguments

<b>wlmName</b>
The name of the Work Load Manager to be removed.



##Example

rm lb wlm ibm_wlm

##set lb wlm

set Work Load Manager attributes NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>wlmName</b>
The name of the work load manager.

<b>KATimeout</b>
The idle time period after which NS would probe the WLM. The value ranges from 1 to 1440 minutes.
Default value: 2
Maximum value: 1440



##Example

set lb wlm ibm_wlm -ka_timeout 6

##unset lb wlm

Use this command to remove lb wlm settings.Refer to the set lb wlm command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##show lb wlm

show Work Load Manager details NOTE: This command is deprecated.WLM feature has been deprecated from Kos onwards as classic build is not supported.


##Synopsys




##Arguments

<b>wlmName</b>
The name of the work load manager.



##Outputs

<b>IPAddress</b>
The IP address of the WLM.

<b>port</b>
A port number for the virtual server.

<b>stateflag</b>

<b>secure</b>
Use this parameter to enable secure mode of communication with WLM.

<b>KATimeout</b>
The idle time period after which NS would probe the WLM. The value ranges from 1 to 1440 minutes.

<b>LBUID</b>
The LBUID for the Load Balancer to communicate to the Work Load Manager.

<b>state</b>
State of the WLM.

<b>vServerName</b>
Name of the virtual server which is to be bound to the WLM.

<b>devno</b>

<b>count</b>



##Example

show lb wlm ibm_wlm

##bind lb wlm

Bind a vserver to Work Load Manager. NOTE: This command is deprecated.WLM feature has been deprecated from Kos onwards as classic build is not supported.


##Synopsys




##Arguments

<b>wlmName</b>
The name of the Work Load Manager.

<b>vServerName</b>
Name of the virtual server which is to be bound to the WLM.



##Example

bind lb wlm ibm_wlm http_vip 	To bind multiple vservers to workload manager use the following command:	bind lb wlm ibm_wlm http_vip[1-3]

##unbind lb wlm

Unbind a vserver from Work Load Manager. NOTE: This command is deprecated.WLM feature has been deprecated from Kos onwards as classic build is not supported.


##Synopsys




##Arguments

<b>wlmName</b>
The name of the Work Load Manager.

<b>vServerName</b>
Name of the virtual server which is to be unbound from the WLM.



##Example

unbind lb wlm ibm_wlm http_vip	To unbind multiple vservers from Work Load Manager use the following command:	unbind lb wlm ibm_wlm http_vip[1-3]

