#ns licenseproxyserver

The following operations can be performed on "ns licenseproxyserver":


[add](#add-ns-licenseproxyserver) | [rm](#rm-ns-licenseproxyserver) | [set](#set-ns-licenseproxyserver) | [show](#show-ns-licenseproxyserver)

##add ns licenseproxyserver

Adds License proxy server config to the appliance.


##Synopsys

add ns licenseproxyserver (&lt;serverIP> | &lt;serverName>) -port &lt;positive_integer>


##Arguments

<b>serverIP</b>
IP address of the License proxy server.

<b>serverName</b>
Fully qualified domain name of the License proxy server.

<b>port</b>
License proxy server port.
Minimum value: 0



##rm ns licenseproxyserver

Removes the License proxy server. You can specify the server by IP address or by name.


##Synopsys

rm ns licenseproxyserver (&lt;serverIP> | &lt;serverName>)


##Arguments

<b>serverIP</b>
IP address of the License proxy server to be removed.

<b>serverName</b>
Name of the License proxy server to be removed.



##set ns licenseproxyserver

Modifies the port of License proxy server.


##Synopsys

set ns licenseproxyserver (&lt;serverIP> | &lt;serverName>) -port &lt;positive_integer>


##Arguments

<b>serverIP</b>
IP address of the License proxy server to be modified.

<b>serverName</b>
Name of the License proxy server to be modified.

<b>port</b>
License proxy server port.
Minimum value: 0



##show ns licenseproxyserver

Displays information about an License proxy server. You can specify the server by IP address or by name.


##Synopsys

show ns licenseproxyserver [&lt;serverIP> | &lt;serverName>]


##Arguments

<b>serverIP</b>
IP address of the License proxy server about which to display information.

<b>serverName</b>
Name of the License proxy server about which to display information.



##Outputs

<b>port</b>
License proxy server port.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



