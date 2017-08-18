#cloud parameter

The following operations can be performed on "cloud parameter":


[set](#set-cloud-parameter) | [unset](#unset-cloud-parameter) | [show](#show-cloud-parameter)

##set cloud parameter

Set the cloud parameters required to register to the cloud.


##Synopsys

set cloud parameter [-ControllerFQDN &lt;string>] [-ControllerPort &lt;port|*>] [-InstanceID &lt;string>  [-CustomerID &lt;string>]  [-ResourceLocation &lt;string>]] [-verifyURL &lt;URL>]


##Arguments

<b>ControllerFQDN</b>
FQDN of the controller to which the Netscaler SDProxy Connects

<b>ControllerPort</b>
Port number of the controller to which the Netscaler SDProxy connects
Minimum value: 1

<b>InstanceID</b>
Instance ID of the customer provided by Trust

<b>CustomerID</b>
Customer ID of the citrix cloud customer

<b>ResourceLocation</b>
Resource Location of the customer provided by Trust

<b>verifyURL</b>
Verify url will be fetched from the trust service and consumed by GUI to login to the cloud



##unset cloud parameter

Unset the cloud parameters.Refer to the set cloud parameter command for meanings of the arguments.


##Synopsys

unset cloud parameter [-InstanceID] [-CustomerID] [-ResourceLocation] [-verifyURL]


##show cloud parameter

Displays information about cloud parameters


##Synopsys

show cloud parameter


##Outputs

<b>ControllerFQDN</b>
FQDN of the controller to which the Netscaler SDProxy Connects

<b>ControllerPort</b>
Port number of the controller to which the Netscaler SDProxy connects

<b>InstanceID</b>
Instance ID of the customer provided by Trust

<b>CustomerID</b>
Customer ID of the citrix cloud customer

<b>ResourceLocation</b>
Resource Location of the customer provided by Trust

<b>verifyURL</b>
Verify url will be fetched from the trust service and consumed by GUI to login to the cloud



