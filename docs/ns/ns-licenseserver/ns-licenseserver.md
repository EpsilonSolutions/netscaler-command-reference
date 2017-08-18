#ns licenseserver

The following operations can be performed on "ns licenseserver":


[add](#add-ns-licenseserver) | [rm](#rm-ns-licenseserver) | [set](#set-ns-licenseserver) | [show](#show-ns-licenseserver)

##add ns licenseserver

Adds License server config to the appliance.


##Synopsys

add ns licenseserver (&lt;licenseServerIP> | &lt;serverName>) [-port &lt;positive_integer>]


##Arguments

<b>licenseServerIP</b>
IP address of the License server.

<b>serverName</b>
Fully qualified domain name of the License server.

<b>port</b>
License server port.
Default value: NS_LICENSE_DEFAULT_PORT
Minimum value: 0



##rm ns licenseserver

Removes the License server. You can specify the server by IP address or by name.


##Synopsys

rm ns licenseserver (&lt;licenseServerIP> | &lt;serverName>)


##Arguments

<b>licenseServerIP</b>
IP address of the License server to be removed.

<b>serverName</b>
Name of the License server to be removed.



##set ns licenseserver

Modifies the port of License server.


##Synopsys

set ns licenseserver (&lt;licenseServerIP> | &lt;serverName>) [-port &lt;positive_integer>]


##Arguments

<b>licenseServerIP</b>
IP address of the NTP server to be modified.

<b>serverName</b>
Name of the NTP server to be modified.

<b>port</b>
License server port.
Default value: NS_LICENSE_DEFAULT_PORT
Minimum value: 0



##show ns licenseserver

Displays information about an License server. You can specify the server by IP address or by name.


##Synopsys

show ns licenseserver [&lt;licenseServerIP> | &lt;serverName>]


##Arguments

<b>licenseServerIP</b>
IP address of the NTP server about which to display information.

<b>serverName</b>
Name of the NTP server about which to display information.



##Outputs

<b>port</b>
License server port.

<b>status</b>
Status of license server.

<b>grace</b>
Grace status of server.

<b>gptimeleft</b>
Grace time left

<b>devno</b>

<b>count</b>

<b>stateflag</b>



