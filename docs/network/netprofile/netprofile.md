#netProfile

The following operations can be performed on "netProfile":


[add](#add-netprofile) | [rm](#rm-netprofile) | [set](#set-netprofile) | [unset](#unset-netprofile) | [show](#show-netprofile)

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

<b>vpathEncap</b>
enable/disable vPath Encapsulation

<b>overrideLsn</b>
USNIP/USIP settings override LSN settings for configured
              service/virtual server traffic..

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show netProfile

