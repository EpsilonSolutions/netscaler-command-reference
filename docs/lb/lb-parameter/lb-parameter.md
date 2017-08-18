#lb parameter

The following operations can be performed on "lb parameter":


[set](#set-lb-parameter) | [unset](#unset-lb-parameter) | [show](#show-lb-parameter)

##set lb parameter

Modifies the specified global load balancing parameters.


##Synopsys

set lb parameter [-httpOnlyCookieFlag ( ENABLED | DISABLED )] [-useEncryptedPersistenceCookie ( ENABLED | DISABLED )] [-cookiePassphrase ] [-consolidatedLConn ( YES | NO )] [-usePortForHashLb ( YES | NO )] [-preferDirectRoute ( YES | NO )] [-startupRRFactor &lt;positive_integer>] [-monitorSkipMaxClient ( ENABLED | DISABLED )] [-monitorConnectionClose ( RESET | FIN )] [-vServerSpecificMac ( ENABLED | DISABLED )] [-AllowBoundSvcRemoval ( ENABLED | DISABLED )] [-retainservicestate ( ON | OFF )]


##Arguments

<b>httpOnlyCookieFlag</b>
Include the HttpOnly attribute in persistence cookies. The HttpOnly attribute limits the scope of a cookie to HTTP requests and helps mitigate the risk of cross-site scripting attacks.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>useEncryptedPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cookiePassphrase</b>
Use this parameter to specify the passphrase used to generate secured persistence cookie value. It specifies the passphrase with a maximum of 31 characters.

<b>consolidatedLConn</b>
To find the service with the fewest connections, the virtual server uses the consolidated connection statistics from all the packet engines. The NO setting allows consideration of only the number of connections on the packet engine that received the new connection.
Possible values: YES, NO
Default value: YES

<b>usePortForHashLb</b>
Include the port number of the service when creating a hash for hash based load balancing methods. With the NO setting, only the IP address of the service is considered when creating a hash.
Possible values: YES, NO
Default value: YES

<b>preferDirectRoute</b>
Perform route lookup for traffic received by the NetScaler appliance, and forward the traffic according to configured routes. Do not set this parameter if you want a wildcard virtual server to direct packets received by the appliance to an intermediary device, such as a firewall, even if their destination is directly connected to the appliance. Route lookup is performed after the packets have been processed and returned by the intermediary device.
Possible values: YES, NO
Default value: YES

<b>startupRRFactor</b>
Number of requests, per service, for which to apply the round robin load balancing method before switching to the configured load balancing method, thus allowing services to ramp up gradually to full load. Until the specified number of requests is distributed, the NetScaler appliance is said to be implementing the slow start mode (or startup round robin). Implemented for a virtual server when one of the following is true:
* The virtual server is newly created.
* One or more services are newly bound to the virtual server. 
* One or more services bound to the virtual server are enabled.
* The load balancing method is changed.
This parameter applies to all the load balancing virtual servers configured on the NetScaler appliance, except for those virtual servers for which the virtual server-level slow start parameters (New Service Startup Request Rate and Increment Interval) are configured. If the global slow start parameter and the slow start parameters for a given virtual server are not set, the appliance implements a default slow start for the virtual server, as follows:
* For a newly configured virtual server, the appliance implements slow start for the first 100 requests received by the virtual server.
* For an existing virtual server, if one or more services are newly bound or newly enabled, or if the load balancing method is changed, the appliance dynamically computes the number of requests for which to implement startup round robin. It obtains this number by multiplying the request rate by the number of bound services (it includes services that are marked as DOWN). For example, if the current request rate is 20 requests/s and ten services are bound to the virtual server, the appliance performs startup round robin for 200 requests.
Not applicable to a virtual server for which a hash based load balancing method is configured.
Minimum value: 0

<b>monitorSkipMaxClient</b>
When a monitor initiates a connection to a service, do not check to determine whether the number of connections to the service has reached the limit specified by the service's Max Clients setting. Enables monitoring to continue even if the service has reached its connection limit.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>monitorConnectionClose</b>
Close monitoring connections by sending the service a connection termination message with the specified bit set.
Possible values: RESET, FIN
Default value: FIN

<b>vServerSpecificMac</b>
Allow a MAC-mode virtual server to accept traffic returned by an intermediary device, such as a firewall, to which the traffic was previously forwarded by another MAC-mode virtual server. The second virtual server can then distribute that traffic across the destination server farm. Also useful when load balancing Branch Repeater appliances.
Note: The second virtual server can also send the traffic to another set of intermediary devices, such as another set of firewalls. If necessary, you can configure multiple MAC-mode virtual servers to pass traffic successively through multiple sets of intermediary devices.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>AllowBoundSvcRemoval</b>
This is used, to enable/disable the option of svc/svcgroup removal, if it is bound to one or more vserver. If it is enabled, the svc/svcgroup can be removed, even if it bound to vservers. If disabled, an error will be thrown, when the user tries to remove a svc/svcgroup without unbinding from its vservers.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>retainservicestate</b>
This option is used to retain the original state of service or servicegroup member when an enable server command is issued.
Possible values: ON, OFF
Default value: OFF



##Example

set lb parameter -httponly (ENABLED|DISABLED)

##unset lb parameter

Use this command to remove lb parameter settings.Refer to the set lb parameter command for meanings of the arguments.


##Synopsys

unset lb parameter [-httpOnlyCookieFlag] [-useEncryptedPersistenceCookie] [-cookiePassphrase] [-consolidatedLConn] [-usePortForHashLb] [-preferDirectRoute] [-startupRRFactor] [-monitorSkipMaxClient] [-monitorConnectionClose] [-vServerSpecificMac] [-AllowBoundSvcRemoval] [-retainservicestate]


##show lb parameter

Displays the global load balancing parameters.


##Synopsys

show lb parameter


##Outputs

<b>httpOnlyCookieFlag</b>
Include the HttpOnly attribute in persistence cookies. The HttpOnly attribute limits the scope of a cookie to HTTP requests and helps mitigate the risk of cross-site scripting attacks.

<b>useSecuredPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.

<b>useEncryptedPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.

<b>cookiePassphrase</b>
Use this parameter to specify the passphrase used to generate secured persistence cookie value. It specifies the passphrase with a maximum of 31 characters.

<b>consolidatedLConn</b>
To find the service with the fewest connections, the virtual server uses the consolidated connection statistics from all the packet engines. The NO setting allows consideration of only the number of connections on the packet engine that received the new connection.

<b>usePortForHashLb</b>
Include the port number of the service when creating a hash for hash based load balancing methods. With the NO setting, only the IP address of the service is considered when creating a hash.

<b>preferDirectRoute</b>
Perform route lookup for traffic received by the NetScaler appliance, and forward the traffic according to configured routes. Do not set this parameter if you want a wildcard virtual server to direct packets received by the appliance to an intermediary device, such as a firewall, even if their destination is directly connected to the appliance. Route lookup is performed after the packets have been processed and returned by the intermediary device.

<b>startupRRFactor</b>
Used to change the factor of service hits after which vserver will come out of slowstart phase.

<b>monitorSkipMaxClient</b>
When a monitor initiates a connection to a service, do not check to determine whether the number of connections to the service has reached the limit specified by the service's Max Clients setting. Enables monitoring to continue even if the service has reached its connection limit.

<b>monitorConnectionClose</b>
Close monitoring connections by sending the service a connection termination message with the specified bit set.

<b>vServerSpecificMac</b>
Allow a MAC-mode virtual server to accept traffic returned by an intermediary device, such as a firewall, to which the traffic was previously forwarded by another MAC-mode virtual server. The second virtual server can then distribute that traffic across the destination server farm. Also useful when load balancing Branch Repeater appliances.
Note: The second virtual server can also send the traffic to another set of intermediary devices, such as another set of firewalls. If necessary, you can configure multiple MAC-mode virtual servers to pass traffic successively through multiple sets of intermediary devices.

<b>sessionsThreshold</b>
This option is used to get the upper-limit on the number of persistent sessions set by the administrator for this system

<b>builtin</b>

<b>AllowBoundSvcRemoval</b>
This is used, to enable/disable the option of svc/svcgroup removal, if it is bound to one or more vserver. If it is enabled, the svc/svcgroup can be removed, even if it bound to vservers. If disabled, an error will be thrown, when the user tries to remove a svc/svcgroup without unbinding from its vservers.

<b>retainservicestate</b>
This option is used to retain the original state of service or servicegroup member when an enable server command is issued.



##Example

show lb parameter

