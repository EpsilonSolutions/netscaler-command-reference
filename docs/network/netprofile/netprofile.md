#netProfile

The following operations can be performed on "netProfile":


[add](#add-netprofile) | [rm](#rm-netprofile) | [set](#set-netprofile) | [unset](#unset-netprofile) | [bind](#bind-netprofile) | [unbind](#unbind-netprofile) | [show](#show-netprofile)

##add netProfile

Creates a net profile. A net profile (or network profile) contains an IP address or an IP set. During communication with physical servers or peers, the NetScaler appliance uses the addresses specified in the profile as the source IP address.


##Synopsys

add netProfile &lt;name> [-td &lt;positive_integer>] [-srcIP &lt;string>] [-srcippersistency ( ENABLED | DISABLED )] [-overrideLsn ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the net profile. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the profile is created. Choose a name that helps identify the net profile.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>srcIP</b>
IP address or the name of an IP set.

<b>srcippersistency</b>
When the net profile is associated with a virtual server or its bound services, this option enables the NetScaler appliance to use the same  address, specified in the net profile, to communicate to servers for all sessions initiated from a particular client to the virtual server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>overrideLsn</b>
USNIP/USIP settings override LSN settings for configured
              service/virtual server traffic.. 
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add netProfile prof1 -srcip 10.102.1.10 

##rm netProfile

Removes a net profile from the NetScaler appliance.


##Synopsys

rm netProfile &lt;name> ...


##Arguments

<b>name</b>
Name of the net profile to be removed.



##Example

rm netProfile prof1

##set netProfile

Modifies the srcIP parameter of a net profile.


##Synopsys

set netProfile &lt;name> [-srcIP &lt;string>] [-srcippersistency ( ENABLED | DISABLED )] [-overrideLsn ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the net profile whose parameter you want to modify.

<b>srcIP</b>
IP address or the name of an IP set.

<b>srcippersistency</b>
When the net profile is associated with a virtual server or its bound services, this option enables the NetScaler appliance to use the same  address, specified in the net profile, to communicate to servers for all sessions initiated from a particular client to the virtual server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>overrideLsn</b>
USNIP/USIP settings override LSN settings for configured
              service/virtual server traffic.. 
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set netProfile prof_1 -srcIP 10.102.1.10

##unset netProfile

Removes the srcIP attribute of a net profile..Refer to the set  netProfile command for meanings of the arguments.


##Synopsys

unset netProfile &lt;name> [-srcIP] [-srcippersistency] [-overrideLsn]


##Example

unset netProfile prof1 -srcIP

##bind netProfile

Binds specified port range to a netprofile.


##Synopsys

bind netProfile &lt;name> (-srcPortRange &lt;int[-int]> ... | (-natRule &lt;ip_addr>  &lt;netmask>  &lt;rewriteIp>))


##Arguments

<b>name</b>
Name of the netprofile to which to bind port ranges.

<b>srcPortRange</b>
When the source port range is configured and associated with the netprofile bound to a service group, Netscaler will choose a port from the range configured for connection establishment at the backend servers.
Minimum value: 1024
Maximum value: 65535

<b>natRule</b>
When Natrule is configured and netprofile is bound to lb vserver, NetScaler will use the prefix of rewrite IP for outgoing packets if prefix of source IP of incoming packet matches with prefix of IP of natrule.
This will take preference over USIP and USNIP configuration.
  ip_addr   : IP for which prefix need to rewritten.
  netmask   : Netmask for NatRule IP and RewriteIP.
  rewriteIp : Prefix for modified IP.

<b>netmask</b>

<b>rewriteIp</b>



##Example

bind netprofile npf_1 -srcportrange 2000-3000bind netprofile npf_1 -natRule 10.0.0.0 255.0.0.0 11.0.0.0

##unbind netProfile

Unbinds the specified port range from a netprofile.


##Synopsys

unbind netProfile &lt;name> (-srcPortRange &lt;int[-int]> ... | (-natRule &lt;ip_addr>  &lt;netmask>))


##Arguments

<b>name</b>
Name of the netprofile to which to bind port ranges.

<b>srcPortRange</b>
When the source port range is configured and associated with the netprofile bound to a service group, Netscaler will choose a port from the range configured for connection establishment at the backend servers.
Minimum value: 1024
Maximum value: 65535

<b>natRule</b>
Unbind the already bound natrule from netProfile.

<b>netmask</b>



##Example

unbind netprofile npf_1 -srcportrange 2000-3000unbind netprofile npf_1 -natrule 1.0.0.0 255.0.0.0

##show netProfile

Displays the settings of all net profiles configured on the NetScaler appliance, or of the specified net profile.


##Synopsys

show netProfile [&lt;name>]


##Arguments

<b>name</b>
Name of the net profile whose details you want to display.



##Outputs

<b>srcIP</b>
Source IPaddress or IPSET name.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>srcippersistency</b>
When the net profile is associated with a virtual server or its bound services, this option enables the NetScaler appliance to use the same  address, specified in the net profile, to communicate to servers for all sessions initiated from a particular client to the virtual server.

<b>netprofRefcount</b>
Used to keep reference count of IP

<b>overrideLsn</b>
USNIP/USIP settings override LSN settings for configured
              service/virtual server traffic..

<b>srcPortRange</b>
When the source port range is configured and associated with the netprofile bound to a service group, Netscaler will choose a port from the range configured for connection establishment at the backend servers.

<b>stateflag</b>
state flag

<b>flags</b>

<b>natRule</b>
IPv4 network address on whose traffic you want the NetScaler appliance to do rewrite ip prefix.

<b>netmask</b>

<b>rewriteIp</b>

<b>devno</b>

<b>count</b>



##Example

show netProfile

