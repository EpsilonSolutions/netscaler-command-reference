#dns view

The following operations can be performed on "dns view":


[add](#add-dns-view) | [rm](#rm-dns-view) | [show](#show-dns-view)

##add dns view

Creates a DNS view. A DNS view is used in global server load balancing (GSLB) to return a predetermined IP address to a specific group of clients, which are identified by using a DNS policy.


##Synopsys

add dns view &lt;viewName>


##Arguments

<b>viewName</b>
Name for the DNS view.



##Example

add dns view privateview

##rm dns view

Removes a DNS view.


##Synopsys

rm dns view &lt;viewName>


##Arguments

<b>viewName</b>
Name for the DNS view.



##Example

rm dns view privateview

##show dns view

Displays the specified DNS view or, if no DNS view name is specified, all the DNS views configured on the NetScaler appliance.


##Synopsys

show dns view [&lt;viewName>]


##Arguments

<b>viewName</b>
Name of the view to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>serviceName</b>
Service name of the service using this view.NOTE: This attribute is deprecated.This attribute is deprecated. please use -gslbservicename

<b>gslbServiceName</b>
Service name of the service using this view.

<b>dnsPolicyName</b>
dnspolicy name of this view.

<b>IPAddress</b>
IP of the service corresponding to the given view.

<b>flags</b>
Flags controlling display.NOTE: This attribute is deprecated.This is deprecated attribute.

<b>stateflag</b>
flags controlling display

<b>devno</b>

<b>count</b>



