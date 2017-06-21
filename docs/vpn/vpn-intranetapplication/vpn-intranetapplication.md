#vpn intranetApplication

The following operations can be performed on "vpn intranetApplication":


[add](#add-vpn-intranetapplication) | [rm](#rm-vpn-intranetapplication) | [show](#show-vpn-intranetapplication)

##add vpn intranetApplication

Defines intranet applications to be made accessible through NetScaler Gateway.


##Synopsys

add vpn intranetApplication &lt;intranetApplication> [&lt;protocol>] ((&lt;destIP>  [-netmask &lt;netmask>]) | &lt;IPRange> | &lt;hostName>) [-destPort &lt;port[-port]>] [-interception ( PROXY | TRANSPARENT )  [-srcIP &lt;ip_addr>]  [-srcPort &lt;port>]]


##Arguments

<b>intranetApplication</b>
Name of the intranet application.

<b>protocol</b>
Protocol used by the intranet application. If protocol is set to BOTH, TCP and UDP traffic is allowed.
Possible values: TCP, UDP, ANY

<b>destIP</b>
Destination IP address, IP range, or host name of the intranet application. This address is the server IP address.

<b>netmask</b>
Destination subnet mask for the intranet application.
Default value: 0xFFFFFFFF

<b>IPRange</b>
If you have multiple servers in your network, such as web, email, and file shares, configure an intranet application that includes the IP range for all the network applications. This allows users to access all the intranet applications contained in the IP address range.

<b>hostName</b>
Name of the host for which to configure interception. The names are resolved during interception when users log on with the NetScaler Gateway Plug-in.

<b>destPort</b>
Destination TCP or UDP port number for the intranet application. Use a hyphen to specify a range of port numbers, for example 90-95.
Minimum value: 1

<b>interception</b>
Interception mode for the intranet application or resource. Correct value depends on the type of client software used to make connections. If the interception mode is set to TRANSPARENT, users connect with the NetScaler Gateway Plug-in for Windows. With the PROXY setting, users connect with the NetScaler Gateway Plug-in for Java.
Possible values: PROXY, TRANSPARENT

<b>srcIP</b>
Source IP address. Required if interception mode is set to PROXY. Default is the loopback address, 127.0.0.1.

<b>srcPort</b>
Source port for the application for which the NetScaler Gateway virtual server proxies the traffic. If users are connecting from a device that uses the NetScaler Gateway Plug-in for Java, applications must be configured manually by using the source IP address and TCP port values specified in the intranet application profile. If a port value is not set, the destination port value is used.
Minimum value: 1



##rm vpn intranetApplication

Removes a configured intranet resource.


##Synopsys

rm vpn intranetApplication &lt;intranetApplication>


##Arguments

<b>intranetApplication</b>
Name of the intranet resource to remove.



##show vpn intranetApplication

Displays information about all the configured intranet resources, or displays detailed information about the specified intranet resource.


##Synopsys

show vpn intranetApplication [&lt;intranetApplication>]


##Arguments

<b>intranetApplication</b>
Name of the intranet resource for which to display detailed information.



##Outputs

<b>protocol</b>
The IP protocol; for example, TCP, UDP or ANY

<b>destIP</b>
The destination IP address.

<b>netmask</b>
The destination netmask.

<b>IPAddress</b>
The IP address for the application. This address is the real application server IP address.

<b>hostName</b>
Name based interception. Names should be valid dns or wins names and will be resolved during interception on the sslvpn.

<b>destPort</b>
The destination port.

<b>clientApplication</b>
Names of the client applications, such as PuTTY and Xshell.

<b>spoofIIP</b>
This specifies whether to spoof this application on the client.

<b>interception</b>
The interception type; for example, proxy or transparent.

<b>srcIP</b>
The source IP address.

<b>srcPort</b>
The source port.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



