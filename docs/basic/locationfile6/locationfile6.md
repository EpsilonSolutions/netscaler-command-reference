#locationFile6

The following operations can be performed on "locationFile6":


[add](#add-locationfile6) | [rm](#rm-locationfile6) | [show](#show-locationfile6)

##add locationFile6

Loads the IPv6 static location database from the specified file.


##Synopsys

add locationFile6 &lt;locationFile> [-format ( netscaler6 | geoip-country6 )]


##Arguments

<b>locationFile</b>
Name of the IPv6 location file, with or without absolute path. If the path is not included, the default path (/var/netscaler/locdb) is assumed. In a high availability setup, the static database must be stored in the same location on both NetScaler appliances.

<b>format</b>
Format of the IPv6 location file. Required for the NetScaler appliance to identify how to read the location file.
Possible values: netscaler6, geoip-country6
Default value: netscaler6



##Example

add locationfile6 /var/nsmap/locationdb  -format netscaler6

##rm locationFile6

Removes the currently loaded static location database from the NetScaler appliance.


##Synopsys

rm locationFile6


##Example

rm locationfile6

##show locationFile6

Displays the name, including the absolute path, and format of the location file currently loaded on the NetScaler appliance.


##Synopsys

show locationFile6


##Outputs

<b>locationFile</b>
The name of the location file.

<b>format</b>
The format of the location file.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show locationfile6

